# Angular-classes
Prerequisite to learn angular
Install Node and npm latest version 
Install Angular CLI 8 or later 
Install Visual Studio Code 


For dry run
$ ng new angular-application -d

// To create angular application
$ ng new angular-application

// to redirect to path
$ cd angular-application

// to run application in development mode
$ ng serve --open 
$ ng s -o
// Open http://localhost:4200 to view it in the browser.

// to build application 
$ ng build
// create dist folder which will go for production





install bootstrap, jquery and @types/jquery to your package.json file

$ npm install bootstrap@3 --save
$ npm install @types/jquery --save
$ npm install jquery --save
// or you can all these command in one go
$ npm install bootstrap@3 @types/jquery jquery --save




Create Customer, Supplier and Home page using below command

$ ng g c Home/Home --skipTests --flat=true -is
$ ng g c Customer/Customer --skipTests --flat=true -is
$ ng g c Supplier/Supplier --skipTests --flat=true -is
--skipTests is to skipt spec files 
--flat is to not create folder 
-is is to skip css files 

Add below code snippet in app-routing.module

const routes: Routes = [
  { path: 'Home', component: HomeComponent },
  { path: 'Customer', component: CustomerComponent },
  { path: 'Supplier', component: SupplierComponent },
  { path: '', component: HomeComponent }

];



Add below code snippet in app.component.html

<div class="container">
    <nav class="navbar navbar-default">
        <ul class="nav navbar-nav">
            <li routerLinkActive="active"><a routerLink="Home" >Home</a></li>
            <li routerLinkActive="active"><a routerLink="Customer" >Customer</a></li>
            <li routerLinkActive="active"><a routerLink="Supplier" >Supplier</a></li>
        </ul>
    </nav>
    <router-outlet></router-outlet>
</div>




Creating simple UI page
Create Customer Model class in customer folder using below command

$ ng g class Customer/customer-model --skipTests
Add below code snippet in customer-model.ts

export class CustomerModel {
    CustomerCode: string;
    CustomerName: string;
    CustomerAmount: number;
}
Create simple UI page in customer.component.html

<div>
    Customer code : <input type="text" [(ngModel)]="customerModel.CustomerCode" name="cCode" id="cCode"> <br>
    Customer name : <input type="text" [(ngModel)]="customerModel.CustomerName" name="cName" id="cName"> <br>
    Customer amount : <input type="text" [(ngModel)]="customerModel.CustomerAmount" name="cAmount" id="cAmount"> <br>
    <input type="button" value="Add">
    <br>
    {{customerModel.CustomerCode}} <br>
    {{customerModel.CustomerName}} <br>
    {{customerModel.CustomerAmount}} <br>
</div>





For creating html table
create customers object in customer.component.ts

import { CustomerModel } from './customer-model';
.
export class CustomerComponent implements OnInit {
  .
  .
  customerModel: CustomerModel = new CustomerModel();
  customerModels: Array<CustomerModel> = new Array<CustomerModel>();

  Add() {
    this.customerModels.push(this.customerModel);
    this.customerModel = new CustomerModel();
  }
}



