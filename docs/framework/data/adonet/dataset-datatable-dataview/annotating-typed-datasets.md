---
title: Annotazione di dataset tipizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 8ce7cd859ce0c9a5874751e9928e5bced33593d6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205244"
---
# <a name="annotating-typed-datasets"></a>Annotazione di dataset tipizzati
Le annotazioni consentono di modificare i nomi degli elementi nel <xref:System.Data.DataSet> tipizzato senza modificare lo schema sottostante. Se si modificano i nomi degli elementi nello schema sottostante, il **set** di dati tipizzato farà riferimento a oggetti che non esistono nell'origine dati, oltre a perdere un riferimento agli oggetti esistenti nell'origine dati.  
  
 Utilizzando le annotazioni, è possibile personalizzare i nomi degli oggetti nel **set di dati** tipizzato con nomi più significativi, rendendo il codice più leggibile e il **set di dati** tipizzato più semplice per l'utilizzo da parte dei client, lasciando intatto lo schema sottostante. Ad esempio, l'elemento dello schema seguente per la tabella Customers del database **Northwind** genera un nome di oggetto **DataRow** di **CustomersRow** e un <xref:System.Data.DataRowCollection> oggettodenominato Customers.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Il nome di un DataRowCollection dei **clienti** è significativo nel codice client, ma un nome **DataRow** di **CustomersRow** è fuorviante perché è un singolo oggetto. Negli scenari comuni, inoltre, l'oggetto verrebbe denominato senza l'identificatore di **riga** , ma verrebbe semplicemente definito oggetto **Customer** . La soluzione consiste nell'annotare lo schema e nell'identificare nuovi nomi per gli oggetti **DataRow** e **DataRowCollection** . Di seguito viene riportata una versione annotata dello schema precedente.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Se si specifica un valore tipizzato **Customer** , viene generato il nome dell'oggetto **DataRow** del **cliente**. Specificando un valore **typedPlural** di **Customers** , viene mantenuto il nome **DataRowCollection** dei **clienti**.  
  
 Nella seguente tabella sono indicate le annotazioni disponibili.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**typedName**|Nome dell'oggetto.|  
|**typedPlural**|Nome della raccolta di oggetti.|  
|**typedParent**|Nome dell'oggetto quando si fa riferimento a tale oggetto in una relazione padre.|  
|**typedChildren**|Nome del metodo per la restituzione di oggetti da una relazione figlio.|  
|**nullValue**|Valore se il valore sottostante è **DBNull**. Per le annotazioni **NullValue** , vedere la tabella seguente. Il valore predefinito è **_throw**.|  
  
 Nella tabella seguente vengono illustrati i valori che è possibile specificare per l'annotazione **NullValue** .  
  
|Valore nullValue|Descrizione|  
|---------------------|-----------------|  
|*Valore di sostituzione*|Specifica il valore da restituire. È necessario che il valore restituito corrisponda al tipo dell'elemento. Usare ad esempio `nullValue="0"` per restituire 0 per i campi integer null.|  
|**_throw**|Generazione di un'eccezione. Questa è l'impostazione predefinita.|  
|**_null**|Consente di restituire un riferimento null o di generare un'eccezione se viene rilevato un tipo primitivo.|  
|**_empty**|Per le stringhe, restituire **String. Empty**. in caso contrario, restituisce un oggetto creato da un costruttore vuoto. Se viene rilevato un tipo primitivo, consente di generare un'eccezione.|  
  
 Nella tabella seguente vengono illustrati i valori predefiniti per gli oggetti in un **DataSet** tipizzato e le annotazioni disponibili.  
  
|Oggetto/Metodo/Evento|Predefinito|Annotazione|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** Metodi|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Proprietà**|PropertyName|typedName|  
|**Figlio** Accesso|GetChildTableNameRows|typedChildren|  
|**Elemento padre** Accesso|TableNameRow|typedParent|  
|**Set di dati** Eventi|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Per utilizzare le annotazioni del **set di dati** tipizzato, è necessario includere il riferimento **xmlns** seguente nello schema XSD (XML Schema Definition Language). Per creare un XSD dalle tabelle di database, <xref:System.Data.DataSet.WriteXmlSchema%2A> vedere o uso dei set di dati [in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Di seguito è riportato uno schema con annotazioni di esempio che espone la tabella Customers del database **Northwind** con una relazione con la tabella **Orders** inclusa.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"   
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 Nell'esempio di codice seguente viene utilizzato un **set di dati** fortemente tipizzato creato dallo schema di esempio. Viene utilizzato uno <xref:System.Data.SqlClient.SqlDataAdapter> per popolare la tabella Customers e <xref:System.Data.SqlClient.SqlDataAdapter> un'altra per popolare la tabella **Orders** . Il set di **dati** fortemente tipizzato definisce i DataRelation.  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",   
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new   
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =   
    customers.Customers.NewCustomer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Set di dati tipizzati](typed-datasets.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
