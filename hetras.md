**Create PMS Reservation**

PMS::RegistrationAdapter.new(venue: Venue.first, user: User.last, confirmation_id: '92145986', last_name: 'test3').synchronize_registration


**Update Guest Profile**

PMS::GuestInfoAdapter.new(Reservation.last).push_info
