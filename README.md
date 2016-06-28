# vue-snackbar

 The Snackbar is a component used to notify a user of an operation's status. It displays at the bottom of the screen. A snackbar may contain an action button to execute a command for the user. Actions should undo the committed action or retry it if it failed for example. Actions should not be to close the snackbar. By not providing an action, the snackbar becomes a toast component

## Installation
With NPM

        npm install 'vue-snackbar'

## Usage

        import Vue from 'vue';
        import Snackbar from 'vue-snackbar'

        new Vue({
            el: 'body',
            components: {
              Snackbar
            }
        });

In the HTML :

        <snackbar v-if="messageSent" message="Message sent!" action-text="UNDO" :action-handler="myHandler()"></snackbar>

## Props

| Prop name      	| Description                                                                     	|
|----------------	|---------------------------------------------------------------------------------	|
| message        	| Message text to be shown on the snackbar.                                       	|
| action-text    	| The text of the action button.                                                  	|
| action-handler 	| Your (the user) custom click handler for when the snackbar's button is clicked. 	|
