---
title: "Dataset Display"
description: "The combination of a management bar with one or many data visualization types and a possible mechanism of pagination."
layout: "guide"
weight: 1
---

<div class="page-description">{$page.description}</div>

A dataset display is the combination of a [management bar](./management_bar.html) with one or many data visualization types and a possible mechanism of pagination. The most common visualization types used are [table](./table.html), [list](./list.html) and [card](./card.html).

<div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
  <ol class="carousel-indicators">
    <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
    <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
  </ol>
  <div class="carousel-inner">
    <div class="carousel-item active">
      <img class="d-block w-100" src="../../../images/DTTableView.jpg" alt="First slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" src="../../../images/DTListView.jpg" alt="Second slide">
    </div>
    <div class="carousel-item">
      <img class="d-block w-100" src="../../../images/DTCardView.jpg" alt="Third slide">
    </div>
  </div>
  <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
    <span class="carousel-control-prev-icon" aria-hidden="true"></span>
    <span class="sr-only">Previous</span>
  </a>
  <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
    <span class="carousel-control-next-icon" aria-hidden="true"></span>
    <span class="sr-only">Next</span>
  </a>
</div>


### Usage
This pattern is used when the elements of the visualization require collective management, therefore the management bar becomes important as it facilitates tools needed to work with the dataset.

* This pattern can be only used one time in a page.
* Use it is you want to have several visualizations for a set of data.
* Use it if you want to perform actions over the data at individual level or group level.
* Only use the needed visualizations. Not all visualizations are appropriate for all data types.
* When the result of a filter is an empty result, the filter must be possible to be changed to another filter not blocking the management bar usage. Always offer a descriptive message on empty datasets due to no elements or no match in the search.

#### Use a list view
* If you need to display a homogeneous sets of basic data.
* If you need to sort, group, or filter simple data sets.
* If you don’t need to compare between attributes of different items.
* If you need to display a single-level hierarchy.
* If you need to provide a quick identification of the basic content of a list item at a glance.

#### Use a table view
* If you need to manage complex data sets that need to be extensively sorted, grouped, filtered, or edited..
* If you need to compare between attributes of different items.
* If you work with complex hierarchies.

#### Use a grid view
* If the primary content consists on images.
 
#### Use of other visualization methods
* Other visualization methods are also possible, such as map view, but you will have to implement it by yourself as it is not the most common case we have in our platform.



### Empty state

It is important to let the user know what happens in empty states and let them know what has happened and how to perform actions to move out from that empty state. All these scenarios can be found in detail at [empty states](./emptyStates.html) page.

### Individual actions

Individual actions are all those actions that an element has. This actions are always possible to reach from the element itself through the actions menu. Some of this actions are also placed in the management bar when only one element from the dataset is selected. These actions are always represented by a metaphor, , they are buttons with icon. Only those actions that can be easily represented by an icon will be there. Not all possible represented by an icon must be there, only the ones considered as more relevant.

![individual actions displayed both in management bar and from actions menu](../../../images/DatasetDisplayIndividualActions.png)

### Collective actions

Collective actions are shown in the management bar when more than one element is selected in the dataset. In case there are  collective actions that don't have an icon representation the can be placed in a dropdown triggered from the actions button.

![collective actions displayed both in management bar and from actions menu](../../../images/DatasetDisplayGroupActions.png)

### Filtering
* Use filter only when you need them.
* When a filter is applied from the management bar to a visualization type, the visualization type itself needs to update to show the specific data requested by the user.
* A user is only able to filter by the elements that are displayed. Hidden elements can not be used for filtering as they must not appear among the filtering options.
* When the result of a filter is an empty result, the filter must be possible to be changed to another filter not blocking the management bar usage.
 
### Sorting
When sorting is applied from the management bar to a visualization type, the visualization type itself needs to update to show the specific data requested by the user.
* A user is only able to sort by the elements that are displayed. Hidden elements can be used for sorting as they must not appear among the sorting options.
* Tables are able to show the sorting applied in the column header. This update must be done in both ways:
	* When the user sorts using the column header the value must be marked on the sort panel and the arrow must indicate the “sort direction”.
	* When the user sorts using the sort panel and button, the action must be reflected in the appropriate column header.
 
### Selection
When an item is selected in any of the views the management bar must change state 2. This state has a different background color so the user can notice the change. Depending on the number of items selected in the visualization, the number of actions adapt.
* One item selected: The available actions are the same as in the row.
* More than one item selected: The available actions are the ones that apply to the group.
The check box in the management bar selects/unselects all elements in the visualization.


### Drag and drop example

![collective actions displayed both in management bar and from actions menu](../../../images/DatasetDisplayDragDrop.png)

### Change view

Changing view is something to have only when there is more than one visualization. Otherwise, this pattern must not appear in the management bar.

![dataset display view change animation](../../../images/DatasetDisplayChangeView.gif)
