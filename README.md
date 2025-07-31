# Foodlog

A simple Rails application for tracking daily food intake and nutritional information. Built with Rails 8.0.2 and Ruby 3.4.5.

## Features

- Log food entries with nutritional information (calories, proteins, carbohydrates, fats)
- Track meal types (breakfast, lunch, dinner, snacks)
- View all entries in a card-based layout
- Edit and delete entries
- Responsive design using Bulma CSS framework

## Prerequisites

Before running this application, make sure you have the following installed:

- **Ruby 3.4.5** (use [rbenv](https://github.com/rbenv/rbenv) or [rvm](https://rvm.io/) to manage Ruby versions)
- **Rails 8.0.2**
- **SQLite3** (usually comes with Rails)
- **Node.js** (for asset compilation)

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd foodlog
   ```

2. **Install Ruby dependencies**
   ```bash
   bundle install
   ```

3. **Set up the database**
   ```bash
   rails db:create
   rails db:migrate
   rails db:seed
   ```

4. **Start the Rails server**
   ```bash
   rails server
   ```

5. **Open your browser**
   Navigate to [http://localhost:3000](http://localhost:3000)

## Database Setup

The application uses SQLite3 as the database. The database files will be created in the `storage/` directory:

- `storage/development.sqlite3` - Development database
- `storage/test.sqlite3` - Test database

## Running Tests

```bash
rails test
```

## Development

### Key Files

- **Models**: `app/models/entry.rb` - Food entry model with validations
- **Controllers**: `app/controllers/entries_controller.rb` - CRUD operations for entries
- **Views**: `app/views/entries/` - Entry display and forms
- **Database**: `db/schema.rb` - Database schema definition

### Database Schema

The `entries` table contains:
- `meal_type` (string) - Type of meal (breakfast, lunch, dinner, snack)
- `calories` (integer) - Calorie count
- `proteins` (integer) - Protein in grams
- `carbohydrates` (integer) - Carbohydrates in grams
- `fats` (integer) - Fats in grams
- `created_at` / `updated_at` (datetime) - Timestamps

## Deployment

This application includes Docker support and Kamal deployment configuration:

```bash
# Build Docker image
docker build -t foodlog .

# Run with Docker
docker run -p 3000:3000 foodlog
```

For production deployment using Kamal:
```bash
kamal deploy
```

## Troubleshooting

### Common Issues

1. **Ruby version mismatch**
   ```bash
   rbenv install 3.4.5
   rbenv local 3.4.5
   ```

2. **Database issues**
   ```bash
   rails db:reset
   ```

3. **Asset compilation issues**
   ```bash
   rails assets:precompile
   ```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is open source and available under the [MIT License](LICENSE).
