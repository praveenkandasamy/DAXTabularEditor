# DAXTabularEditor
DAXTabularEditor



https://github.com/praveenkandasamy/DAXTabularEditor.git


//COUNT
// Creates a COUNT measure for every currently selected column and not hide the column.

foreach(var c in Selected.Columns)

{
    var newMeasure = c.Table.AddMeasure(
        "Count of " + c.Name,                    // Name
        "COUNT(" + c.DaxObjectFullName + ")",    // DAX expression
        c.DisplayFolder                        // Display Folder
    );
    
    // Set the format string on the new measure:
    newMeasure.FormatString = "#,0";

    // Provide some documentation:
    newMeasure.Description = "This measure is the count of column " + c.DaxObjectFullName;

    // Hide the base column:
    c.IsHidden = false;
}


