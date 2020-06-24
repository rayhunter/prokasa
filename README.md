# prokasa

> an application that renders Kasa reservation data to a user

1) explore using a service worker for app offline use,
   online the app should reload it's data instead of using the cached data

2) following URLs should be handled:

   /: the list page of the reservation, with a select box here to   
      select the chosen reservation

   /:confirmationCode: the detail view of the given reservation

3) use the Nuxt framework to create an SPA app

4) create a simple backend service that return static data or use a  
   3rd party mock api client

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

## steps to verify Progressive Web App

after running 'yarn build' & 'yarn start', open URL in Chrome,
click the vertical three dots in the upper right-hand corner of the browser,  and you should see a link to install 'Prokasa' locally. it should function just the same.


## example mock data 
## @ https://demo6894002.mockable.io/reservations

[
  {
    confirmationCode: 'AAAAAA',
    checkInDate: '2020-02-10',
    checkOutDate: '2020-02-14',
    city: 'San Francisco, CA',
		rating: null,
    cityImage:
      '<https://cdn.pixabay.com/photo/2013/11/13/21/14/san-francisco-210230_960_720.jpg>'
  },
  {
    confirmationCode: 'BBBBBB',
    checkInDate: '2020-03-10',
    checkOutDate: '2020-03-14',
    city: 'Los Angeles, CA',
		rating: 3,
    cityImage:
      '<https://cdn.pixabay.com/photo/2016/10/25/12/28/los-angeles-1768743_960_720.jpg>'
  },
  {
    confirmationCode: 'CCCCCC',
    checkInDate: '2020-04-10',
    checkOutDate: '2020-04-14',
    city: 'New York City, NY',
		rating: 5,
    cityImage:
      '<https://cdn.pixabay.com/photo/2016/01/19/18/00/city-1150026_960_720.jpg>'
  }
]

## Test Flow

(Online) 
  - Visit the main page → a list of reservations is shown to me
  - Select a reservation -> the reservation's details are loaded from 
    the server -> they are rendered
  - Visit the main page again. Select another reservation -> the 
    reservation's details are loaded from the server -> they are rendered
  - I go back to the first reservation -> the data from the server is 
    re-loaded
  - Open a new tab, and visit the first reservation directly → the 
    reservation's details are loaded from the server

(Offline) 
  - Visit the main page again → the reservation list is loaded from 
    cache
  - Visit the first reservation → reservation's details are loaded 
    from cache
  - Visit the third reservation → an error is shown that there is no 
    internet access available
  - Open a new tab, and visit the second reservation directly → the  
    reservation's details are loaded from cache

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
