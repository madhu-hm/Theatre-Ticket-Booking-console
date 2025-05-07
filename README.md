PROJECT : THEATRE TICKET BOOKING SYSTEM
TITLE : THEATRE HUB
TARGET AUDIENCE : Theatre Administration Team
TYPE : B2B
TIMELINE : 2weeks
BUDGET : 0
TOTAL MEMBERS : 1
FEATURES :
	Admin Authentication
	Show Management:
		Add,edit, and delete shows
		Add show details
		Set show status
	Theatre layout:
		Seating structure
		Seating category
		Representation numbers for seats
	Pricing Details:
		Set ticket prices for different categories
		Discount and special offers
	Ticket Booking:
		View seat availability
		Select seats and apply ticket types
		Generate unique booking IDs
	Customer details:
		Add and edit customer information
		Search filters
		View customer booking history
	Reporting:
		Revenue details
		Export reports to text files
	Booking Administration:
		View all bookings
		Process Ticket cancellation and refunds
		Modify existing bookings
		Print or Display ticket information
DATA MODEL:
	Admin Class
		admin_id String
		username String
		password String
	Show-Class
		show_id String
		movie_title String
		description String
		start_time Date/Time
		end_time Date/Time
		status String("Active"/"Cancelled"/"Completed")
		theatre_id String
	TheatreLayout-Class
		layout_id String
		theatre_id String
		category String("VIP"/"Regular"/"Economy")
		rows int
		columns int
		seat_map Map<seat_number,category>
	Seat-Class
		seat_id String
		seat_number String
		category String
		is_booked Boolean
	Pricing-Class
		category String
		price Double
		discount Double
		offer_description String
	Booking-Class
		booking_id String
		show_id String
		customer_id String
		booked_seats List<Seat>
		ticket_type String("Standard"/"Offer")
		total_amount Double
		booking_time Date/Time
		status String("Confirmed"/"Cancelled")
	Customer-Class
		customer_id String
		name String
		emailid String
		phoneno String/long
		booking_history List<Booking>
	Report-Class
		report_id String
		generated_date Date
		revenue_generated Double
		total_bookings int
		export_file_path String
	BookingAdmin-Class
		viewAllBookings() List<Booking>
		CancelBooking(booking_id String)
		RefundBooking(booking_id String)
		ModifyBooking(booking_id String)
		PrintTicket(booking_id String)
	SearchFilter-Class
		filterByMovieTitle String
		filterByCustomerName String
		filterByDate Date
		filterByStatus String
