# Resume_Generator_OpenAI
A Python application that automatically generates professional, one-page resumes in DOCX format using OpenAI's GPT models. Simply provide a job title, industry, and seniority level, and the AI will create a tailored resume with realistic experience and skills.
## What This Program Does

This tool creates professional resumes by:
- Taking your input (job title, industry, seniority level)
- Using OpenAI's AI to generate realistic resume content
- Formatting everything into a clean, two-column DOCX document
- Saving the resume with a timestamp for easy organization

## Features

- **AI-Powered Content**: Uses GPT models to generate relevant experience and skills
- **Professional Layout**: Clean two-column format optimized for one page
- **Customizable**: Configure your name, target seniority, and industry context
- **Multiple Resumes**: Generate as many different resumes as you need
- **Automatic Formatting**: Consistent fonts, spacing, and bullet points

## Prerequisites (What You Need Before Starting)

### 1. Python Installation
You need Python 3.7 or higher installed on your computer.

**Check if Python is installed:**
```bash
python --version
```

**If you don't have Python:**
- Windows: Download from [python.org](https://www.python.org/downloads/)
- Mac: Use Homebrew (`brew install python`) or download from python.org
- Linux: Use your package manager (`sudo apt install python3` on Ubuntu)

### 2. OpenAI API Key
You need an OpenAI account and API key to use this program.

**Get your API key:**
1. Go to [OpenAI's website](https://openai.com/)
2. Sign up for an account (if you don't have one)
3. Navigate to the API section
4. Generate a new API key
5. Copy and save this key securely

**Important:** The API key costs money to use, but generating resumes typically costs less than $0.10 each.

## Installation Guide

### Step 1: Download the Project
```bash
# If you have git installed
git clone <repository-url>
cd <project-folder>

# Or download the ZIP file and extract it
```

### Step 2: Create a Virtual Environment (Recommended)
A virtual environment keeps this project's dependencies separate from other Python projects.

```bash
# Create virtual environment
python -m venv .venv

# Activate it
# On Windows:
.venv\Scripts\activate
# On Mac/Linux:
source .venv/bin/activate
```

### Step 3: Install Required Packages
```bash
pip install -r requirements.txt
```

This installs:
- `openai`: For communicating with OpenAI's API
- `python-docx`: For creating Word documents
- `python-dotenv`: For managing environment variables

### Step 4: Set Up Your Configuration
Create a file called `.env` in the project folder with your settings:

```bash
# Copy this template and fill in your information
OPENAI_API_KEY=your_api_key_here
OPENAI_MODEL=gpt-4o-mini
CANDIDATE_NAME=Your Full Name
TARGET_SENIORITY=Senior
INDUSTRY_CONTEXT=AI engineering for medical software
```

**Configuration Options:**
- `OPENAI_API_KEY`: Your OpenAI API key (required)
- `OPENAI_MODEL`: Which AI model to use (gpt-4o-mini is cheaper, gpt-4 is more advanced)
- `CANDIDATE_NAME`: The name that will appear on your resume
- `TARGET_SENIORITY`: Default seniority level (Junior, Mid-level, Senior, etc.)
- `INDUSTRY_CONTEXT`: Default industry context for generating relevant experience

## How to Use

### Basic Usage
1. Open your terminal/command prompt
2. Navigate to the project folder
3. Activate your virtual environment (if using one)
4. Run the program:

```bash
python main.py
```

### Interactive Process
The program will ask you three questions:

1. **Target job title**: What job are you applying for?
   - Example: "Software Engineer", "Data Scientist", "Product Manager"

2. **Industry**: What industry is the job in?
   - Example: "Healthcare", "Finance", "E-commerce", "Gaming"

3. **Seniority level**: What level position?
   - Example: "Junior", "Mid-level", "Senior", "Lead", "Principal"

### Example Session
```
Enter target job title: Frontend Developer
Enter industry: E-commerce
Enter seniority level: Mid-level
Generating content...
Creating document...
✓ Saved: resume_20250917_143930.docx

Generate another? (y/n): n
```

## Understanding the Output

The program creates a DOCX file with these sections:
- **Career Overview**: Brief summary of your career trajectory
- **Summary Profile**: Professional summary highlighting key strengths
- **Core Technical Competencies**: Main technical skills
- **Work Experience**: Realistic job history with achievements
- **Academic History**: Educational background
- **Contact Information**: Professional contact details
- **Professional Development**: Certifications and training
- **Technical Skills Matrix**: Detailed technical skills breakdown

Each section contains exactly 3 bullet points for consistency and readability.

## File Structure
```
project-folder/
├── main.py              # Main program file
├── requirements.txt     # Python dependencies
├── .env                # Your configuration (create this)
├── README.md           # This file
└── resume_*.docx       # Generated resume files
```

## Troubleshooting

### Common Issues

**"Missing OPENAI_API_KEY in .env"**
- Make sure you created the `.env` file
- Check that your API key is correctly entered
- Ensure there are no extra spaces around the key

**"Connection error"**
- Check your internet connection
- Verify your API key is valid and has credits
- Try again in a few minutes (API might be temporarily busy)

**"Parse failed"**
- This usually resolves by running the program again
- The AI occasionally returns malformed data, but retry logic handles this

**"Permission denied" when saving**
- Make sure you have write permissions in the folder
- Close any open DOCX files with the same name

### Getting Help

If you encounter issues:
1. Check that all prerequisites are installed
2. Verify your `.env` file is configured correctly
3. Make sure you have internet connection
4. Try running with a simpler job title first

## Customization Options

### Changing the Resume Format
The resume layout is defined in the `make_docx()` function. You can modify:
- Font styles and sizes
- Margins and spacing
- Number of columns
- Section order

### Adding New Sections
To add new resume sections:
1. Add the section name to the `SECTIONS` list
2. The AI will automatically generate content for it
3. The DOCX formatter will include it in the output

### Using Different AI Models
Change the `OPENAI_MODEL` in your `.env` file:
- `gpt-4o-mini`: Faster and cheaper
- `gpt-4`: More sophisticated but more expensive
- `gpt-3.5-turbo`: Older but very cost-effective

## Cost Information

Typical costs per resume generation:
- GPT-4o-mini: ~$0.02-0.05
- GPT-4: ~$0.10-0.20
- GPT-3.5-turbo: ~$0.01-0.03

Costs depend on the complexity of your requirements and current OpenAI pricing.

## Tips for Best Results

1. **Be Specific**: Use detailed job titles like "Senior React Developer" instead of just "Developer"
2. **Match Industry**: Use the same industry terminology as the job posting
3. **Appropriate Seniority**: Match the level you're actually qualified for
4. **Review Output**: Always review and customize the generated resume before using it
5. **Multiple Versions**: Generate different versions for different types of roles

## Security Notes

- Never share your `.env` file or API key
- Add `.env` to your `.gitignore` if using version control
- Regularly rotate your API keys for security
- Be mindful that resume content is sent to OpenAI's servers

## License

This project is for educational and personal use. Please respect OpenAI's terms of service when using their API.
