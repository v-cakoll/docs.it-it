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
# <a name="annotating-typed-datasets"></a><span data-ttu-id="74f39-102">Annotazione di dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="74f39-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="74f39-103">Le annotazioni consentono di modificare i nomi degli elementi nel <xref:System.Data.DataSet> tipizzato senza modificare lo schema sottostante.</span><span class="sxs-lookup"><span data-stu-id="74f39-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="74f39-104">La modifica dei nomi degli elementi nello schema sottostante causerebbe il **DataSet** tipizzato fare riferimento a oggetti che non esistono nell'origine dati, nonché perdere un riferimento agli oggetti presenti nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="74f39-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="74f39-105">Utilizzando le annotazioni, è possibile personalizzare i nomi degli oggetti nel **DataSet** tipizzato con nomi più significativi, rendendo il codice più leggibile e il **DataSet** tipizzato per i client da utilizzare, lasciando intatto lo schema sottostante.</span><span class="sxs-lookup"><span data-stu-id="74f39-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="74f39-106">Ad esempio, il seguente elemento dello schema per la tabella **Customers** del database **Northwind** comporterebbe un nome di oggetto **DataRow** denominato **CustomersRow** e un <xref:System.Data.DataRowCollection> nome **Customers**.</span><span class="sxs-lookup"><span data-stu-id="74f39-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="74f39-107">Un **nome DataRowCollection** di **Customers** è significativo nel codice client, ma un nome **DataRow** di **CustomersRow** è fuorviante perché è un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="74f39-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="74f39-108">Inoltre, negli scenari comuni, l'oggetto verrebbe indicato senza l'identificatore **di riga** e invece verrebbe semplicemente indicato come un oggetto **Customer.**</span><span class="sxs-lookup"><span data-stu-id="74f39-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="74f39-109">La soluzione consiste nell'annotare lo schema e identificare nuovi nomi per il **DataRow** e **DataRowCollection** oggetti.</span><span class="sxs-lookup"><span data-stu-id="74f39-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="74f39-110">Di seguito viene riportata una versione annotata dello schema precedente.</span><span class="sxs-lookup"><span data-stu-id="74f39-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="74f39-111">Se si specifica un valore **typedName** di **Customer,** verrà dato come risultato un nome di oggetto **DataRow** **Customer**.</span><span class="sxs-lookup"><span data-stu-id="74f39-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="74f39-112">Se si specifica un valore **typedPlural** di **Customers,** il nome **DataRowCollection** di **Customers**viene mantenuto.</span><span class="sxs-lookup"><span data-stu-id="74f39-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="74f39-113">Nella seguente tabella sono indicate le annotazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="74f39-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="74f39-114">Annotazione</span><span class="sxs-lookup"><span data-stu-id="74f39-114">Annotation</span></span>|<span data-ttu-id="74f39-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74f39-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="74f39-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="74f39-116">**typedName**</span></span>|<span data-ttu-id="74f39-117">Nome dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="74f39-117">Name of the object.</span></span>|  
|<span data-ttu-id="74f39-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="74f39-118">**typedPlural**</span></span>|<span data-ttu-id="74f39-119">Nome della raccolta di oggetti.</span><span class="sxs-lookup"><span data-stu-id="74f39-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="74f39-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="74f39-120">**typedParent**</span></span>|<span data-ttu-id="74f39-121">Nome dell'oggetto quando si fa riferimento a tale oggetto in una relazione padre.</span><span class="sxs-lookup"><span data-stu-id="74f39-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="74f39-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="74f39-122">**typedChildren**</span></span>|<span data-ttu-id="74f39-123">Nome del metodo per la restituzione di oggetti da una relazione figlio.</span><span class="sxs-lookup"><span data-stu-id="74f39-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="74f39-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="74f39-124">**nullValue**</span></span>|<span data-ttu-id="74f39-125">Valore se il valore sottostante è **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="74f39-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="74f39-126">Vedere la tabella seguente per le annotazioni **nullValue.See** the following table for nullValue annotations.</span><span class="sxs-lookup"><span data-stu-id="74f39-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="74f39-127">Il valore predefinito è **_throw**.</span><span class="sxs-lookup"><span data-stu-id="74f39-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="74f39-128">Nella tabella seguente vengono illustrati i valori che possono essere specificati per l'annotazione **nullValue.**</span><span class="sxs-lookup"><span data-stu-id="74f39-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="74f39-129">Valore nullValue</span><span class="sxs-lookup"><span data-stu-id="74f39-129">nullValue Value</span></span>|<span data-ttu-id="74f39-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="74f39-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="74f39-131">*Valore di sostituzione*</span><span class="sxs-lookup"><span data-stu-id="74f39-131">*Replacement Value*</span></span>|<span data-ttu-id="74f39-132">Specifica il valore da restituire.</span><span class="sxs-lookup"><span data-stu-id="74f39-132">Specify a value to be returned.</span></span> <span data-ttu-id="74f39-133">È necessario che il valore restituito corrisponda al tipo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="74f39-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="74f39-134">Usare ad esempio `nullValue="0"` per restituire 0 per i campi integer null.</span><span class="sxs-lookup"><span data-stu-id="74f39-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="74f39-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="74f39-135">**_throw**</span></span>|<span data-ttu-id="74f39-136">Generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="74f39-136">Throw an exception.</span></span> <span data-ttu-id="74f39-137">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="74f39-137">This is the default.</span></span>|  
|<span data-ttu-id="74f39-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="74f39-138">**_null**</span></span>|<span data-ttu-id="74f39-139">Consente di restituire un riferimento null o di generare un'eccezione se viene rilevato un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="74f39-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="74f39-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="74f39-140">**_empty**</span></span>|<span data-ttu-id="74f39-141">Per le stringhe, restituire **String.Empty**, in caso contrario restituire un oggetto creato da un costruttore vuoto.</span><span class="sxs-lookup"><span data-stu-id="74f39-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="74f39-142">Se viene rilevato un tipo primitivo, consente di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="74f39-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="74f39-143">Nella tabella seguente vengono illustrati i valori predefiniti per gli oggetti in un **DataSet** tipizzato e le annotazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="74f39-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="74f39-144">Oggetto/Metodo/Evento</span><span class="sxs-lookup"><span data-stu-id="74f39-144">Object/Method/Event</span></span>|<span data-ttu-id="74f39-145">Predefinito</span><span class="sxs-lookup"><span data-stu-id="74f39-145">Default</span></span>|<span data-ttu-id="74f39-146">Annotazione</span><span class="sxs-lookup"><span data-stu-id="74f39-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="74f39-147">**Datatable**</span><span class="sxs-lookup"><span data-stu-id="74f39-147">**DataTable**</span></span>|<span data-ttu-id="74f39-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="74f39-148">TableNameDataTable</span></span>|<span data-ttu-id="74f39-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="74f39-149">typedPlural</span></span>|  
|<span data-ttu-id="74f39-150">**DataTable** Metodi</span><span class="sxs-lookup"><span data-stu-id="74f39-150">**DataTable** Methods</span></span>|<span data-ttu-id="74f39-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="74f39-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="74f39-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="74f39-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="74f39-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="74f39-153">DeleteTableNameRow</span></span>|<span data-ttu-id="74f39-154">typedName</span><span class="sxs-lookup"><span data-stu-id="74f39-154">typedName</span></span>|  
|<span data-ttu-id="74f39-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="74f39-155">**DataRowCollection**</span></span>|<span data-ttu-id="74f39-156">TableName</span><span class="sxs-lookup"><span data-stu-id="74f39-156">TableName</span></span>|<span data-ttu-id="74f39-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="74f39-157">typedPlural</span></span>|  
|<span data-ttu-id="74f39-158">**Datarow**</span><span class="sxs-lookup"><span data-stu-id="74f39-158">**DataRow**</span></span>|<span data-ttu-id="74f39-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="74f39-159">TableNameRow</span></span>|<span data-ttu-id="74f39-160">typedName</span><span class="sxs-lookup"><span data-stu-id="74f39-160">typedName</span></span>|  
|<span data-ttu-id="74f39-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="74f39-161">**DataColumn**</span></span>|<span data-ttu-id="74f39-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="74f39-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="74f39-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="74f39-163">DataRow.ColumnName</span></span>|<span data-ttu-id="74f39-164">typedName</span><span class="sxs-lookup"><span data-stu-id="74f39-164">typedName</span></span>|  
|<span data-ttu-id="74f39-165">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="74f39-165">**Property**</span></span>|<span data-ttu-id="74f39-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="74f39-166">PropertyName</span></span>|<span data-ttu-id="74f39-167">typedName</span><span class="sxs-lookup"><span data-stu-id="74f39-167">typedName</span></span>|  
|<span data-ttu-id="74f39-168">**Bambino** Funzione</span><span class="sxs-lookup"><span data-stu-id="74f39-168">**Child** Accessor</span></span>|<span data-ttu-id="74f39-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="74f39-169">GetChildTableNameRows</span></span>|<span data-ttu-id="74f39-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="74f39-170">typedChildren</span></span>|  
|<span data-ttu-id="74f39-171">**Genitore** Funzione</span><span class="sxs-lookup"><span data-stu-id="74f39-171">**Parent** Accessor</span></span>|<span data-ttu-id="74f39-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="74f39-172">TableNameRow</span></span>|<span data-ttu-id="74f39-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="74f39-173">typedParent</span></span>|  
|<span data-ttu-id="74f39-174">**DataSet (Gruppo di dati)** Eventi</span><span class="sxs-lookup"><span data-stu-id="74f39-174">**DataSet** Events</span></span>|<span data-ttu-id="74f39-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="74f39-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="74f39-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="74f39-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="74f39-177">typedName</span><span class="sxs-lookup"><span data-stu-id="74f39-177">typedName</span></span>|  
  
 <span data-ttu-id="74f39-178">Per utilizzare le annotazioni **di DataSet** tipizzate, è necessario includere il riferimento **xmlns** seguente nello schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="74f39-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="74f39-179">Per creare un file xsd <xref:System.Data.DataSet.WriteXmlSchema%2A> dalle tabelle di database, vedere o [Utilizzo dei dataset in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="74f39-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="74f39-180">Di seguito è riportato uno schema con annotazioni di esempio che espone la tabella **Customers** del database **Northwind** con una relazione alla tabella **Orders** inclusa.</span><span class="sxs-lookup"><span data-stu-id="74f39-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="74f39-181">Nell'esempio di codice riportato di seguito viene utilizzato un **DataSet** fortemente tipizzato creato dallo schema di esempio.</span><span class="sxs-lookup"><span data-stu-id="74f39-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="74f39-182">Ne usa <xref:System.Data.SqlClient.SqlDataAdapter> uno per popolare <xref:System.Data.SqlClient.SqlDataAdapter> la tabella **Customers** e un altro per popolare la tabella **Orders.**</span><span class="sxs-lookup"><span data-stu-id="74f39-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="74f39-183">Il **DataSet** fortemente tipizzato definisce **DataRelations**.</span><span class="sxs-lookup"><span data-stu-id="74f39-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="74f39-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74f39-184">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="74f39-185">Dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="74f39-185">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="74f39-186">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="74f39-186">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="74f39-187">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="74f39-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
