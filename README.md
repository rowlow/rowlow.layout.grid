# rowlow.layout.grid

The grid module of ROW LOW is probably one of the most powerful and complex modules in this framework. Basically it helps you build nice responsive grid layouts, but additionally it provides you tools to shift and offset columns and it helps you to apply the right gutter to your grid.

The grid is strongly connected with the breakpoints you've configured in the ```rowlow.utils.breakpoints``` module. Not only the name of your breakpoints, but also the total number of breakpoitns an their value will affect your responsive grid. 

Additionally ROW LOW gives you the possibility to not just use one grid layout at a time, you are able to run a 10-column-based layout and a 12-column-based layout simultaneously if your project requires this.

But please be careful. With every breakpoint and column-layout you add, you multiply the CSS selectors that will be generated by this module.


## Install

```
    bower install --save rowlow.layout.responsive-grid
```


## Settings
```
$rowlow-grid-namespace: "";             // Specific module namespace
$rowlow-grid-columns:   12;             // List of columns for your layout
$rowlow-grid-gutter:    20;             // The gutter width
```

## Functions

```
    rowlow-gutter( $multiplier )        // Returns 0.5 * $mulitpler of $rowlow-grid-gutter
```

## Usage

### Rows & Columns

#### CSS Selector Naming Scheme

```
    .{rowlow-grid-namespace}column--{breakpoint-name}--{column}of{total-columns}
```

#### HTML

```
    <div class="row">
        <div class="column--m--6of12 column--l--4of12">
            
        </div>
        <div class="column--m--6of12 column--l--4of12">
            
        </div>
    </div>
```


### Column Offset

#### CSS Selector Naming Scheme

```
    .{rowlow-grid-namespace}column-offset--{breakpoint-name}--{column}of{total-columns}
```

#### HTML

```
    <div class="row">
        <div class="column--m--4of12 column-offset--m--4of12"></div>
    </div>
```

### Column Shifting

#### CSS Selector Naming Scheme

```
    .{rowlow-grid-namespace}column-push--{breakpoint-name}--{column}of{total-columns}

    .{rowlow-grid-namespace}column-pull--{breakpoint-name}--{column}of{total-columns}
```


#### HTML

```
    <div class="row">
        <div class="column--m--4of12 column-push--m--4of12"></div>
        <div class="column--m--4of12 column-pull--m--4of12"></div>
        <div class="column--m--4of12"></div>
    </div>
```

### Column Gutter

#### CSS Selector Naming Scheme

```
    .gutter--{breakpoint-name}--{gutter-multiplier}
    .gutter-top--{breakpoint-name}--{gutter-multiplier}
    .gutter-right--{breakpoint-name}--{gutter-multiplier}
    .gutter-bottom--{breakpoint-name}--{gutter-multiplier}
    .gutter-left--{breakpoint-name}--{gutter-multiplier}
    .gutter-vertical--{breakpoint-name}--{gutter-multiplier}
    .gutter-horizontal--{breakpoint-name}--{gutter-multiplier}
```

#### SCSS

```
    .any-element{
        padding: rowlow-gutter(1);
    } 
```

#### HTML

                                                        
    <div class="row">
        <div class="column--m--6of12">
            <div class="gutter--s--2 gutter--m--1"></div>
        </div>
        <div class="column--m--6of12">
            <div class="gutter-top--s--2 gutter-top--m--1"></div>
        </div>
        <div class="column--m--6of12">
            <div class="gutter-right--s--2 gutter-right--m--1"></div>
        </div>
        <div class="column--m--6of12">
            <div class="gutter-bottom--s--2 gutter-bottom--m--1"></div>
        </div>
        <div class="column--m--6of12">
            <div class="gutter-left--s--2 gutter-left--m--1"></div>
        </div>
        <div class="column--m--6of12">
            <div class="gutter-vertical--s--2 gutter-vertical--m--1"></div>
        </div>
        <div class="column--m--6of12">
            <div class="gutter-horizontal--s--2 gutter-horizontal--m--1"></div>
        </div>
    </div>