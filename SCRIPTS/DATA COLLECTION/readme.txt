
Pre-requisite:
* Create a CSV file containing the CVEs (that you want to collect data for) and their NVD disclosure date.

The Data collection is performed in two steps:

- Collecting all the Issues,PRs and Commits from the NVD References ---> LEVEL 1. 
* Step 1: Create a data mapping between the CVE ID and the list of references.
	** In the three folders, issue_mappings, commit_mappings and pr_mappings, create a CSV file for each CVE listing the issue_links, commit_links and pr_links respectively.  (Sample data is provided for a reference)
* Step 2: Run the script ./Level_1_data_collection/collect_github_artifacts_level_1.py
	** Change the value of the MAIN_FOLDER_VALUE which indicates the root folder wherein the DATA is saved. Ensure you have the following folder structure.
	-- DATA
		-- ISSUE
		-- PR
		-- COMMIT
* Step 3: Run the script get_pr_commits.py which downloads the commits associated with each PR and stores in ./DATA/PR/PR_COMMIT/.

- Collecting all the Issues, PRS and Commits which are referenced & hyperlinked by the LEVEL 1 artifacts ---> LEVEL 2.
* Collecting the Referenced Artifacts (Scripts at ./Level_2_data_collection/)
	** Collecting the issues referenced by issues/prs. - Run the execute_i_pr_download_referred_i.py
	** Collecting the prs referenced by issues/prs. - Run the execute_i_pr_download_referred_pr.py

	** Collecting the commits referenced by issues - Run the execute_c_download_referred_i.py
	** Collecting the commits referenced by prs - Run the execute_c_download_referred_pr.py

* Collecting the Hyperlinked Artifacts
	** Collecting the issues hyperlinked in the text components of  other issues/prs/commits - Run the i_download_hyperlinked_artifact.py
	** Collecting the prs hyperlinked in the text components of  other issues/prs/commits - Run the pr_download_hyperlinked_artifact.py
	** Collecting the commits hyperlinked in the text components of  other issues/prs/commits - Run the c_download_hyperlinked_artifact.py

At the end of the data collection process, the next steps would expect three folders to be created: DATA (containing vulnerable artifacts), NON_VULN_DATA (containing the associated non-vulnerable artifacts) and GITHUB_ARCHIVE_DATA. Please copy the folder paths for these three folders. 


For an easy replication process, we have included the data collected (Archive.zip -> DATA dir) and (NV_Archive.zip -> NV_DATA dir). The GitHub archive files are also included in the GH_ARCHIVE.ZIP
