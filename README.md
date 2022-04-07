# This is all about creating url linked drop down using wix code format.Most people facing the problem as wix dont have such method added o its library so i find it usefull to help all freinds who are facing problems linking drop down to url of pages the below method works use it.
Fisrt of all you must have a wix static page .
Create a datavbase using wix database creator.databse name-myskn
Create a drop down menu from tool bar ."dropdown1"
add a button from tool bar 
open developer option in wix 
create drop down on change event
paste the code below
import wixLocation from 'wix-location';


$w("#dropdown1").options = [
{"Label": "Open", "value": "edit-user-profile"},
{"Label": "Edit", "value": "userprofiledata/{ID}"},
];
export function dropdown1n_change(event)
{
let page = event.target.value; // new page name selected
let path = "/" + page; // create path to your local page
wixLocation.to(path);
}
OR you can with simple dropdown using below code

import wixLocation from 'wix-location';

$w.onReady(function () {

});

export function dropdown1_change(event, $w) {
    console.log(event.target.value);
    wixLocation.to(event.target.value);
}
but use change vent function in drop down menu

You can visit fo more help on wix to: https://www.wix.com/velo/forum/coding-with-velo/dropdown-list-with-options-that-can-link-to-pages
https://www.skntechnology.in
