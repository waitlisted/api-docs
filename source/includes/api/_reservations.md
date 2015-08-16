# Reservations

## Create a Reservation

```ruby
require 'waitlisted'

Waitlisted::Reservation.create(email: "test@test.com", name: "Greg Smith")
# => #<Waitlisted::Reservation:0x007fbecac2c3c0 @id="f12b29bd8a7ca8cfae639539e8507bad", @uuid="f12b29bd8a7ca8cfae639539e8507bad", @affiliate="fd2c7e6802c9", @email="test@test.com", @name=nil, @position=1, @meta={"total"=>1}>

```

```javascript

var api = new Waitlisted.Api({domain: "kittens.app.waitlisted.co"})

api.reserve({email: 'test@test.com'}).then(function(reservation) {
  console.log(reservation)
})

// {
//   "reservation": {
//     "id": "e7252b80151d969450359cf904a44d08",
//     "uuid": "e7252b80151d969450359cf904a44d08",
//     "affiliate": "698e556c200b",
//     "email": "testing123456@test.com",
//     "name": "Joe Smith",
//     "position": 3
//   },
//   "meta": {
//     "total": 3
//   }
// }


```

```shell
curl https://kittens.app.waitlisted.co/api/v1/reservation -d "reservation[email]=tester123%40test.com&reservation[name]=Greg+Smith"

#{
#    "reservation": {
#        "id": "d7507474267df6b7884fe25948d1352b",
#        "uuid": "d7507474267df6b7884fe25948d1352b",
#        "affiliate": "2b81645184ef",
#        "email": "tester123@test.com",
#        "name": "Greg Smith",
#        "position": 2
#    },
#    "meta": {
#        "total": 2
#    }
#}
```

This endpoint retrieves a specific reservation.

### HTTP Request

`POST https://kittens.app.waitlisted.co/api/v1/reservation`

### URL Parameters

Parameter | Description
--------- | -----------
Email | The email of the person requesting reservation
Name  | The name of the person requesting the reservation



## Get a Specific Reservation

```ruby
require 'waitlisted'

Waitlisted::Reservation.find(email: "test@test.com")
# => #<Waitlisted::Reservation:0x007fbecac2c3c0 @id="f12b29bd8a7ca8cfae639539e8507bad", @uuid="f12b29bd8a7ca8cfae639539e8507bad", @affiliate="fd2c7e6802c9", @email="test@test.com", @name=nil, @position=1, @meta={"total"=>1}>

```

```javascript
var api = new Waitlisted.Api({domain: "kittens.app.waitlisted.co"})

api.position('testing123456@test.com').then(function(reservation) {
  console.log(reservation)
})

// {
//   "reservation": {
//     "id": "e7252b80151d969450359cf904a44d08",
//     "uuid": "e7252b80151d969450359cf904a44d08",
//     "affiliate": "698e556c200b",
//     "email": "testing123456@test.com",
//     "name": "Joe Smith",
//     "position": 3
//   },
//   "meta": {
//     "total": 3
//   }
// }

```

```shell
curl "https://kittens.app.waitlisted.co/api/v1/reservation?email=test@test.com"

# {
#   "reservation": {
#       "id": "f12b29bd8a7ca8cfae639539e8507bad",
#       "uuid": "f12b29bd8a7ca8cfae639539e8507bad",
#       "affiliate": "fd2c7e6802c9",
#       "email": "test@test.com",
#       "name": null,
#       "position": 1
#   },
#   "meta": {
#       "total": 1
#   }
# }
```

This endpoint retrieves a specific reservation.

### HTTP Request

`GET https://kittens.app.waitlisted.co/api/v1/reservation?email=<Email>`

### URL Parameters

Parameter | Description
--------- | -----------
Email | The email of the specific reservation