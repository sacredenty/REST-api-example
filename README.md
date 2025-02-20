# REST-api-example
This API includes:
Proper HTTP status codes (200, 201, 400, 404, etc.)
JSON responses
Basic error handling
CRUD operations
RESTful routing
Features:
Uses SQL alchemy for db
Includes timestamps for todo creation
Supports title, description, and completion status
Auto-incrementing IDs


Dependencies:
You'll need to install Flask-SQLAlchemy:
bash
pip install flask-sqlalchemy
Database Configuration:
app.config['SQLALCHEMY_DATABASE_URI'] specifies the database location
SQLite will create a todos.db file in the same directory
For production, you might use: 'postgresql://user:password@host:port/dbname'
Model Definition:
The Todo class defines the database table structure
Each attribute is a column with specific data types and constraints
db.Model is inherited to make it a SQLAlchemy model
Database Initialization:
db.create_all() creates the tables based on the models
Must be run within an app context
Database Operations:
Query all: Todo.query.all()
Query by ID: Todo.query.get(id)
Create: db.session.add(object) + db.session.commit()
Update: Modify object attributes + db.session.commit()
Delete: db.session.delete(object) + db.session.commit()
Serialization:
Added todo_to_dict() helper function to convert database objects to JSON-friendly dictionaries
To switch to another database (e.g., PostgreSQL):
Install the appropriate driver (e.g., pip install psycopg2)
Change the database URI in the config
Update any database-specific queries if needed
