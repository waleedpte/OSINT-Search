# OSINT-Search Description
- Script in Python that applies OSINT techniques by searching public data using email addresses, phone numbers, domains, IP addresses or URLs.
- Create an account at https://pipl.com/api and get the API key.
- Create an account at https://www.opencnam.com/ and get the Account SID and Auth Token.
- Create an account at https://www.shodan.io/ and get the Shodan API key.
- Create an account at https://whatcms.org/API and get the WhatCMS API key.
- Create an account at https://censys.io/register and get the API ID and API secret.
- Create an account at https://dashboard.fullcontact.com/consents and get the FullContact API key.
- Create an account at https://www.towerdata.com/email-validation ang get the TowerData API key.

# Functionality

- Presents personal information like full name, age, gender, location, languages, social networks, etc...
- Presents information related to data breaches.
- Presents information related to pastes of data breaches made public.
- Presents which country a phone number belongs to.
- Presents results of google hackings searches.
- Presents results related to a domain or an IP address.
- Presents digital certificates for a certain domain.
- Presents CMS for a certain website.
- Presents DNS Records and zone transfers information for a certain domain.
- Presents URL links that contain valuable data related with a Facebook ID.
- Presents URLs present in some web page.
- Presents URL that tells what torrents are being downloaded from some IP.

The script allows specfic searches and in bulk.

More functionalities to be added later.

# Tested On

- Kubuntu 18.04.2 LTS
- Kali Linux 2019.1
- Windows 10

# Requirements (Install)

- Linux:

  Python3 - https://docs.python-guide.org/starting/install3/linux/#install3-linux

  `sudo apt-get install git`

- Windows:

  Python3 - https://www.python.org/downloads/windows/

  git - https://git-scm.com/download/win

- Both:

  ``` bash
  pip3 install -r requirements.txt
  pip3 install git+https://github.com/abenassi/Google-Search-API --upgrade
  pip3 install https://github.com/PaulSec/API-dnsdumpster.com/archive/master.zip --user
  ```

# Run

- On the first run of the script you need to submit your API fields to get all the functionality of the script. I suggest you create the accounts mentioned in the description.
- A configuration file called 'osintSearch.config.ini' is created with your data and can be edited by you.

# Usage

``` bash
$ osintS34rCh v1.0

USAGES
  Email
  ./osintS34rCh -e <target@email>				# All Searches: Pipl, FullContact, Haveibeenpwnded Data Breaches and Credentials Pastes, TowerData - validate e-mail
  ./osintS34rCh -e <target@email> --pipl 			# Pipl
  ./osintS34rCh -e <target@email> --fullcontact 		# FullContact
  ./osintS34rCh -e <target@email> --pwned 			# Haveibeenpwnded Data Breaches and Credentials Pastes
  ./osintS34rCh -e <target@email> --validate			# TowerData - validate e-mail

  Domain
  ./osintS34rCh.py -t <domain>					# All Searches: Shodan Recon, crt.sh, DNSDumpster, All Google Hacking Dorks, HackerTarget - DNS Zonetransfer
  ./osintS34rCh.py -t <domain> --shodan				# Shodan Recon
  ./osintS34rCh.py -t <domain> --crt 				# crt.sh
  ./osintS34rCh.py -t <domain> --dns 				# DNSDumpster, HackerTarget - DNS Zonetransfer
  ./osintS34rCh.py -t <domain> -d <dork> -n <num_pages>		# Google Hacking
  ./osintS34rCh.py -t <domain> -d --all				# All Google Hacking Dorks

  IP
  ./osintS34rCh.py -t <IP>					# All Searchs: Shodan and Censys Recon
  ./osintS34rCh.py -t <IP> --shodan				# Shodan Recon
  ./osintS34rCh.py -t <IP> --censys				# Censys Recon
  ./osintS34rCh.py -t <IP> --torrent				# KnowWhatYouDownload URL

  URL
  ./osintS34rCh.py -u <url>					# WhatCMS Check, HackerTarget - Extract URLs
  ./osintS34rCh.py -u <url> --cms				# WhatCMS Check
  ./osintS34rCh.py -u <url> --extract				# HackerTarget - Extract URLs
  ./osintS34rCh.py -u <url> --facebook 				# Facebook

  Phone
  ./osintS34rCh.py -p <phonenumber> --callerID			# CallerID

OPTIONS:
  -h or --help
  -e <email> [--pipl] [--fullcontact] [--pwned]
  -t <target IP or Domain> [--shodan] [--crt] [--dns] [-d] [<dork>] [--all] [-n <num_pages>]
  -u [--cms] [--censys] [--extract] [--facebook]
  -p <phone> --callerID

DORKS:
  dir_list
  files
  docs
  db
  login
  sql
  sensitive
  php

CONFIG_FILE:
  /yourdirectory/osintSearch.config.ini
  ```
