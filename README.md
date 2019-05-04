Intallation

```bash
pip install jsonstoredb
```

Example Usage

```python
from jsonstoredb import JSONStore

db = JSONStore()
users = db.table("users")
resume = db.table("resume")

users.insert("1", {
    "role": "admin",
    "name": "admin",
    "password": "1234"
})

users.insert("10", {
    "role": "admin",
    "name": "userman",
    "password": "hunter2"
})

user = users.select("1")
# user == {'name': 'admin', 'password': '1234'}
user = users.select("2")
# user == None
admins = users.selectBy(lambda val: val["role"] == "admin", limit=None)
# admins == [('1', {'name': 'admin', 'password': '1234'}), ('10', {'name': 'admin', 'password': 'hunter2'})]

```
