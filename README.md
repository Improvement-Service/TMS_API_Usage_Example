# Tell Me Scotland REST API

This repository includes python code and documentation to support users wanting to explore and utilise the 
**Tell Me Scotland** REST API. The Tell Me Scotland API functionality is described below:

###Show notices

**URL:** `/api/v1/notices` or `/api/v1/notices/:id`

**Method:** `GET`

**URL Parameters:** All parameters for this API end-point are optional

`:id` – The unique ID for a notice

`offset`=[integer] – the number of notices to offset the result by (DEFAULT: 0)

`limit`=[integer] – The maximum number of notices to show (DEFAULT: 20)

`archived`=[0/1] – Return archived (1) or unarchived (0) notices (DEFAULT: 0)

`from`=[YYYY-MM-DD] – Return notices created after this date only

`to`=[YYYY-MM-DD] – Return notices created before this date only

`orid`=[integer] – Return only notices with this organization ID

`ntid`=[integer] – Return only notices with this notice type ID

Response Codes: Success OK (`200`), Unauthorized (`401`), Resource not found (`404`)

###Show organisation.

**URL:** `/api/v1/organisations` or `/api/v1/organisations/:id` 

**Method:** `GET`

**URL Parameters:** All parameters for this API end-point are optional

`:id` – The unique ID for an organisation

`offset`=[integer] – the number of organisations to offset the result by (DEFAULT: 0)

`limit`=[integer] – The maximum number of organisations to show (DEFAULT: 20)

Response Codes: Success OK (`200`), Unauthorized (`401`), Resource not found (`404`)

######All organisations: `https://www.tellmescotland.gov.uk/api/v1/organisations.json?limit=100`

###Show notice types.

**URL:** `/api/v1/notice_types` or `/api/v1/notice_types/:id` 

**Method:** `GET`

**URL Parameters:** All parameters for this API end-point are optional

`:id` – The unique ID for a notice type

`offset`=[integer] – the number of notice types to offset the result by (DEFAULT: 0)

`limit`=[integer] – The maximum number of notice types to show (DEFAULT: 20)

Response Codes: Success OK (`200`), Unauthorized (`401`), Resource not found (`404`)

#Examples

####Notice types: `https://www.tellmescotland.gov.uk/api/v1/notice_types.json`
`[{'10': {'ntid': '10', 'name': 'General', 'color': '#97ee4f'}, '11': {'ntid': '11', 'name': 'Traffic', 'color': '#f0b2f7'}, '12': {'ntid': '12', 'name': 'Licensing', 'color': '#67deff'}, '13': {'ntid': '13', 'name': 'Planning', 'color': '#ff8181'}}]`

####One organisation data: `https://www.tellmescotland.gov.uk/api/v1/organisations.json?limit=1`
`[{'12': {'orid': '12', 'title': 'Aberdeen City', 'body': "<p>Aberdeen City Council covers a population of 229,840 (NRS 2016) in Scotland's 3rd largest City. Aberdeen is a lively, cosmopolitan city located in North East Scotland, famous for its beautiful architecture and as a gateway to Scotland's spectacular castle and whisky country. Since the 1970's, the city has been the hub of the UK's energy industry.</p>\r\n", 'status': "<p>Aberdeen City Council covers a population of 229,840 (NRS 2016) in Scotland's 3rd largest City. Aberdeen is a lively, cosmopolitan city located in North East Scotland, famous for its beautiful architecture and as a gateway to Scotland's spectacular castle and whisky country. Since the 1970's, the city has been the hub of the UK's energy industry.</p>\r\n", 'active': "<p>Aberdeen City Council covers a population of 229,840 (NRS 2016) in Scotland's 3rd largest City. Aberdeen is a lively, cosmopolitan city located in North East Scotland, famous for its beautiful architecture and as a gateway to Scotland's spectacular castle and whisky country. Since the 1970's, the city has been the hub of the UK's energy industry.</p>\r\n", 'url': '', 'url_title': '', 'email': '', 'council': '1', 'logo': 'https://www.tellmescotland.gov.uk/sites/default/files/organisation-logos/aberdeen-city.svg'}}]`

####All live notices: `https://www.tellmescotland.gov.uk/api/v1/notices.json?limit=1000000`
