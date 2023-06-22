# Django Todo App

The project is a walkthrough project in the Code Institute Fullstack Developer Program

[Link To App](https://djng-todo-app.herokuapp.com/)

## UX

### User Demographic

This Django Todo List is meant for:

- Anyone who needs a simple todo list with the basic functionality.

### User Stories

#### As a user I expect

- To be able to add an item to the todolist.
- To see the items that have been added.
- To be able to mark an item as done.
- To be able to edit an item.
- To be able to delete an item.

### User Goals

- Add items to the list and complete the items on the list.

### Requirements

A server hosting the list.

### Planning

The project flowshart is as follows:

- Todo List is loaded
  - If there are items in the list
    - Items are listed one after the other in a descending order with toggle/edit/delete buttons
      - User clicks toggle button:
        - The item is toggled between done/not done, if done the item is strike through
      - User clicks edit button:
        - User gets redirected to form to update name/toggle for done
          - User clicks cancel:
            - Item is unchanged and user is redirected to main list
          - User clicks update item:
            - Item gets updated and user is redirected to main list.
      - User clicks delete button:
        - Item is deleted from the list.
  - If no items in list:
    - Display text saying there are no items in the list.
  - User clicks New Item:
    - Redirects to new item form:
      - User fills out form and create new item
        - User gets redirected to list page and new item is created and displayed
      - user clicks cancel:
        - User gets redirected to list page and no new item is created.

### Design

No design has been added to this project as it is a simple project designed to display the functions of django and therefore the website is not styled.

## Features

### List

![list](/readme-imgs/list.png)

Users have the option to add new items or interact with the current items in the list.

The items in the list have 3 buttons:

- Toggle: Toggles if done
- Edit: Redirects to edit page
- Delete: Deletes item

### Toggle
![toggle](/readme-imgs/toggle.png)

List item toggled as done

### Edit/Create Form

The forms are the same with a small difference in that update loads the saved values of the name and done toggle, cancel button redirects you to the list without changes being saved / items being created on each form respectively

#### Add

![create](/readme-imgs/add.png)

Form for creating a list item with name and toggle if done or not, default is not done, below is list after creation of item

![create2](/readme-imgs/listafteradd.png)


#### Edit

![edit](/readme-imgs/edit.png)

Form for updating a list item with name and toggle being loaded in to edit, default is not done

![edit2](/readme-imgs/editafter.png)

#### Delete

![delete1](/readme-imgs/deleteb4.png)

The before and after of deleting item one are above and below respectively

![delete2](/readme-imgs/deleteafter.png)

### Features Left to Implement

- Styling to the UI
- Categories for the Items to create separate lists.

## Technologies used

- [Python](https://www.python.org/)
- [Django](https://www.djangoproject.com/)

## Deployment

### Production Deployment

The deployment consists of creating and linking up the heroku app and connecting it to the ElephantSQL Database.

After creating my django app I deployed the then empty project to Heroku to ensure that everything was done properly well in advance to the production deployment, to avoid any potential deadline issues if there were to occur issues while deploying.

#### Create Heroku app:

1. Log in to Heroku.
2. Create the app in the dashboard by clicking "New" and "Create new app" in the dropdown
3. Name the app, choose the region closes to you and click create app.

#### Create ElephantSQL Database:

1. Log in to ElephantSQL.
2. Create the database isntance in the dashboard by clicking "Create new instace"
3. Name the app, choose the plan and click choose region.
4. Choose region, closes to you, click review.
5. Click Create instance.
6. Navigate to the detaisl apge database you created
7. Copy the value of the URL column, (postgres://.....) to use as a config variable down below

#### Connect ElephantSQL Database to Heroku App:

1. Open the your on the Heroku Dashboard
2. Navigate to the Settings tab and go to config vars, reveal them
3. Add Config Vars Key: DATABASE_URL Value: URL from elephantSQL

#### Deploy App on Heroku:

1. Go to Settings > Config Vars > Reveal Config Vars
2. Add a SECRET_KEY Variable
3. Under Deployment method select github and choose the correct repository.
4. Scroll down to Deploy and deploy the project.
