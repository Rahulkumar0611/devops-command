# MongoDB Docker Commands

## Enter Inside MongoDB Docker Container

This command lets you enter inside the running Docker container named `school_mongo`.

### Step 1: Enter MongoDB Container in mongodb

```bash
docker exec -it school_mongo bashs
```
iouisyusay
saouiuyft
---piouiyusayt

## Open Mongo Shell shugusagsuasguasaljhgh  osihugyfsiuts

### Step 2: Start MongoDB Shell

```bash
mongosh
```

---

## Show All Databases

### Step 3: View Databases

```javascript
show dbs
```

---

## Show Collections

### Step 4: View Collections

```javascript
show collections
```

---

## View Collection Data

### Step 5: View Documents

```javascript
db.users.find()
```

Pretty formatted output:

```javascript
db.users.find().pretty()
```

---

## Exit Mongo Shell / Container

```bash
exit
```

---

# MongoDB Index Commands

## Show Existing Indexes

```javascript
db.classes.getIndexes()
```

---

## Delete Specific Index

Use the index name:

```javascript
db.classes.dropIndex("className_1")
```

---

## Delete All Indexes Except Default `_id`

```javascript
db.classes.dropIndexes()
```

---

## Verify Indexes Again

```javascript
db.classes.getIndexes()
```

---

# Important Notes

* Removing indexes can slow down database queries.
* If you remove a unique index, duplicate data can be inserted afterward.
* In production environments, deleting indexes on huge collections can temporarily affect performance.
* Always verify indexes before deleting them.

---

## Useful Commands

### Check Running Containers

```bash
docker ps
```

### View Docker Images

```bash
docker images
```

### Check MongoDB Container Logs

```bash
docker logs school_mongo
```
