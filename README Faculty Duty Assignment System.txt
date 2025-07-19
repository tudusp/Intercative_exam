# Faculty Duty Assignment System

A comprehensive web application for managing faculty duty assignments during examination periods. Built with React frontend and FastAPI backend, featuring advanced report generation and duty management capabilities.

## 🚀 Features

- **Faculty Management**: Upload and manage faculty data with contact information
- **Exam Configuration**: Configure exam type, semester, year, department, and institute
- **Exam Schedule Management**: Add and manage examination dates and required faculty counts
- **Duty Assignment**: Automatic generation of duty assignments based on faculty availability
- **Faculty Grouping**: Group faculty members to be assigned together
- **Unavailability Management**: Mark faculty as unavailable for specific dates/shifts
- **Manual Intervention**: Manually adjust assignments and override automatic assignments
- **Advanced Reports**: Generate professional Word and Excel reports with contact information
- **Regeneration from Summary**: Upload edited Excel summaries to regenerate assignments

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Node.js** (v14 or higher)
- **Python** (v3.8 or higher)
- **pip** (Python package manager)

## 🛠️ Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd faculty-duty-frontend
```

### 2. Install Frontend Dependencies
```bash
npm install
```

### 3. Install Backend Dependencies
```bash
pip install fastapi uvicorn pandas openpyxl python-docx python-multipart
```

## 🚀 How to Start the Application

### Step 1: Start the Backend Server
Open a terminal/command prompt and run:
```bash
python faculty_duty_app.py
```

You should see output like:
```
INFO:     Started server process [xxxxx]
INFO:     Waiting for application startup.
INFO:     Application startup complete.
INFO:     Uvicorn running on http://0.0.0.0:8000 (Press CTRL+C to quit)
```

### Step 2: Start the Frontend Application
Open another terminal/command prompt and run:
```bash
npm start
```

The React application will start and automatically open in your browser at `http://localhost:3000`

## 📖 How to Use the Application

### 1. Faculty Management

#### Configure Exam Settings
1. Navigate to **Faculty Management** section
2. In the **Exam Configuration** card at the top:
   - Select **Exam Type** (MID SEM, END SEM, QUIZ, LAB)
   - Choose **Semester** (MO, SP, MAKE UP, SUMMER)
   - Enter **Year** (e.g., 2025)
   - Set **Department** name
   - Set **Institute** name
   - Click **Save Config**

#### Upload Faculty Data
1. Click **Upload CSV/Excel** button
2. Select your faculty data file (CSV or Excel format)
3. The file should contain columns: `faculty`, `Phone No`, `Email Id`, `Designation`, `Max Duties`
4. Faculty list will be displayed in an expandable table

#### Faculty Grouping
1. In the **Faculty Grouping** section:
   - Select multiple faculty members from the dropdown
   - Click **Add Group** to create a group
   - Groups will be assigned together during duty generation
   - Use the delete icon to remove groups

#### Faculty Unavailability
1. In the **Faculty Unavailability** section:
   - For each faculty member, check/uncheck dates and shifts
   - Mark faculty as unavailable for specific dates and shifts
   - Changes are automatically saved

### 2. Exam Schedule Management

1. Navigate to **Exam Schedule** section
2. Add examination dates:
   - Enter **Date** (YYYY-MM-DD format)
   - Set **First Half** faculty count required
   - Set **Second Half** faculty count required
   - Click **Add Date**
3. Use the delete icon to remove dates

### 3. Duty Assignment

1. Navigate to **Duty Assignment** section
2. Click **Generate Assignments** button
3. The system will automatically assign faculty based on:
   - Available faculty members
   - Faculty groups (assigned together)
   - Unavailability settings
   - Required faculty counts per shift

### 4. Manual Intervention

1. Navigate to **Manual Intervention** section
2. View current assignments in a table format
3. Modify assignments as needed:
   - Change faculty assignments
   - Add/remove assignments
   - Adjust duty counts
4. Changes are automatically saved

### 5. Reports & Downloads

#### Download Reports
1. Navigate to **Reports & Downloads** section
2. Click **Download Excel Report** to get a comprehensive faculty summary
3. Click **Download Word Report** to get a professional formatted document

#### Regenerate from Summary
1. Download the Excel report
2. Edit the Excel file manually (modify dates, faculty assignments, etc.)
3. In the **Regenerate Duty from Edited Summary** section:
   - Click **Upload Edited Summary**
   - Select your modified Excel file
   - Click **Regenerate Assignments**
4. The system will create new assignments based on your edits

## 📁 File Structure

```
faculty-duty-frontend/
├── src/
│   ├── App.js                 # Main application component
│   ├── FacultyManagement.js   # Faculty management interface
│   ├── ExamSchedule.js        # Exam schedule management
│   ├── DutyAssignment.js      # Duty assignment generation
│   ├── ManualIntervention.js  # Manual assignment editing
│   ├── ReportsDownloads.js    # Report generation and downloads
│   └── api.js                 # API utility functions
├── faculty_duty_app.py        # FastAPI backend server
├── faculty_upload.csv         # Faculty data storage
├── exam_schedule.json         # Exam schedule storage
├── assignments.json           # Generated assignments
├── faculty_groups.json        # Faculty groups storage
├── faculty_unavailability.json # Unavailability settings
└── exam_config.json          # Exam configuration
```

## 🔧 Configuration Files

The application uses several JSON files to store data:

- **faculty_upload.csv**: Faculty member data with contact information
- **exam_schedule.json**: Examination dates and required faculty counts
- **assignments.json**: Generated duty assignments
- **faculty_groups.json**: Faculty grouping information
- **faculty_unavailability.json**: Faculty unavailability settings
- **exam_config.json**: Exam configuration (type, semester, year, etc.)

## 📊 Report Formats

### Excel Report
- Faculty summary with contact information
- Duty counts (First Half, Second Half, Total)
- Assignment dates for each shift
- Unavailability information
- Professional formatting with auto-sized columns

### Word Report
- Professional document with institutional header
- Formatted tables for each examination date
- Faculty contact information (Phone, Email)
- Department and institute information
- Notes and signature section

## 🐛 Troubleshooting

### Common Issues

1. **Backend not starting**:
   - Check if Python and required packages are installed
   - Ensure port 8000 is not in use
   - Check for syntax errors in `faculty_duty_app.py`

2. **Frontend not connecting to backend**:
   - Ensure backend is running on `http://localhost:8000`
   - Check browser console for CORS errors
   - Verify network connectivity

3. **File upload issues**:
   - Ensure file format is correct (CSV or Excel)
   - Check file size (should be reasonable)
   - Verify file permissions

4. **Report generation fails**:
   - Ensure faculty data is uploaded
   - Check if assignments are generated
   - Verify exam configuration is set

### Error Messages

- **"Failed to upload faculty"**: Check file format and content
- **"No assignments found"**: Generate assignments first
- **"Failed to generate report"**: Check data completeness
- **"Missing required columns"**: Verify Excel file structure

## 🔄 Data Flow

1. **Setup**: Upload faculty data and configure exam settings
2. **Planning**: Add exam schedule and set unavailability
3. **Generation**: Create automatic duty assignments
4. **Refinement**: Use manual intervention for adjustments
5. **Reporting**: Generate and download professional reports
6. **Iteration**: Upload edited summaries to regenerate assignments

## 📝 Notes

- All data is stored locally in JSON/CSV files
- Changes are automatically saved
- The system supports both CSV and Excel file formats
- Reports include faculty contact information when available
- Faculty groups ensure members are assigned together
- Unavailability settings prevent conflicts

## 🤝 Contributing

To contribute to this project:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

---

**For support or questions, please refer to the troubleshooting section or create an issue in the repository.**
