# Career Crawler 

A powerful job search application built with Streamlit that scrapes job listings from multiple platforms including Indeed, LinkedIn, ZipRecruiter, Glassdoor, and Google Jobs.

## Features 

- Multi-platform job search across major job sites
- Customizable search parameters
- Remote job filtering
- CSV export functionality
- User-friendly interface
- Real-time job data scraping

## Tech Stack 

- Python 3.x
- Streamlit
- JobSpy
- Pandas
- CSV

## Installation

1. Clone the repository:
```bash
git clone https://github.com/umer-farooq230/Career-Crawler.git
cd Career-Crawler
```

2. Install required packages:
```bash
pip install streamlit jobspy pandas
```

## Usage 

1. Run the Streamlit app:
```bash
streamlit run careercrawler.py
```

2. Input your search criteria:
   - Job Title (e.g., "Software Engineer")
   - Country (e.g., "United States")
   - Toggle Remote Jobs Only if desired
   - Select how many days old the job postings can be
   - Choose number of jobs to fetch

3. Click "Download CSV" to start the scraping process and download results

## Features Explained 

### Search Parameters
- **Job Title**: The position you're looking for
- **Country**: Location for job search
- **Remote Jobs**: Toggle to filter for remote positions only
- **Days Old**: How recent the job postings should be
- **Number of Jobs**: How many positions to fetch

### Supported Job Sites
- Indeed
- LinkedIn
- ZipRecruiter
- Glassdoor
- Google Jobs

### Output Format
The CSV file includes the following information:
- Site source
- Job title
- Company name
- Posting date
- Job type
- Salary range (min/max)
- Currency
- Job description
- Remote status
- Job URL


## Contributing 

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## Acknowledgments 

- [JobSpy](https://github.com/Bunsly/JobSpy) for providing the job scraping functionality
- Streamlit for the web interface framework

## Contact 📧

Umer Farooq - [GitHub Profile](https://github.com/umer-farooq230)

Project Link: [https://github.com/umer-farooq230/Career-Crawler](https://github.com/umer-farooq230/Career-Crawler)
