## Background

Atlassian is having a major outage on Apr 2022, with one week already passed and with ETA of restoration at two weeks.

* Cause: One product was to be removed.
And maintenance script to delete the data went haywire,
as it was executed with wrong mode and wrong list of IDs.
  * Wrong mode: permanent deletion instead of delete with failsafe
  * Wrong ID: where the plugin is installed v.s. where plugin data should be deleted.

## Reference

* Official Atlassian update [april-2022-outage-update](https://www.atlassian.com/engineering/april-2022-outage-update)