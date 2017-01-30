

* READ FIRST!
* Introduction
  * Kazoo explained
  * Getting started
  * History
* Preparation
  * Archetecture
  * Requirements
* Components
  * FreeSWITCH
  * Kamailio
  * RabbitMQ
  * HAProxy
  * Kazoo Core
  * Kazoo Applications
  * Monster UI Core
  * Monster UI Applications
  * Bigcouch
* Installation
  * via CentOS 7
  * via RPM
  * via ISO
  * via source
* General Configuration
  * Quick Start
  * DNS
  * Networking
  * ACLs
* Interfaces
  * UI (Monster UI)
  * HTTP Websockets (blackhole)
  * HTTP APIs (crossbar)
  * Webhooks (webhooks)
  * Command Line (SUP)
  * Direct Database Access
* SSL
  * Quick Start
  * HTTP APIs
  * HTTP Websockets
  * SIP TLS
  * WebRTC Websockets
* Numbers and Routing
  * Overview
  * Kazoo Number Manager
  * Carrier Intergrations (kazoo_number_manager/carriers)
  * Number Features (kazoo_number_manager/providers)
  * Resources (stepswitch)
* Account Management
  * Overview
  * Account hiearchy
  * Best Practices
  * Reseller Accounts
* Voice/Video/Message Processing
  * Overview
  * PBX Features (callflow)
  * Conferencing (conference)
  * Realtime Call Control (pivot)
  * Wholesale SIP Service (trunkstore)
  * SMS Features (doodle)
* Fax
  * Overview
  * Fax Application
  * Fax to Email
  * Email to Fax
  * Fax over IP
  * Advanced Integrations
  * Best Practices
* Whitelabeling
  * DNS
  * Emails
* Billing and Rating
  * Overview
  * Rating (hotornot)
  * Limiting (jonny5)
  * Service Plans (kazoo_services)
  * Transactions (kazoo_services/bookkeepers)
  * Ledgers (kazoo_ledgers -> per_minute, ect)
* CDRs
  * Overview
  * Channels vs Calls
  * Analyzing CDRs
  * Storing CDRs (cdr)
  * Call Health Monitoring (hangups)
* Data Storage
  * Overview
  * Bigcouch / CouchDB 2.0
  * Database Structure (account, modb, system, ect)
  * Data Plans
  * Third-party Storage
  * Compaction
  * Best Practices
* Prompts and Media
  * Streamed Prompts (system_media, media_mgr)
  * Local Prompts (freeswitch prompts)
  * Text to Speech
  * Hold Music
* Security
  * Overview
  * SSO
  * Multi-factor Authentication
  * Token Buckets
  * Fraud Prevention
  * Best Practices
* Opertaions
  * SUP
  * milliwatt
  * tasks
* Additional Considerations:
  * Door Bells

	notify
	teletype



Community Applications:
	acdc
	camper
	cccp
	konami
	spyvsspy
	frontier
call_instpector
stats

Cluster Operation:
	Security






	billing_and_rating:
hotornot
jonny5
