# Assignment

## Brief

Create an ERD for each of the following case study question.

## Instructions

Paste the answer as DBML in the answer code section below each question.

### Question 1

Construct an ERD for a social media company whose database includes information about users, their followers, and the posts that they make. Users can follow multiple users and create multiple posts.

Each entity has the following attributes:

- User: id, username, email, created_at
- Post: id, title, body, user_id, status, created_at
- Follows: following_user_id, followed_user_id, created_at

Answer:

```dbml
Table user {
  id int [pk, increment]
  username varchar
  email varchar
  created_at datetime
}

Table post {
  id int [pk, increment]
  title varchar
  body varchar
  user_id int 
  status varchar
  created_at datetime

}

Table follows {
  following_user_id int 
  followed_user_id int 
  created_at datetime 
}

Ref: post.user_id > user.id
Ref: follows.following_user_id > user.id
Ref: follows.followed_user_id > user.id

```

### Question 2

Construct an ERD for a company that sells books online. The company has a website where customers can browse available books and add them to their shopping carts. Each cart can contain multiple books.

There are 4 entities, think of what attributes each entity should have.

- Customer
- Book
- Cart
- CartItem

Answer:

```dbml
Table customer {
  id int [pk, increment]
  name varchar
  email varchar
  address varchar
  phone_number int
  date_of_birth datetime
}

Table book {
  id int [pk, increment]
  isbn varchar
  title varchar
  genre varchar
  author varchar
  price decimal
  status varchar
  year_published datetime

}

Table cart {
  id int 
  customer_id int
  status varchar
  created_at datetime 
}

Table cartitem {
  cart_id int [pk, increment]
  book_id int [pk, increment]
  quantity int
  unit_price decimal
  created_at datetime

}
Ref: cart.customer_id > customer.id
Ref: cartitem.cart_id > cart.id
Ref: cartitem.book_id > book.id
```

## Submission

- Submit the URL of the GitHub Repository that contains your work to NTU black board.
- Should you reference the work of your classmate(s) or online resources, give them credit by adding either the name of your classmate or URL.
