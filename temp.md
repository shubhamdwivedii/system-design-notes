

Movie Booking BMS 

1. Cites

2. Users
3. Movies/Events 
4. Theatres 
5. Screens 
6. Seats 
7. Tiers // golden
8. Show (movies, screenid)
9. Bookings (paymentid, userid, status)
10. Reviews 

Users {
    id int 
    name varchar 
    email varchar 
}

Movies {
    id int 
    title varchar 
    description varchar
    createdAt datetime
}

Theatres {
    id int 
    cityid int [ref: > Cities]
    name varchar 
    address varchar
}

Screens {
    id int unique
    theatre_id int [ref: > Theatre]
    code varchar [note: "1, a"]
    totalSeats int 
}

Tiers {
    id int 
    screen_id int [ref: > Screens]
    code varchar 
    tile varchar [note: "golden/silver"]
}

Seats {
    id int 
    screen_id int [ref: > Screens]
    tier_id int [ref: > Theatres]
    code varchar "30b"
}


Shows {
    id int 
    movie_id [ref: > Movies]
    screen_id [ref: > Screens]
    theatre_id [ref: > Theater]
    start_time datetime 
    end_time datetime 
}

SeatBooking {
    id int 
    seatId [ref: > Seats]
    bookingId [ref: > Booking]
    show_id [ref: > Shows]
    status enum ["locked", "booked", "available"]
}

Booking {
    id int 
    userId [ref: > User]
    payment_status enum ["pending", "complete", "cancelled"]
    booking_status enum ["locked", "booked", "cancelled"]
    created_at datetime 
}


// 

GetUserBookingsByDurations(userId, startDate, endDate) {
    SELECT (bookingId) from Bookings where created_at >= startDate AND created_at <= endDate
}


// 

GetFreeSeatsForMovie(movieId) {
    SELECT (Screens.totalSeats - Count(SeatBooking.id))
    FROM Movies 
    INNER JOIN Shows 
    ON Movies.id = Shows.movie_id 
    INNER JOIN Screens
    ON Shows.screen_id = Screens.id 
    INNER JOIN SeatBookings 
    ON Shows.id = SeatBooking.show_id   
    GROUP BY Shows.id 
}


Orderid, date, userid 

user < orders 

Select Count(*) From Orders 
Group By userid


1 2 A 
2 2 B 
3 2 A 



ShowId  Count(Seats)
1        42 
3        53

Morning Uber 