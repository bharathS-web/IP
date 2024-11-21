# Ruby on Rails 

## Rails Framework

Rails is a web application framework built with Ruby for building clean, organized websites and applications.

### MVC (Model-View-Controller) Pattern

- **Model**: Manages data and business logic
- **View**: Handles UI/UX (HTML, CSS)
- **Controller**: Manages user input and application flow

## Rails with Database

Rails simplifies database interaction using Active Record.

### Key Database Features

- **Models**: Represent data (e.g., users, products) and interact with the database
- **Migrations**: Manage database structure (e.g., create or modify tables)
- **CRUD Operations**: Effortlessly perform Create, Read, Update, and Delete operations

## Steps to Build a Rails App with Database

### 1. Install Rails

```bash
gem install rails
```

### 2. Create a New Rails Application

```bash
rails new myapp
cd myapp
```

### 3. Generate a Model and Table

Create a Product model with name (string) and price (float):

```bash
rails generate model Product name:string price:float
```

### 4. Run the Migration

Update the database schema:

```bash
rails db:migrate
```

### 5. Use the Rails Console

Open the Rails console to interact with the database:

```bash
rails console
```

### 6. CRUD Operations

#### Create

```ruby
Product.create(name: "Widget A", price: 19.99)
```

#### Read

```ruby
Product.all
Product.find(1)
```

#### Update

```ruby
product = Product.find(1)
product.update(price: 24.99)
```

#### Delete

```ruby
Product.find(2).destroy
```

### 7. Exit Console

```ruby
exit
```

## Key Concepts Recap

### Models
- Define data and database interaction

### Migrations
- Manage schema changes

### CRUD
- Easy data manipulation

### MVC Pattern
- **Models**: Handle data
- **Views**: Display content
- **Controllers**: Process logic
