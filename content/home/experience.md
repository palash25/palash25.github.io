
+++
# Experience widget.
widget = "experience"  # See https://sourcethemes.com/academic/docs/page-builder/
headless = true  # This file represents a page section.
active = true  # Activate this widget? true/false
weight = 40  # Order that this section will appear.

title = "Experience"
subtitle = ""

# Date format for experience
#   Refer to https://sourcethemes.com/academic/docs/customization/#date-format
date_format = "Jan 2006"

# Experiences.
#   Add/remove as many `[[experience]]` blocks below as you like.
#   Required fields are `title`, `company`, and `date_start`.
#   Leave `date_end` empty if it's your current employer.
#   Begin/end multi-line descriptions with 3 quotes `"""`.
[[experience]]
  title = "Intern"
  company = "Cloud Native Computing Foundation"
  company_url = "https://cncf.io"
  location = "Remote"
  date_start = "2019-07-15"
  date_end = "2019-08-09"
  description = """
  Work Highlights:

  * Wrote a coredns plugin to serve dns records from Google Cloud DNS

  Keywords: Go
  """

[[experience]]
  title = "SDE Intern"
  company = "Hackerrank"
  company_url = "https://hackerrank.com"
  location = "Bengaluru, India"
  date_start = "2020-01-06"
  date_end = "2020-05-30"
  description = """
* Git skills (a git analytics dashboard to help provide CTOs and engineering management insights into the org's developer skills)
  - Wrote the git analysis engine in Go from scratch.
  - Worked on the rails backend for the web app
  - Designed the elasticsearch schema

* CodeRunner (Hackerrank's code exection service written in Go)
  - Reduced the compile time for Rust submissions from 20s to 0.52s by reusing build artifacts across submissions

  Tech Stack: Go, Ruby on Rails, Elasticsearch
  """

[[experience]]
  title = "Backend Engineering Intern"
  company = "Atlan"
  company_url = "https://atlan.com"
  location = "New Delhi, India"
  date_start = "2019-05-13"
  date_end = "2019-07-13"
  description = """
  Worked on a data collection tool called Collect which is used by hundreds of organizations across 50 countries.

  Work Highlights:

  * Rewrote the analytics API for collect in Go.
  * Deployed the analytics API on GCP.
  * Ported some parts of the NodeJS monolith to Go.
  * Did a POC on adding full-text search capabilities to collect backend leveraging Elasticsearch.
  * Did a POC on improving the Elasticsearch cluster topology for collect.

  Keywords: Go, Python, Elasticsearch
  """

[[experience]]
  title = "Software Engineering Intern"
  company = "Appbase"
  company_url = "https://appbase.io"
  location = "Remote"
  date_start = "2018-09-13"
  date_end = "2019-07-13"
  description = """
  Working on the following products:

  * [abc](https://github.com/appbaseio/abc/): A data ingestion pipeline and CLI tool.
  * [Arc](https://github.com/appbaseio/arc): an Elasticsearch API gateway.

  Work Highlights:

  * Wrote unit/integration tests for the various plugins in https://github.com/appbaseio/arc
  * Wrote a Redis adaptor to transport data from a Redis database and index it onto elasticsearch as a selection task for the internship.
  * Added gitlab login support for appbase.io to the CLI tool
  * Wrote an analytics switch for the CLI tool that displays analytics data for a particular app
  * Added support for cluster management to the CLI tool.
  * Wrote a homebrew formula for abc

  Keywords: Go, Redis, Elasticsearch, Ruby
  """

  [[experience]]
  title = "Google Summer of Code Student"
  company = "coala"
  company_url = "https://coala.io"
  location = "Remote"
  date_start = "2018-05-13"
  date_end = "2018-08-13"
  description = """
  Worked on coala's [core repo](https://github.com/coala/coala) with a special focus on caching, I/O & the NextGen-Core. The following features were implemented during GSoC:

  * Improved coala's I/O mechanism by implementing ``FileFactory`` class. An abstraction layer to interface with file content instead of dealing with actual files. This way files are now lazy loaded thereby improving the performance.

  * Implemented ``Directory`` class which provides details about a project's sub-directories. This feature can later be used to enhance the NextGen caching by implementing an `Ignore Directories Functionality`.

  * Provided support for unordered collection types (e.g. ``sets`` and ``dicts``) in ``PersistentHash`` module enhancing coala's NextGen-Core's ability to deal with complex task objects by pickling and hashing them to generate unique hashes for every task objects which increases the accuracy of the caching mechanism.

  * Further improved performance by caching the properties provided by ``FileFactory`` by memoizing the function calls.

  * Integrated ``FileFactory`` by writing a middleware called ``FileDict``. The middleware mimics a dictionary and keeps the contents of the file-dict same (providing support for future integration with the NextGen-Core) but also provide the core with the actual file contents (using the file access properties provided by ``FileFactory``) instead of the ``FileFactory`` objects on get calls (thereby maintaining backwards compatibility with the old core).

  * Wrote the documentation for the aforementioned features.

  Keywords: Python

  [Project link on the GSoC site](https://summerofcode.withgoogle.com/projects/#6434190552203264)
  [Final GSoC Report](https://projects.coala.io/GSoC/2018/StatusReport/palash25)
  """

+++
