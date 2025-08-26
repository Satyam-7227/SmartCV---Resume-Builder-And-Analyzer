# SmartCV - Resume Builder And Analyzer

**Group Project - 4th Semester**  
*Developed by: Satyam Patel, Vedant Patel, Smit Kadia, Parth Shah, DhruvrajSinh Zala*

An intelligent full-stack web application that combines AI-powered resume analysis, ATS optimization, and career guidance. Built with Django backend and React frontend, featuring machine learning models for resume scoring and job role prediction.

## 🚀 Features

### Core Functionality
- **Resume Analysis & ATS Scoring** - ML-powered evaluation of resume compatibility with Applicant Tracking Systems
- **Skill Matching** - Intelligent comparison of resume skills with job descriptions using fuzzy matching algorithms
- **Job Role Prediction** - Machine learning model that predicts suitable job roles based on user skills
- **Professional Resume Builder** - Create polished resumes with multiple layout options and real-time preview
- **Career Path Recommendations** - AI-driven suggestions for career advancement based on skill analysis
- **Comprehensive Analytics Dashboard** - Track your progress, ATS scores, and career development metrics

### Advanced Features
- **User Authentication & History** - Secure login system with activity tracking
- **Resume Draft Management** - Save and edit resume drafts with version control
- **Admin Panel** - User management and system analytics for administrators
- **Real-time Processing** - Fast PDF parsing and analysis using advanced NLP techniques
- **Responsive Design** - Modern, mobile-friendly interface built with React

## 👥 Team Members

This project was developed as a group project during the 4th semester by:

- **Satyam Patel** - [GitHub Profile](https://github.com/Satyam-7227)
- **Vedant Patel** - [GitHub Profile](https://github.com/VedantPatel24)
- **Smit Kadia** - [GitHub Profile](https://github.com/smit-kadia)
- **Parth Shah** - [GitHub Profile](https://github.com/parth-shah)
- **DhruvrajSinh Zala** - [GitHub Profile](https://github.com/DhruvrajSinhZala24)

**Academic Year:** 4th Semester  
**Project Type:** Group Project

> 💡 **Note:** This is a collaborative group project. Each team member contributed significantly to different aspects of the application.

## 🛠️ Tech Stack

### Backend
- **Framework**: Django 5.2.4 + Django REST Framework
- **Database**: SQLite (development), PostgreSQL ready (production)
- **Authentication**: JWT-based authentication system
- **ML Libraries**: Scikit-learn, spaCy, NumPy, Pandas
- **PDF Processing**: PyPDF2, ReportLab
- **API**: RESTful API with CORS support

### Frontend
- **Framework**: React 19.1.0 with modern hooks
- **Routing**: React Router DOM
- **Styling**: Custom CSS with responsive design
- **Charts**: Chart.js with React integration
- **Icons**: Lucide React for modern iconography
- **HTTP Client**: Axios for API communication

### Machine Learning
- **ATS Scoring Model**: Random Forest Regressor for resume evaluation
- **Job Prediction Model**: Naive Bayes classifier for role prediction
- **NLP Processing**: spaCy for entity extraction and text analysis
- **Feature Engineering**: Custom algorithms for skill matching and scoring

## 📁 Project Structure

```
Group_Resume_Django/
├── backend/                 # Django backend application
│   ├── groupresume/        # Django project settings
│   ├── resumebackend/      # Main Django app
│   ├── ML/                 # Machine learning models and training
│   │   ├── ATS_Score/      # ATS scoring model
│   │   └── Job_Prediction/ # Job role prediction model
│   ├── manage.py           # Django management script
│   └── requirements.txt    # Python dependencies
├── frontend/               # React frontend application
│   ├── src/               # Source code
│   │   ├── components/    # React components
│   │   ├── css/          # Stylesheets
│   │   └── App.js        # Main application
│   ├── package.json      # Node.js dependencies
│   └── public/           # Static assets
└── README.md             # This file
```

## 🚀 Getting Started

### Prerequisites
- Python 3.11+
- Node.js 18+
- npm or yarn

### Backend Setup

1. **Navigate to backend directory**
   ```bash
   cd backend
   ```

2. **Create virtual environment**
   ```bash
   python -m venv venv
   ```

3. **Activate virtual environment**
   - Windows: `venv\Scripts\activate`
   - macOS/Linux: `source venv/bin/activate`

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Install spaCy model**
   ```bash
   python -m spacy download en_core_web_sm
   ```

6. **Run migrations**
   ```bash
   python manage.py migrate
   ```

7. **Create superuser (optional)**
   ```bash
   python manage.py createsuperuser
   ```

8. **Start Django server**
   ```bash
   python manage.py runserver
   ```

### Frontend Setup

1. **Navigate to frontend directory**
   ```bash
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm start
   ```

4. **Build for production**
   ```bash
   npm run build
   ```

## 🔧 Configuration

### Environment Variables
Create a `.env` file in the backend directory:

```env
SECRET_KEY=your-secret-key-here
DEBUG=True
ALLOWED_HOSTS=localhost,127.0.0.1
CORS_ALLOWED_ORIGINS=http://localhost:3000
```

### Database Configuration
The project uses SQLite by default. For production, update `settings.py`:

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_db_name',
        'USER': 'your_db_user',
        'PASSWORD': 'your_db_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

## 📊 API Endpoints

### Authentication
- `POST /api/register/` - User registration
- `POST /api/login/` - User login
- `POST /api/logout/` - User logout

### Resume Analysis
- `POST /api/analyze-resume/` - Analyze resume and get ATS score
- `GET /api/history/` - Get user's analysis history
- `DELETE /api/history/<id>/` - Delete history entry

### Resume Builder
- `POST /api/build-resume/` - Generate resume from form data
- `POST /api/save-draft/` - Save resume draft
- `GET /api/list-drafts/` - List user's drafts
- `GET /api/get-draft/<id>/` - Get specific draft

### Career Guidance
- `POST /api/get-career-paths/` - Get career path recommendations
- `POST /api/get-job-details/` - Get job details for predicted role

### Admin (Admin users only)
- `GET /api/admin/dashboard/` - Admin dashboard data
- `GET /api/admin/users/` - List all users

## 🤖 Machine Learning Models

### ATS Scoring Model
- **Algorithm**: Random Forest Regressor
- **Features**: Skill count, education, experience, company count, project count, text length
- **Training Data**: Custom dataset with annotated resume features
- **Output**: Score from 0-100 indicating ATS compatibility

### Job Role Prediction Model
- **Algorithm**: Multinomial Naive Bayes
- **Features**: Skill-based text vectorization
- **Training Data**: Job skills dataset with role mappings
- **Output**: Predicted job role based on user skills

## 🎯 Usage Examples

### Resume Analysis
1. Upload your resume PDF
2. Provide job description (optional)
3. Get ATS score and skill analysis
4. Receive improvement suggestions

### Resume Building
1. Fill out the resume form
2. Choose from multiple layouts
3. Preview in real-time
4. Download as PDF

### Career Guidance
1. Analyze your skills
2. Get career path recommendations
3. View matching job opportunities
4. Track your progress over time

## 🔒 Security Features

- JWT-based authentication
- CORS protection
- Input validation and sanitization
- Secure file upload handling
- Admin-only endpoints protection

## 🚀 Deployment

### Backend Deployment
1. Set `DEBUG=False` in production
2. Use production database (PostgreSQL recommended)
3. Configure static files serving
4. Set up proper CORS origins
5. Use environment variables for secrets

### Frontend Deployment
1. Build the production bundle: `npm run build`
2. Serve static files from a web server
3. Configure API endpoint URLs
4. Set up HTTPS in production

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Django and React communities for excellent frameworks
- Scikit-learn and spaCy for ML capabilities
- Contributors and testers who helped improve the system

## 📞 Support

For support and questions:
- Create an issue in the GitHub repository
- Check the documentation in the codebase
- Review the API endpoints for integration help

---

**SmartCV** - Empowering your career with intelligent resume analysis and guidance.
