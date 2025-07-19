
In **Apex triggers**, Salesforce provides a set of built-in **trigger context variables** that allow you to access information about the current execution context — like what event is happening, which records are involved, and what operation is being performed.

Here’s a **complete list of all trigger context variables** in Apex:

---

## **1. `Trigger.isInsert`**
- **Returns**: `true` if the trigger was fired due to an **insert** operation.
- **Use Case**: When you want to run logic only during record creation.

---

## **2. `Trigger.isUpdate`**
- **Returns**: `true` if the trigger was fired due to an **update** operation.
- **Use Case**: Compare old and new values on record updates.

---

## **3. `Trigger.isDelete`**
- **Returns**: `true` if the trigger was fired due to a **delete** operation.
- **Use Case**: Logic for cleanup or archive on deletion.

---

## **4. `Trigger.isBefore`**
- **Returns**: `true` if the trigger was fired **before** the record was saved to the database.
- **Use Case**: Modify field values before saving (e.g., auto-calculate fields).

---

## **5. `Trigger.isAfter`**
- **Returns**: `true` if the trigger was fired **after** the record was saved.
- **Use Case**: Access record IDs, do DML on related records.

---

## **6. `Trigger.isUndelete`**
- **Returns**: `true` if the trigger was fired due to a **record undelete**.
- **Use Case**: Restore related data or logs when a record is undeleted.

---

## **7. `Trigger.new`**
- **Type**: `List<SObject>`
- **Returns**: A list of **new versions** of the records in **insert**, **update**, or **undelete** triggers.
- **Use Case**: Access current field values being inserted or updated.

---

## **8. `Trigger.old`**
- **Type**: `List<SObject>`
- **Returns**: A list of **old versions** of the records in **update** or **delete** triggers.
- **Use Case**: Compare field changes or access deleted records.

---

## **9. `Trigger.newMap`**
- **Type**: `Map<Id, SObject>`
- **Returns**: A map of record IDs to **new versions** (for update and insert triggers).
- **Use Case**: Fast lookups for related data processing.

---

## **10. `Trigger.oldMap`**
- **Type**: `Map<Id, SObject>`
- **Returns**: A map of record IDs to **old versions** (for update and delete triggers).
- **Use Case**: Compare changes by record ID.

---

## **11. `Trigger.size`**
- **Type**: `Integer`
- **Returns**: The total number of records in the trigger context.
- **Use Case**: Useful for debugging, limits handling, or batch control.

---

## **12. `Trigger.operationType`**
- **Type**: `System.TriggerOperation` enum
- **Returns**: Enum value that tells you the exact operation type.
  - `BEFORE_INSERT`
  - `AFTER_INSERT`
  - `BEFORE_UPDATE`
  - `AFTER_UPDATE`
  - `BEFORE_DELETE`
  - `AFTER_DELETE`
  - `AFTER_UNDELETE`

- **Use Case**: Cleaner alternative to multiple `if` conditions.

---

### Example Use in a Trigger:

```apex
trigger AccountTrigger on Account (before insert, before update) {
    if (Trigger.isInsert) {
        for (Account acc : Trigger.new) {
            acc.Name = acc.Name + ' - Verified';
        }
    }

    if (Trigger.isUpdate) {
        for (Account acc : Trigger.new) {
            Account oldAcc = Trigger.oldMap.get(acc.Id);
            if (acc.Name != oldAcc.Name) {
                System.debug('Account name was changed!');
            }
        }
    }
}
```

---

### Summary Table

| Variable | Type | Available In | Purpose |
|----------|------|--------------|---------|
| `isInsert` | Boolean | All triggers | Check if insert |
| `isUpdate` | Boolean | All triggers | Check if update |
| `isDelete` | Boolean | All triggers | Check if delete |
| `isBefore` | Boolean | All triggers | Check if before save |
| `isAfter` | Boolean | All triggers | Check if after save |
| `isUndelete` | Boolean | After undelete | Check if undelete |
| `new` | List<SObject> | Insert, Update, Undelete | New versions of records |
| `old` | List<SObject> | Update, Delete | Old versions of records |
| `newMap` | Map<Id, SObject> | Insert, Update | Map of new records |
| `oldMap` | Map<Id, SObject> | Update, Delete | Map of old records |
| `size` | Integer | All triggers | Number of records |
| `operationType` | Enum | All triggers | Operation being performed |

---

Let me know if you’d like a **cheat sheet PDF**, or a **code sample trigger** with all these context variables in action!