# Xenia indexes

Temporary home for indexes needed for xenia queries.  This will become unnecessary when indexing requirements are built into the system.

```
db.asset.createIndex({"metadata.src_id": 1});
db.asset.createIndex({"metadata.word_count": 1});
db.asset.createIndex({"metadata.section.display_name": 1});
db.asset.createIndex({"metadata.section.keywords": 1});
db.asset.createIndex({"metadata.authors.name": 1});
db.asset.createIndex({"metadata.publicationdate": -1});


db.comment.createIndex({"asset_id": -1})
db.comment.createIndex({"user_id": -1})
db.comment.createIndex({"parent_d": -1})
db.comment.createIndex({"status": 1})
db.comment.createIndex({"date_created": -1})


db.comment.createIndex({"source.id": -1})
db.comment.createIndex({"source.user_id": -1})
db.comment.createIndex({"source.asset_id": -1})

db.comment_timeseries.createIndex({"duration": 1})
db.comment_timeseries.createIndex({"start": 1})
db.comment_timeseries.createIndex({"start_iso": 1})
db.comment_timeseries.createIndex({"target": 1})
db.comment_timeseries.createIndex({"target_doc._id": 1})
db.comment_timeseries.createIndex({"data.comments": 1})
db.comment_timeseries.createIndex({"data.authors": 1})
db.comment_timeseries.createIndex({"data.sections": 1})
db.comment_timeseries.createIndex({"data.comments": 1})
db.comment_timeseries.createIndex({"data.accept_ratio": 1})
db.comment_timeseries.createIndex({"data.replies": 1})
db.comment_timeseries.createIndex({"data.replies_per_comment": 1})

```
