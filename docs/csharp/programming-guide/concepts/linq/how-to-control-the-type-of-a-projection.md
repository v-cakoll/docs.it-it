---
title: Come controllare il tipo di una proiezione (C )
ms.date: 07/20/2015
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
ms.openlocfilehash: cb7c272fbe67c0700b5740691befc483993f4e29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141360"
---
# <a name="how-to-control-the-type-of-a-projection-c"></a>Come controllare il tipo di una proiezione (C )
Per proiezione si intende il processo in cui un unico set di dati viene accettato e filtrato, ne viene cambiata la forma e persino il tipo. Le proiezioni vengono eseguite nella maggior parte delle espressioni di query. Quasi tutte le espressioni di query illustrate in questa sezione restituiscono il tipo <xref:System.Collections.Generic.IEnumerable%601> di <xref:System.Xml.Linq.XElement>, tuttavia è possibile controllare il tipo della proiezione per creare raccolte di altri tipi. In questo argomento viene illustrato come eseguire questa operazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito un nuovo tipo `Customer`. L'espressione di query crea quindi un'istanza per nuovi oggetti `Customer` nella clausola `Select`. Il tipo dell'espressione di query diventa quindi <xref:System.Collections.Generic.IEnumerable%601> di `Customer`.  
  
 Questo esempio usa il documento XML seguente: [File XML di esempio: clienti e ordini (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).  
  
```csharp  
public class Customer  
{  
    private string customerID;  
    public string CustomerID{ get{return customerID;} set{customerID = value;}}  
  
    private string companyName;  
    public string CompanyName{ get{return companyName;} set{companyName = value;}}  
  
    private string contactName;  
    public string ContactName { get{return contactName;} set{contactName = value;}}  
  
    public Customer(string customerID, string companyName, string contactName)  
    {  
        CustomerID = customerID;  
        CompanyName = companyName;  
        ContactName = contactName;  
    }  
  
    public override string ToString()  
    {  
        return $"{this.customerID}:{this.companyName}:{this.contactName}";
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement custOrd = XElement.Load("CustomersOrders.xml");  
        IEnumerable<Customer> custList =  
            from el in custOrd.Element("Customers").Elements("Customer")  
            select new Customer(  
                (string)el.Attribute("CustomerID"),  
                (string)el.Element("CompanyName"),  
                (string)el.Element("ContactName")  
            );  
        foreach (Customer cust in custList)  
            Console.WriteLine(cust);  
    }  
}  
```  
  
 L'output del codice è il seguente:  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Linq.Enumerable.Select%2A>
