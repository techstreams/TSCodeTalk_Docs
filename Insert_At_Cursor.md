# TSCodeTalk > Docs > Insert at Cursor

This function inserts text at the doc cursor.

---

```js
/**
 * Inserts the sentence "Hey there!" at the current cursor location in boldface.
 */
function insertAtCursor() {
  var cursor = DocumentApp.getActiveDocument().getCursor();

  if (cursor) {
    // Attempt to insert text at the cursor position. If insertion returns null,
    // then the cursor's containing element doesn't allow text insertions.
    var element = cursor.insertText('Hey there!');
    if (element) {
      element.setBold(true);
    } else {
      DocumentApp.getUi().alert('Cannot insert text at this cursor location.');
    }
  } else {
    DocumentApp.getUi().alert('Cannot find a cursor in the document.');
  }
}
```
