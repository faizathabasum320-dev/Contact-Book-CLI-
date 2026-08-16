# Contact-Book-CLI-
Add, search, and delete contacts stored in a JSON file
import json, os
FILE = "contacts.json"
contacts = json.load(open(FILE)) if os.path.exists(FILE) else {}

cmd = input("add/search/delete/list: ")
if cmd == "add":
    name = input("Name: "); contacts[name] = input("Phone: ")
elif cmd == "search":
    print(contacts.get(input("Name: "), "Not found"))
elif cmd == "delete":
    contacts.pop(input("Name: "), None)
elif cmd == "list":
    for k, v in contacts.items(): print(k, v)
json.dump(contacts, open(FILE, "w"))
