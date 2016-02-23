# Tip - Generate dummy content in wp-cli

#### Generate pages
- `wp post generate --count=10 --post_type=page --post_date=1999-01-04`

#### Generate 10 dummy posts
- `curl http://loripsum.net/api/5 | wp post generate --post_content --count=10`

