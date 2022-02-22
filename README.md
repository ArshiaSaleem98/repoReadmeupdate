# Accessibility

The accessibility requirements for all the form tags are already configured in the library. For components (input, checkbox, select, radio…) different attributes have been introduced that can be configured through props. 

Next, we can see different attributes and tags to adjust the accessibility of the form and how to configure them: 

| Attribute/Tag  	| Description  	
|---	   |---	|
|   Aria-describedby	  |  To configure that, only it is necessary to pass “name form” as a prop |
|   Fieldset / Legend	|  Tags that are being used to group and associate related form controls (you can see in the multiple checkbox example given below) |
|   Required    |   To indicate if the field is necessary to fill or not while completing the form |
|   Placeholder	| Used to guide and help the user to describe the format and expected value for the field |
|   Type      |  To specify the type of elements to display | 

* To define the style for the fields, as we use theme-ui, we can either do inline-styling using style=”” or instead sx=”” where you pass the style accordingly. Also, we can include an “id” attribute for input that needs a unique style.

* For the markdown component, we can add the corresponding tag to the text or title. To illustrate that, if the title is an h2, it will include “##” before text, or, if the title is an h3, it will include “###”, and so on. 

### Following are the few code examples to see how we use each component:

### Input tag

```jsx
<div class="form-group">
    <label for="first_name">First name*</label>
    <input
        type="text"
        class="form-control"
        placeholder=""
        id="first_name"
        name="first_name"
        aria-describedby="error_message_first_name"
        required>
    <span class="invalid-feedback"
          style="display:block;"
          id="error_message_first_name">This field is required</span>
</div>
```

### Dropdown fields

```jsx
<div class="form-group">
    <label for="age">Age Range</label>
    <select class="form-control"
            autocomplete="off"
            id="age"
            name="age"
            aria-describedby="error_message_age"
            required
    >
        <option value="" disabled>Please make a selection</option>
        <option value="one">One</option>
        <option value="two">Two</option>
        <option value="three">Three</option>
    </select>
    <span class="invalid-feedback"
          style="display:block;"
          id="error_message_age">Please make a selection</span>
</div>
```

### Multiple checkbox

```jsx
<div class="form-group" ref="what_sport_interested_in">
    <fieldset>
        <legend for="what_sport_interested_in">Are you interested in any of the sports below?</legend>
        <span class="invalid-feedback"
          style="display:block;"
          id="error_message_what_sport_interested_in">Please make a selection</span>
        <div class="form-group container">
            <div class="row">
                <div class="form-check col-12 col-md-6">
                    <input type="checkbox" 
                      class="form-check-input"
                      value="Tennis"
                      id="what_sport_interested_in_tennis"
                      name="what_sport_interested_in_tennis"
                      aria-describedby="error_message_what_sport_interested_in">
                    <label class="form-check-label" for="what_sport_interested_in_tennis">Tennis</label>
                </div>
                <div class="form-check col-12 col-md-6">
                    <input type="checkbox" 
                      class="form-check-input"
                      value="Football"
                      id="what_sport_interested_in_football"
                      name="what_sport_interested_in_football"
                      aria-describedby="error_message_what_sport_interested_in">
                    <label class="form-check-label" for="what_sport_interested_in_football">Football</label>
                </div>
            </div>
        </div>
    </fieldset>
</div>
```

### Checkbox fields

```jsx
<div class="form-group">
    <label for=”privacy_policy">Privacy policy*</label>
    <input
        type="checkbox"
        class="form-control"
        id="privacy_policy"
        name="privacy_policy"
        aria-describedby="error_message_privacy_policy"
        required>
    <span class="invalid-feedback"
          style="display:block;"
          id="error_message_first_name">This field is required</span>
    <div>
         <p> I confirm I am aged 18 years or older, a resident of the United Kingdom and have read and agree to the competition terms and condition and privacy policy</p>
   </div>

```





