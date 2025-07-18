# PostgreSQL Notes Application

A Flask-based note-taking application with tag management, built with PostgreSQL database and SQLAlchemy ORM.

## Features

- **Create Notes**: Add new notes with title, description, and tags
- **Edit Notes**: Modify existing notes and their tags
- **Delete Notes**: Remove notes with confirmation dialog
- **Tag Management**: Create, edit, and delete tags
- **Tag Filtering**: View notes by specific tags
- **Many-to-Many Relationship**: Notes can have multiple tags, tags can be associated with multiple notes
- **Responsive UI**: Bootstrap-styled interface

## Technology Stack

- **Backend**: Flask (Python web framework)
- **Database**: PostgreSQL 15
- **ORM**: SQLAlchemy with Flask-SQLAlchemy
- **Forms**: WTForms with Flask-WTF
- **Frontend**: HTML, Bootstrap CSS
- **Containerization**: Docker & Docker Compose
- **Database Admin**: pgAdmin 4

## Project Structure

```
postgresql/
├── docker-compose.yml          # Docker services configuration
├── requirements.txt           # Python dependencies
├── psunote/                  # Main application directory
│   ├── noteapp.py           # Flask application and routes
│   ├── models.py            # SQLAlchemy database models
│   ├── forms.py             # WTForms form definitions
│   └── templates/           # Jinja2 HTML templates
│       ├── base.html        # Base template
│       ├── index.html       # Home page with notes list
│       ├── notes-create.html # Note creation/editing form
│       ├── tags-view.html   # Tag-specific notes view
│       └── tag-edit.html    # Tag editing form
```

## Prerequisites

- Docker and Docker Compose
- Python 3.10+

## Installation & Setup

### Option 1: Using Docker (Recommended)

1. **Clone the repository**
   ```bash
   git clone https://github.com/jayjiratta/POSTGRESQL-git.git
   cd postgresql
   ```

2. **Start the services**
   ```bash
   docker-compose up -d
   ```

3. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Flask application**
   ```bash
   cd psunote
   python noteapp.py
   ```

### Using the Application

1. **Home Page**: View all notes with their tags and timestamps
2. **Create Note**: Click "Create" button to add new notes
3. **Edit Note**: Click "Edit" button on any note card
4. **Delete Note**: Click "Delete" button with confirmation
5. **View by Tag**: Click on any tag to see all notes with that tag
6. **Manage Tags**: Edit or delete tags from the tag view page

### Tag Input Format
When creating or editing notes, enter tags as comma-separated values:


## API Routes

| Route                | Method    | Description                |
|----------------------|-----------|----------------------------|
| `/`                  | GET       | Home page - list all notes |
| `/notes/create`      | GET, POST | Create new note            |
| `/notes/edit/<id>`   | GET, POST | Edit existing note         |
| `/notes/delete/<id>` | POST      | Delete note                |
| `/tags/<name>`       | GET       | View notes by tag          |
| `/tags/edit/<id>`    | GET, POST | Edit tag name              |
| `/tags/delete/<id>`  | POST      | Delete tag                 |


## Key Files Explained

- **`noteapp.py`**: Main Flask application with all route handlers
- **`models.py`**: SQLAlchemy models for Note and Tag entities
- **`forms.py`**: WTForms for handling form validation and rendering
- **`templates/`**: Jinja2 templates for the web interface