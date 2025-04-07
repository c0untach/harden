# harden

## Confidentiality
TBA

## Integrity
```bash
# install aide
apt install aide -y

# change line 8 in /etc/default/aide if cron daily will be activated
CRON_DAILY_RUN=yes

# add locations to exclude from aide to /etc/aide/aide.conf
!/var/log

# initialize aide database
aide --init --config /etc/aide/aide.conf

# copy database
cp -p /var/lib/aide/aide.db.new /var/lib/aide/aide.db

# run aide check against the database
aide --check --config /etc/aide/aide.conf

# if you want to update database with accepted changes run 
aide --update --config /etc/aide/aide.conf

# and copy current database to act as a trusted database
cp -p /var/lib/aide/aide.db.new /var/lib/aide/aide.db
```

## Availability
TBA
