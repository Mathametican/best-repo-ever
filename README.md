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
