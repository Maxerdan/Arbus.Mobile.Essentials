# Arbus.Mobile.Essentials
Essential tools for building mobile apps

[![Build Status](https://dev.azure.com/arbus/GitHub%20Pipelines/_apis/build/status/Arbus.Mobile.Essentials?branchName=main)](https://dev.azure.com/arbus/GitHub%20Pipelines/_build/latest?definitionId=46&branchName=main)

## How top use iOS.Essentials 

### Fluent AutoLayout:

```
View.AddSubviewsForAutoLayout(_label, _label2, _label3, _label4);
View.AddConstraints(
  _label.WithSameTop(View, margin: ...),
  _label.WithSameBottom(View, margin: ...),
  _label.ToLeftOf(sNameLabel, margin: ...),

  _label2.WithSameTop(_label),
  _label2.AtRightOf(View, margin: ...),
  _label2.WithSameWidth(_label),

  _label3.WithSameWidth(_label2),
  _label3.WithSameLeft(_label2),
  _label3.Below(_label2, margin: ...),
```

### Fluent UIView extensions:

```
TableView = new UITableView()
    .AccessibilityIdentifier("identifier")
    .MultipleTouch(false)
    .ExclusiveTouch()
    .NoBackgroundColor()
    .SetSource(x => _source = new TableViewSource(x))
    .SetDelegate(() => new TableViewDelegate())
    .SeparatorInset(UIEdgeInsets.Zero)
    .SectionHeaderTopPadding()
    .SeparatorColor(UIColor.OpaqueSeparator);
    
_label = new UILabel()
  .SetText("Some text")
  .SetFontAsBold(UIFontDescriptor.PreferredBody)
  .SetTextAlignment(UITextAlignment.Center)
  .SetTextColor(UIColor.White)
  .SetLinesUnlimited();
```

### SfSymbol:

```
public static SfSymbol ChevronRight => new("chevron.right");
public static SfSymbol ChevronLeft => new("chevron.left");

ChevronRight.ToUiImage(UIImageSymbolWeight.Medium);

_imageView = new UIImageView()
    .Image(SfSymbols.ChevronRight); //implicit operator
```

### DiffableDataSource:

DiffableDataSourceSnapshot and DataSourceIdentifierType

DiffableDataSourceSnapshot<TSection, TItem> snapshot = new();
snapshot.AppendSections(Sections);
snapshot.AppendItems(Items, section);

## Downloads

The latest stable releases are available on NuGet:
- [Arbus.iOS.Essentials](https://www.nuget.org/packages/Arbus.iOS.Essentials)
- Arbus.Android.Essentials (None for now)
