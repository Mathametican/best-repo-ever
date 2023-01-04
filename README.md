# best-repo-ever 
List<Contact> listofContacts=[SELECT FirstName,LastName 
                        FROM Contact LIMIT 2];
System.debug(ListofContacts);
string x='MERHABA';
system.debug(x.charAt(0));
system.debug(x.charAt(1));
system.debug(x.charAt(2));
system.debug(x.charAt(3));
system.debug(x.charAt(4));
system.debug(x.charAt(5));
system.debug(x.charAt(6));
string x='MERHABA BUGUN HAVA NASIL ORALARDA';
List<String> m=New List<string>();
m = x.split('') ;
System.debug(m);    
for(Integer a=0; a<m.size();a++){
    String n=m.get(a);
System.debug(n.charAt(0));
}
public class ContactUtility {
    public static void viewContacts(){
    List<Contact> ListOfContacts=[SELECT FirstName, LastName FROM Contact];
        for(Contact con:ListOfContacts){
         String Fullname='First Name:   '+con.FirstName+'  Last Name :   '+con.LastName;
            System.debug(Fullname);
        }
    }
}public class AccountUtility {
    public static void viewAnnualRevenue(){
    List<Account> accountsList=[SELECT Name, AnnualRevenue FROM Account];
    for(Account acctRev:accountsList){
        System.debug('Account Name:  '+acctRev.Name+'   Annual Revenue :  '+Account.AnnualRevenue);
        
    }
}
}
public class PropertyUtility {
    Public static void newListedProperties(){
        List<Property__c> newPropList=[SELECT  Name,Date_Pre_Market__c, Broker__r.Email__c FROM Property__c WHERE Date_Listed__c > Last_N_Days:30];
        for(Property__c Pro:newPropList){
           System.debug('Property Name :  '+Pro.Name+'  Broker Email :  '+Pro.Broker__r.Email__c);  
        }
   }
}

List<String> colors = New List<String>{'Red', 'Yellow', 'Blue' };
   List<String> moreColors = New List<String>();
   moreColors.add('purple');
   moreColors.add('Pink');
for(Integer i=0; i<colors.size();i++){
    moreColors.add(colors.get(i));
}
   System.debug(moreColors);

   //Apex TRIFORCIA 1Opportunity
//Apex CW 3 Contact - 3 Opportunity
Account CW=New Account();
CW.Name='Apex CW';
insert CW;
List<Contact> multiContact= New List<Contact>();
List<Opportunity> multiOpportunity=New List<Opportunity>();

for(Integer num=1; num<=3;num++){
    Contact singleContact=New Contact();
    singleContact.FirstName='APEX '+num;
    singleContact.LastName='CW Worker'+num;
    singleContact.accountId=CW.id;
    multiContact.add(singleContact);
    
    Opportunity singleOpportunity=New Opportunity();
    singleOpportunity.Name=CW.Name+'  Opportunity  '+num;
    singleOpportunity.CloseDate=date.Today()+25;
    singleOpportunity.StageName='Prospecting';
    singleOpportunity.accountId=CW.id;
    multiOpportunity.add(singleOpportunity);
}
insert multiContact;
insert multiOpportunity;


//Apex Triforcia 0 Contact 1 Opportunity
//APEX CW 3 Contact 3 Opp.
//APEX CW 3 Contact 4 Opp.

Account triforcia=[SELECT Id, Name FROM Account 
                   WHERE Name ='Apex-Triforcia'];
Account CW = [SELECT Id, Name FROM Account WHERE Name='Apex CW'];
merge CW triforcia;    // burada triforcia Account ile Apex CW accountu merge 
                       // ettik. iki Account un birleşimi yapıldı.
                       // Sonuç APEX CW oldu . 
