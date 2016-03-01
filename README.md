_**PostoExpress** is an on demand dispatch platform aiming to provide convenience to customers and dispatch riders._

# PostoPy
Posto Express Python API Wrapper 


### Installation
`python setup.py install`

### Usage

[Authentication](https://postoapi.com/api/#api_authentication):

```
from postopy import PostoExpress
client = PostoExpress(app_id=APP_ID, token=APP_TOKEN)
```

[Zone Calculator](https://postoapi.com/api/#api_zon_calculator):

`client.estimateByZone(pickup="KUL", delivery="SGR")`

[Post Code Calculator](https://postoapi.com/api/#api_postcode_calculator):

`client.estimateByPostcode(pickup=47000, delivery=52100)`

[Address Calculator](https://postoapi.com/api/#api_address_calculator):

```
pickup = "Damai Perdana 3/1A, Bandar Damai Perdana"
delivery = "Jalan 4/3H, Seksyen 3, Bandar Baru Bangi"
client.estimateByAddress(pickup=pickup, delivery=delivery)
```

[Live Tracker](https://postoapi.com/api/#api_live_tracker):

`client.track(jobid=420)`

[Create Booking](https://postoapi.com/api/#api_create_booking):

```
parcel_details = {
    'sender_fullname': "John Doe",
    'sender_email': "john.doe@email.com",
    'sender_phone': "+60122643163",
    'recipient_fullname': "Steven Lee",
    'recipient_email': "steven.lee@email.com",
    'recipient_phone': "+60123728133",
    'pickup_address': "5,Damai Perdana 3/1A,Bandar Damai Perdana",
    'delivery_address': "Jalan 4/3H, Seksyen 3, Bandar Baru Bangi",
    'pickup_latlng': "3.0472518,101.7385738",
    'delivery_latlng': "2.9615434,101.7774194",
    'distance_km': 20.3,
    'price_myr': 21,
    'trip_type': 1,
    'instruction_notes': "Please call me when you have reached.",
    'datetime_pickup': datetime.datetime.now(),
}
client.book(**parcel_details)
```

[Booking Details](https://postoapi.com/api/#api_booking_details):

`client.bookingDetail(jobid=420, rider=290)`

[Retrieve History](https://postoapi.com/api/#api_get_history):

`client.history()`



