# TSCodeTalk > Docs > Turn Selection Color

This function turns the selected doc text purple.

---

```js
/**
 * Sets the background color of any selected text to purple. Not very useful,
 * perhaps, but it demonstrates how to read and modify the current document
 * selection.
 */
function turnSelectionPurple() {
  // Try to get the current selection in the document. If this fails (e.g.,
  // because nothing is selected), show an alert and exit the function.
  var selection = DocumentApp.getActiveDocument().getSelection();
  if (!selection) {
    DocumentApp.getUi().alert('Cannot find a selection in the document.');
    return;
  }

  var selectedElements = selection.getSelectedElements();
  for (var i = 0; i < selectedElements.length; ++i) {
    var selectedElement = selectedElements[i];

    // Only modify elements that can be edited as text; skip images and other
    // non-text elements.
    var text = selectedElement.getElement().editAsText();

    // Change the background color of the selected part of the element, or the
    // full element if it's completely selected.
    if (selectedElement.isPartial()) {
      text.setBackgroundColor(selectedElement.getStartOffset(),
          selectedElement.getEndOffsetInclusive(), '#69359c');
    } else {
      text.setBackgroundColor('#69359c');
    }
  }
}
```
