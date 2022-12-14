Creating an SPA - RecipeBook

This will work with an API that is created in Express -> linked to Mongodb

1. Create a base RecipeBook.js and import into App.js
   npm install react-bootstrap bootstrap
   npm install axios
2. Setup state mock data
   _id, title, ingredients[]
3. Place current page as a state page: list
4. Install bootstrap and place the css in
5. Copy and paste bootstrap nav bar
   Remember to change all class to className
6. Create a function renderPage
   setup if else. handles the paging between pages
   if list -> go to AllRecipe
   if add -> go to AddNew
7.  Create 2 basic function components with simple JSX
   AddNew: to deal with add recipes
    AllRecipe: to deal with listing of recipes
8.  Import in AddNew AllRecipe into RecipeBook
9.  Change our nav bar to redirect to AddNew | AllRecipe
10. Setup on click that uses a closure onClick={()=>this.switchPage(<page>)}
11. Create a function switchPage that takes in a parameter and changes the current page to that parameter
12. Update render function to include renderPage
13. How the pages change is due to the current state of page
    if this.state.page is list: go to AllRecipe
    if this.state.page is add: go to AddNew
    Default this.state.page is list
14. Send mock data over to AllRecipe using props (lifting up states)
    <AllRecipe recipes={this.state.data}/>: send data over as props
15. Upgrade AllRecipe to have props recipes
    Create a map to print out the recipes data and ingredients
16. Create new component RecipeItem in /components folder. This just does JSX of 1 item
17. Upgrade AllRecipe to use component RecipeItem. (Splitting up the UI)
    Extract JSX of map and place inside RecipeItem
    Change JSX to using props
    Update AllRecipe to send props data over to RecipeItem
    Send _id,title,ingredients as props
18. Dealing with the Create-CRUD. Modify AddNew to include a form
    Create 2 labels and textboxes
    Apply some bootstrap css
19. Setup 1way and 2way binding with AddNew
    setup name,value,onChange on AddNew to use props
    Create a function updateFormFields in RecipeBook to handle form changes and set the state
    Send props data over in RecipeBook > AddNew
20. Create a new function addNew.
    Create a temp obj
    _id: <random id>
    title: this.state.newRecipeTitle
    ingredients: this.state.newRecipeIngredients
    Set the state and update the items and current page
    data: <new recipes>
    page: list (Change the state of the current page back to list. Gives a "redirect")
21. Upgrade to use API data.
    Install axios npm install axios
22. Create an express application
    Install express, cors, mongodb, dotenv
23. Creation of APIs
24. Update RecipeBook to use axios
    Set a BASE_API_URL to the API created
    Use the function componentDidMount
    Make an API call inside