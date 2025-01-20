import csv
from jobspy import scrape_jobs
import pandas as pd
import streamlit as st


st.title("Job Scraper App")
st.markdown("Search for jobs across multiple platforms and download them as a CSV file.")

# Inputs
search_term = st.text_input(label=" Job Title:", placeholder="e.g., Software Engineer")
country = st.text_input(label=" Country:", placeholder="e.g., United States")
is_remote = st.checkbox(" Remote Jobs Only", value=False)
hours = st.number_input(" Days old:", min_value=0, value=1)
jobs_wanted = st.number_input(" Number of jobs to fetch:", min_value=1, value=10)

if st.button("Download CSV"):
    try:
        # Convert days to hours for jobspy
        hours_old = hours * 24

        # Scraping jobs
        st.info("🔄 Scraping jobs, please wait...")
        jobs = scrape_jobs(
            site_name=["indeed", "linkedin", "zip_recruiter", "glassdoor", "google"],
            search_term=search_term,
            google_search_term=f"{search_term} jobs near {country}",
            results_wanted=jobs_wanted,
            hours_old=hours_old,
            country_indeed=country,
            is_remote=is_remote,
        )

        
        df = pd.DataFrame(jobs)

    
        if df.empty:
            st.warning("⚠️ No jobs found. Try refining your search criteria.")
        else:
            st.success(f"🎉 Found {len(jobs)} jobs!")

            df = df[
                ["site", "title", "company", "date_posted", "job_type", "min_amount", "max_amount", "currency", "description", "is_remote", "job_url"]
            ]
            df = df.fillna("....None given....", axis=1)

            csv_file = df.to_csv(index=False, quoting=csv.QUOTE_NONNUMERIC, escapechar="\\")
            st.download_button(
                label="📥 Download CSV",
                data=csv_file,
                file_name=f"jobs_{search_term.replace(' ', '_')}.csv",
                mime="text/csv",
            )
    except Exception as e:
        st.error(f"❌ An error occurred: {str(e)}")
