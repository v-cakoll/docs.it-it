---
title: Annotazione di dataset tipizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151520"
---
# <a name="annotating-typed-datasets"></a>Annotazione di dataset tipizzati
Le annotazioni consentono di modificare i nomi degli elementi nel <xref:System.Data.DataSet> tipizzato senza modificare lo schema sottostante. La modifica dei nomi degli elementi nello schema sottostante causerebbe il **DataSet** tipizzato fare riferimento a oggetti che non esistono nell'origine dati, nonché perdere un riferimento agli oggetti presenti nell'origine dati.  
  
 Utilizzando le annotazioni, è possibile personalizzare i nomi degli oggetti nel **DataSet** tipizzato con nomi più significativi, rendendo il codice più leggibile e il **DataSet** tipizzato per i client da utilizzare, lasciando intatto lo schema sottostante. Ad esempio, il seguente elemento dello schema per la tabella **Customers** del database **Northwind** comporterebbe un nome di oggetto **DataRow** denominato **CustomersRow** e un <xref:System.Data.DataRowCollection> nome **Customers**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Un **nome DataRowCollection** di **Customers** è significativo nel codice client, ma un nome **DataRow** di **CustomersRow** è fuorviante perché è un singolo oggetto. Inoltre, negli scenari comuni, l'oggetto verrebbe indicato senza l'identificatore **di riga** e invece verrebbe semplicemente indicato come un oggetto **Customer.** La soluzione consiste nell'annotare lo schema e identificare nuovi nomi per il **DataRow** e **DataRowCollection** oggetti. Di seguito viene riportata una versione annotata dello schema precedente.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Se si specifica un valore **typedName** di **Customer,** verrà dato come risultato un nome di oggetto **DataRow** **Customer**. Se si specifica un valore **typedPlural** di **Customers,** il nome **DataRowCollection** di **Customers**viene mantenuto.  
  
 Nella seguente tabella sono indicate le annotazioni disponibili.  
  
|Annotazione|Descrizione|  
|----------------|-----------------|  
|**typedName**|Nome dell'oggetto.|  
|**typedPlural**|Nome della raccolta di oggetti.|  
|**typedParent**|Nome dell'oggetto quando si fa riferimento a tale oggetto in una relazione padre.|  
|**typedChildren**|Nome del metodo per la restituzione di oggetti da una relazione figlio.|  
|**nullValue**|Valore se il valore sottostante è **DBNull**. Vedere la tabella seguente per le annotazioni **nullValue.See** the following table for nullValue annotations. Il valore predefinito è **_throw**.|  
  
 Nella tabella seguente vengono illustrati i valori che possono essere specificati per l'annotazione **nullValue.**  
  
|Valore nullValue|Descrizione|  
|---------------------|-----------------|  
|*Valore di sostituzione*|Specifica il valore da restituire. È necessario che il valore restituito corrisponda al tipo dell'elemento. Usare ad esempio `nullValue="0"` per restituire 0 per i campi integer null.|  
|**_throw**|Generazione di un'eccezione. Questa è la modalità predefinita.|  
|**_null**|Consente di restituire un riferimento null o di generare un'eccezione se viene rilevato un tipo primitivo.|  
|**_empty**|Per le stringhe, restituire **String.Empty**, in caso contrario restituire un oggetto creato da un costruttore vuoto. Se viene rilevato un tipo primitivo, consente di generare un'eccezione.|  
  
 Nella tabella seguente vengono illustrati i valori predefiniti per gli oggetti in un **DataSet** tipizzato e le annotazioni disponibili.  
  
|Oggetto/Metodo/Evento|Predefinito|Annotazione|  
|---------------------------|-------------|----------------|  
|**Datatable**|TableNameDataTable|typedPlural|  
|**DataTable** Metodi|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**Datarow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Proprietà**|PropertyName|typedName|  
|**Bambino** Funzione|GetChildTableNameRows|typedChildren|  
|**Genitore** Funzione|TableNameRow|typedParent|  
|**DataSet (Gruppo di dati)** Eventi|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Per utilizzare le annotazioni **di DataSet** tipizzate, è necessario includere il riferimento **xmlns** seguente nello schema XSD (XML Schema Definition Language). Per creare un file xsd <xref:System.Data.DataSet.WriteXmlSchema%2A> dalle tabelle di database, vedere o [Utilizzo dei dataset in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Di seguito è riportato uno schema con annotazioni di esempio che espone la tabella **Customers** del database **Northwind** con una relazione alla tabella **Orders** inclusa.  
  
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
  
 Nell'esempio di codice riportato di seguito viene utilizzato un **DataSet** fortemente tipizzato creato dallo schema di esempio. Ne usa <xref:System.Data.SqlClient.SqlDataAdapter> uno per popolare <xref:System.Data.SqlClient.SqlDataAdapter> la tabella **Customers** e un altro per popolare la tabella **Orders.** Il **DataSet** fortemente tipizzato definisce **DataRelations**.  
  
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
- [Dataset tipizzati](typed-datasets.md)
- [Oggetti DataSet, DataTable e DataView](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
