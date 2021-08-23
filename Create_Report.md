# TSCodeTalk > Docs > Create Report

This function creates a report in a Google Doc from scratch.

---

```js
/**
 * Constructs a simple report with three body sections and a footer in the
 * current Google Docs document.
 */
function createReport() {
  var title = 'Script Center Report';
  var summaryContents = 'This reports addresses...';
  var overviewContents = 'We undertook this project because...';
  var dataContents = 'We collected three samples of data...';

  var doc = DocumentApp.getActiveDocument();
  var body = doc.getBody();

  // Build up the report's title and abstract.
  var reportTitle = body.appendParagraph(title);
  reportTitle.setFontFamily(DocumentApp.FontFamily.ARIAL);
  reportTitle.setFontSize(24);
  reportTitle.setForegroundColor('#4a86e8');
  reportTitle.setAlignment(DocumentApp.HorizontalAlignment.CENTER);

  var execSummary = body.appendParagraph('Executive Summary');
  execSummary.setFontSize(14);
  execSummary.setSpacingBefore(14);
  execSummary.setBold(true);

  var execBody = body.appendParagraph(summaryContents);
  execBody.setFontFamily(DocumentApp.FontFamily.TIMES_NEW_ROMAN);
  execBody.setFontSize(12);
  execBody.setSpacingBefore(6);

  // Build up the report's contents.
  var overview = body.appendParagraph('Project Overview');
  overview.setFontSize(14);
  overview.setSpacingBefore(14);
  overview.setBold(true);

  var overviewBody = body.appendParagraph(overviewContents);
  overviewBody.setFontFamily(DocumentApp.FontFamily.TIMES_NEW_ROMAN);
  overviewBody.setFontSize(12);
  overviewBody.setSpacingBefore(6);

  var data = body.appendParagraph('Project Data');
  data.setFontSize(14);
  data.setSpacingBefore(14);
  data.setBold(true);

  var dataBody = body.appendParagraph(dataContents);
  dataBody.setFontFamily(DocumentApp.FontFamily.TIMES_NEW_ROMAN);
  dataBody.setFontSize(12);
  dataBody.setSpacingBefore(6);

  // Build up the report's footer.
  var footer = doc.addFooter();

  var divider = footer.appendHorizontalRule();

  var footerText = footer.appendParagraph('Confidential and proprietary');
  footerText.setFontSize(9);
  footerText.setForegroundColor('#4a86e8');
  footerText.setAlignment(DocumentApp.HorizontalAlignment.RIGHT);

  return doc;
}
```
