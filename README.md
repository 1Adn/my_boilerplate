# 🚀 Ruby on Rails template

A custom Ruby on Rails template designed to help you kickstart your projects with pre-configured tools and settings.

---

## 🧩 Features

### **Gem Configuration**

This template includes essential gems for rapid development:

- **[PostgreSQL](https://www.postgresql.org/docs/):** Relational database.
- **[Bootstrap](https://getbootstrap.com/):** Pre-installed Bootstrap 5 for responsive design.
- **[Devise](https://github.com/heartcombo/devise):** User authentication made easy.
- **[Simple Form](https://github.com/heartcombo/simple_form):** Simplified form helpers with Bootstrap integration.
- **[Rspec](https://rspec.info/):** A testing framework for behavior-driven development.
- **[FactoryBot](https://github.com/thoughtbot/factory_bot):** Simplified test data generation.
- **[Faker](https://github.com/faker-ruby/faker):** Random data generation for testing.
- **[dotenv-rails](https://github.com/bkeepers/dotenv):** Environment variable management.
- **[SimpleCov](https://github.com/simplecov-ruby/simplecov):** Test coverage analysis.

### **Pre-configured Layout**

- **Bootstrap Navbar:** Responsive and styled navigation bar.
- **Flashes:** Styled Bootstrap alerts for `notice` and `alert` messages.

### **Automated CI/CD**

- GitHub Actions integration for Continuous Integration:
  - Runs tests on every push to `main`.
  - Uses Ruby 3.2 and Rails for testing.

### **Git Initialization**

- Automatically initializes a Git repository.
- Adds `.env` and unnecessary files to `.gitignore`.
- Creates an initial commit.

### **Other Features**

- Generates a home page with Devise user authentication.
- Configures RSpec as the default testing framework.
- Configures environment settings for development.

---

## 🛠️ Usage

### Prerequisites

Ensure you have the following installed:

- **Ruby** (>= 3.2)
- **Rails** (>= 7.0)
- **Git**

### Setting Up a New Project

1. Clone this repository or download the `template.rb` file:

   ```bash
   git clone https://github.com/1Adn/my_template
   ```

2. Create a new Rails project using the template script directly:

   ```bash
   rails new my_project_name -d postgresql -m https://github.com/1Adn/my_template/blob/main/boilerplate.rb
   ```

3. Let the template do its magic! It will:

   - Install and configure gems.
   - Create a PagesController with a home action.
   - Set up Devise for authentication.
   - Initialize a Git repository and make the first commit.

4. Create and migrate the database:

   ```bash
   rails db:create db:migrate
   ```

5. Start your Rails server:
   ```bash
   cd my_project_name
   rails server
   ```

## 📖 Detailed Features

### 🛠️ Gemfile Setup

- Automatically adds essential gems:
  - **bootstrap**: For responsive and modern design.
  - **devise**: For user authentication.
  - **rspec-rails**: For behavior-driven testing.
- Integrates **Bootstrap 5** with **Simple Form** for elegant forms.

---

### 🎨 Layout Customization

- Replaces the default Rails layout with a **Bootstrap-styled version**.
- Adds the following UI components:
  - **Responsive Navbar**: A fully functional navigation bar.
  - **Flash Alerts**: Styled with Bootstrap for `notice` and `alert` messages.

---

### 📂 Controller and Routes

- Automatically generates a `PagesController` with:
  - A `home` action.
- Sets the root route to:
  ```ruby
  root to: "pages#home"
  ```

### 🛠 Database Configuration

This template uses **PostgreSQL** as the default database. Ensure you have PostgreSQL installed and running on your system.

1. Update your `config/database.yml` if needed:

   ```yaml
   default: &default
     adapter: postgresql
     encoding: unicode
     pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
     username: <%= ENV.fetch("POSTGRES_USER") { "your_username" } %>
     password: <%= ENV.fetch("POSTGRES_PASSWORD") { "your_password" } %>
     host: <%= ENV.fetch("POSTGRES_HOST") { "localhost" } %>

   development:
     <<: *default
     database: my_project_name_development

   test:
     <<: *default
     database: my_project_name_test
   ```
