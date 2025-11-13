# 📚 Library Management System

A modern, feature-rich Library Management System built with Django and Python. This system provides a complete solution for managing books, authors, genres, and tracking book borrowings with a beautiful dark-themed user interface.

![Django](https://img.shields.io/badge/Django-4.2.7-green.svg)
![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## ✨ Features

### 🔐 Authentication & Authorization
- **User Registration & Login**: Secure user authentication system
- **Role-Based Access Control**: 
  - **Admins**: Full CRUD operations on all resources
  - **Regular Users**: Browse, search, borrow, and return books
- **Session Management**: Secure login/logout functionality

### 📖 Book Management
- **Complete CRUD Operations**: Create, Read, Update, Delete books (Admin only)
- **Book Content Upload**: Upload PDF/DOC/DOCX/TXT/EPUB files
- **Cover Image Upload**: Upload book cover images with preview
- **Content Access Control**: Users can only view/download content after borrowing
- **Advanced Search**: Search by title, author, ISBN, or description
- **Genre Filtering**: Filter books by genre
- **Status Management**: Automatic status updates (Available/Borrowed/Reserved)

### 👤 Author & Genre Management
- **Author Management**: Add authors with biography and birth date
- **Genre Management**: Organize books by categories
- **Admin-Only Creation**: Only admins can add authors and genres

### 📋 Borrowing System
- **Borrow Books**: Users can borrow available books
- **Return Books**: Easy return functionality
- **Borrowing History**: Track all borrowings (users see only their own)
- **Automatic Updates**: Book availability updates automatically
- **Due Date Tracking**: Track due dates for borrowed books

### 🎨 User Interface
- **Dark Theme**: Beautiful, modern dark-themed interface
- **Animated Background**: Smooth gradient animations
- **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- **Image Previews**: Preview book covers before upload
- **Intuitive Navigation**: Easy-to-use navigation menu

### 🔍 Additional Features
- **Pagination**: Efficient handling of large datasets
- **Form Validation**: Comprehensive client and server-side validation
- **Success/Error Messages**: User-friendly feedback messages
- **Admin Panel**: Full Django admin integration
- **File Management**: Secure file upload and storage

## 🚀 Quick Start

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/library-management-system.git
cd library-management-system
```

2. **Create a virtual environment (Recommended)**
```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On Linux/Mac
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Run migrations**
```bash
python manage.py makemigrations
python manage.py migrate
```

5. **Create a superuser (Admin account)**
```bash
python manage.py createsuperuser
```

6. **Run the development server**
```bash
python manage.py runserver
```

7. **Access the application**
- **Main Website**: http://127.0.0.1:8000/
- **Admin Panel**: http://127.0.0.1:8000/admin/

## 📖 Detailed Setup Guide

For detailed step-by-step instructions, see [GUIDANCE.md](GUIDANCE.md)

## 🎯 Usage Guide

### For Administrators

1. **Login** with your admin credentials
2. **Add Authors**: Go to Authors → Add New Author
3. **Add Genres**: Go to Genres → Add New Genre
4. **Add Books**: 
   - Go to Books → Add New Book
   - Fill in book details
   - Upload cover image (optional)
   - Upload book content file (PDF/DOC/etc.)
   - Set total and available copies
5. **Manage Borrowings**: View all borrowings in the Borrowings section

### For Regular Users

1. **Register**: Create a new account
2. **Login**: Sign in with your credentials
3. **Browse Books**: Search and filter books
4. **Borrow Books**: Click "Borrow" on available books
5. **View/Download Content**: After borrowing, access book content
6. **Return Books**: Return books from "My Borrowings" section

## 📁 Project Structure

```
library-management-system/
├── library/                      # Main Django app
│   ├── migrations/              # Database migrations
│   ├── templates/               # HTML templates
│   │   └── library/
│   │       ├── base.html       # Base template
│   │       ├── home.html        # Home page
│   │       ├── book_*.html      # Book templates
│   │       ├── author_*.html    # Author templates
│   │       ├── genre_*.html     # Genre templates
│   │       ├── borrowing_*.html # Borrowing templates
│   │       ├── login.html       # Login page
│   │       └── register.html    # Registration page
│   ├── models.py               # Database models
│   ├── views.py                # View functions
│   ├── urls.py                 # URL routing
│   ├── forms.py                # Form definitions
│   └── admin.py                # Admin configuration
├── library_project/            # Django project settings
│   ├── settings.py             # Project settings
│   ├── urls.py                 # Main URL configuration
│   └── wsgi.py                 # WSGI configuration
├── static/                     # Static files
│   └── css/
│       └── style.css           # Main stylesheet
├── media/                      # User-uploaded files
│   ├── book_covers/           # Book cover images
│   └── book_content/          # Book content files (PDFs, etc.)
├── manage.py                   # Django management script
├── requirements.txt            # Python dependencies
├── README.md                   # This file
└── GUIDANCE.md                 # Detailed setup guide
```

## 🗄️ Database Models

- **Book**: Stores book information (title, author, genre, copies, cover image, content file)
- **Author**: Author details (name, bio, birth date)
- **Genre**: Book genres/categories
- **Borrowing**: Tracks book borrowings and returns

## 🛠️ Technologies Used

- **Backend**: Django 4.2.7
- **Frontend**: HTML5, CSS3, JavaScript
- **Database**: SQLite (default, can be changed to PostgreSQL/MySQL)
- **Image Processing**: Pillow 10.1.0
- **Python**: 3.8+

## 🔒 Security Features

- **Authentication Required**: Login required for borrowing and content access
- **Borrowing Verification**: Users can only access content of borrowed books
- **Admin Protection**: CRUD operations restricted to admin users
- **CSRF Protection**: Django's built-in CSRF protection
- **Secure File Uploads**: Validated file types and sizes

## 📸 Features Showcase

### Key Features:
- ✅ User authentication (Register/Login/Logout)
- ✅ Role-based access control (Admin/User)
- ✅ Book management with images and content files
- ✅ Author and genre management
- ✅ Borrowing and return system
- ✅ Content access control (borrow required)
- ✅ Advanced search and filtering
- ✅ Responsive dark-themed UI
- ✅ Image preview functionality
- ✅ Pagination for large datasets
- ✅ Form validation and error handling

## 🐛 Troubleshooting

### Common Issues

**Issue**: Static files not loading
- **Solution**: Ensure you're running the server from the project root directory

**Issue**: Images/files not uploading
- **Solution**: Check that `media/` directory exists and has proper permissions

**Issue**: Database errors
- **Solution**: Delete `db.sqlite3` and run `python manage.py migrate` again

**Issue**: Permission denied errors
- **Solution**: Ensure you're logged in as admin for CRUD operations

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is created for educational purposes. Feel free to use and modify as needed.

## 👨‍💻 Author

Created as a college project demonstrating Django web development skills.

## 🙏 Acknowledgments

- Django Framework
- Python Community
- All contributors and users

## 📞 Support

For issues, questions, or contributions, please open an issue on GitHub.

---

**Made with ❤️ using Django and Python**
#   l i b r a r y - m a n a g m e n t  
 #   l i b r a r y _ m a n a g m e n t  
 