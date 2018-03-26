---
title: Annotazione di dataset tipizzati
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: cc09f3f9b43b70b7f9b302d7a9d75428b5a0e6c7
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2018
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="fb17c-102">Annotazione di dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="fb17c-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="fb17c-103">Le annotazioni consentono di modificare i nomi degli elementi nel <xref:System.Data.DataSet> tipizzato senza modificare lo schema sottostante.</span><span class="sxs-lookup"><span data-stu-id="fb17c-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="fb17c-104">Modifica i nomi degli elementi dello schema sottostante causerebbe l'oggetto tipizzato **DataSet** fare riferimento a oggetti che non esiste nell'origine dati, nonché perderebbe un riferimento per gli oggetti presenti nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="fb17c-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="fb17c-105">Utilizzo delle annotazioni, è possibile personalizzare i nomi degli oggetti in tipizzato **DataSet** con nomi più significativi, rendendo più leggibili codice e tipizzato **DataSet** più semplice per i client da utilizzare, lasciando schema sottostante intatto.</span><span class="sxs-lookup"><span data-stu-id="fb17c-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="fb17c-106">Ad esempio, il seguente elemento di schema per il **clienti** tabella del **Northwind** database comporta la un **DataRow** il nome dell'oggetto  **CustomersRow** e <xref:System.Data.DataRowCollection> denominato **clienti**.</span><span class="sxs-lookup"><span data-stu-id="fb17c-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="fb17c-107">A **DataRowCollection** nome di **clienti** è significativo nel codice client, ma un **DataRow** nome di **CustomersRow** è fuorviante perché si tratta di un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="fb17c-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="fb17c-108">In comune scenari, l'oggetto potrebbe essere indicato anche senza il **riga** identificatore e invece potrebbe essere semplicemente considerato come un **cliente** oggetto.</span><span class="sxs-lookup"><span data-stu-id="fb17c-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="fb17c-109">La soluzione consiste nell'annotare lo schema e identificare nuovi nomi per il **DataRow** e **DataRowCollection** oggetti.</span><span class="sxs-lookup"><span data-stu-id="fb17c-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="fb17c-110">Di seguito viene riportata una versione annotata dello schema precedente.</span><span class="sxs-lookup"><span data-stu-id="fb17c-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="fb17c-111">Specifica un **typedName** valore **cliente** comporterà un **DataRow** il nome dell'oggetto **cliente**.</span><span class="sxs-lookup"><span data-stu-id="fb17c-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="fb17c-112">Specifica un **typedPlural** valore **clienti** mantiene il **DataRowCollection** nome di **clienti**.</span><span class="sxs-lookup"><span data-stu-id="fb17c-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="fb17c-113">Nella seguente tabella sono indicate le annotazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="fb17c-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="fb17c-114">Annotazione</span><span class="sxs-lookup"><span data-stu-id="fb17c-114">Annotation</span></span>|<span data-ttu-id="fb17c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb17c-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="fb17c-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="fb17c-116">**typedName**</span></span>|<span data-ttu-id="fb17c-117">Nome dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="fb17c-117">Name of the object.</span></span>|  
|<span data-ttu-id="fb17c-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="fb17c-118">**typedPlural**</span></span>|<span data-ttu-id="fb17c-119">Nome della raccolta di oggetti.</span><span class="sxs-lookup"><span data-stu-id="fb17c-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="fb17c-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="fb17c-120">**typedParent**</span></span>|<span data-ttu-id="fb17c-121">Nome dell'oggetto quando si fa riferimento a tale oggetto in una relazione padre.</span><span class="sxs-lookup"><span data-stu-id="fb17c-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="fb17c-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="fb17c-122">**typedChildren**</span></span>|<span data-ttu-id="fb17c-123">Nome del metodo per la restituzione di oggetti da una relazione figlio.</span><span class="sxs-lookup"><span data-stu-id="fb17c-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="fb17c-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="fb17c-124">**nullValue**</span></span>|<span data-ttu-id="fb17c-125">Il valore se il valore sottostante è **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="fb17c-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="fb17c-126">Vedere la tabella seguente per **nullValue** annotazioni.</span><span class="sxs-lookup"><span data-stu-id="fb17c-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="fb17c-127">Il valore predefinito è **throw**.</span><span class="sxs-lookup"><span data-stu-id="fb17c-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="fb17c-128">Nella tabella seguente vengono illustrati i valori che possono essere specificati per il **nullValue** annotazione.</span><span class="sxs-lookup"><span data-stu-id="fb17c-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="fb17c-129">Valore nullValue</span><span class="sxs-lookup"><span data-stu-id="fb17c-129">nullValue Value</span></span>|<span data-ttu-id="fb17c-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fb17c-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="fb17c-131">*Valore di sostituzione*</span><span class="sxs-lookup"><span data-stu-id="fb17c-131">*Replacement Value*</span></span>|<span data-ttu-id="fb17c-132">Specifica il valore da restituire.</span><span class="sxs-lookup"><span data-stu-id="fb17c-132">Specify a value to be returned.</span></span> <span data-ttu-id="fb17c-133">È necessario che il valore restituito corrisponda al tipo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="fb17c-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="fb17c-134">Usare ad esempio `nullValue="0"` per restituire 0 per i campi integer null.</span><span class="sxs-lookup"><span data-stu-id="fb17c-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="fb17c-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="fb17c-135">**_throw**</span></span>|<span data-ttu-id="fb17c-136">Generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fb17c-136">Throw an exception.</span></span> <span data-ttu-id="fb17c-137">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="fb17c-137">This is the default.</span></span>|  
|<span data-ttu-id="fb17c-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="fb17c-138">**_null**</span></span>|<span data-ttu-id="fb17c-139">Consente di restituire un riferimento null o di generare un'eccezione se viene rilevato un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="fb17c-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="fb17c-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="fb17c-140">**_empty**</span></span>|<span data-ttu-id="fb17c-141">Per le stringhe, restituire **Empty**, in caso contrario, restituire un oggetto creato da un costruttore vuoto.</span><span class="sxs-lookup"><span data-stu-id="fb17c-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="fb17c-142">Se viene rilevato un tipo primitivo, consente di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="fb17c-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="fb17c-143">Nella tabella seguente mostra i valori predefiniti per gli oggetti in una classe tipizzata **DataSet** e le annotazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="fb17c-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="fb17c-144">Oggetto/Metodo/Evento</span><span class="sxs-lookup"><span data-stu-id="fb17c-144">Object/Method/Event</span></span>|<span data-ttu-id="fb17c-145">Default</span><span class="sxs-lookup"><span data-stu-id="fb17c-145">Default</span></span>|<span data-ttu-id="fb17c-146">Annotazione</span><span class="sxs-lookup"><span data-stu-id="fb17c-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="fb17c-147">**DataTable**</span><span class="sxs-lookup"><span data-stu-id="fb17c-147">**DataTable**</span></span>|<span data-ttu-id="fb17c-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="fb17c-148">TableNameDataTable</span></span>|<span data-ttu-id="fb17c-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="fb17c-149">typedPlural</span></span>|  
|<span data-ttu-id="fb17c-150">**DataTable** metodi</span><span class="sxs-lookup"><span data-stu-id="fb17c-150">**DataTable** Methods</span></span>|<span data-ttu-id="fb17c-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="fb17c-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="fb17c-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="fb17c-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="fb17c-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="fb17c-153">DeleteTableNameRow</span></span>|<span data-ttu-id="fb17c-154">typedName</span><span class="sxs-lookup"><span data-stu-id="fb17c-154">typedName</span></span>|  
|<span data-ttu-id="fb17c-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="fb17c-155">**DataRowCollection**</span></span>|<span data-ttu-id="fb17c-156">TableName</span><span class="sxs-lookup"><span data-stu-id="fb17c-156">TableName</span></span>|<span data-ttu-id="fb17c-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="fb17c-157">typedPlural</span></span>|  
|<span data-ttu-id="fb17c-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="fb17c-158">**DataRow**</span></span>|<span data-ttu-id="fb17c-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="fb17c-159">TableNameRow</span></span>|<span data-ttu-id="fb17c-160">typedName</span><span class="sxs-lookup"><span data-stu-id="fb17c-160">typedName</span></span>|  
|<span data-ttu-id="fb17c-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="fb17c-161">**DataColumn**</span></span>|<span data-ttu-id="fb17c-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="fb17c-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="fb17c-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="fb17c-163">DataRow.ColumnName</span></span>|<span data-ttu-id="fb17c-164">typedName</span><span class="sxs-lookup"><span data-stu-id="fb17c-164">typedName</span></span>|  
|<span data-ttu-id="fb17c-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="fb17c-165">**Property**</span></span>|<span data-ttu-id="fb17c-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="fb17c-166">PropertyName</span></span>|<span data-ttu-id="fb17c-167">typedName</span><span class="sxs-lookup"><span data-stu-id="fb17c-167">typedName</span></span>|  
|<span data-ttu-id="fb17c-168">**Figlio** della funzione di accesso</span><span class="sxs-lookup"><span data-stu-id="fb17c-168">**Child** Accessor</span></span>|<span data-ttu-id="fb17c-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="fb17c-169">GetChildTableNameRows</span></span>|<span data-ttu-id="fb17c-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="fb17c-170">typedChildren</span></span>|  
|<span data-ttu-id="fb17c-171">**Padre** della funzione di accesso</span><span class="sxs-lookup"><span data-stu-id="fb17c-171">**Parent** Accessor</span></span>|<span data-ttu-id="fb17c-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="fb17c-172">TableNameRow</span></span>|<span data-ttu-id="fb17c-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="fb17c-173">typedParent</span></span>|  
|<span data-ttu-id="fb17c-174">**Set di dati** eventi</span><span class="sxs-lookup"><span data-stu-id="fb17c-174">**DataSet** Events</span></span>|<span data-ttu-id="fb17c-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="fb17c-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="fb17c-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="fb17c-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="fb17c-177">typedName</span><span class="sxs-lookup"><span data-stu-id="fb17c-177">typedName</span></span>|  
  
 <span data-ttu-id="fb17c-178">Utilizzare tipizzati **DataSet** annotazioni, è necessario includere il seguente **xmlns** riferimento nello schema XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="fb17c-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="fb17c-179">(Per creare un file xsd dalle tabelle di database, vedere <xref:System.Data.DataSet.WriteXmlSchema%2A> o [uso di dataset in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="fb17c-179">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="fb17c-180">Di seguito è riportato un esempio di schema con annotazioni che espone il **clienti** tabella il **Northwind** database con una relazione con il **ordini** tabella inclusa.</span><span class="sxs-lookup"><span data-stu-id="fb17c-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="fb17c-181">L'esempio di codice seguente viene utilizzato un oggetto fortemente tipizzato **DataSet** creato dallo schema di esempio.</span><span class="sxs-lookup"><span data-stu-id="fb17c-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="fb17c-182">Viene utilizzato uno <xref:System.Data.SqlClient.SqlDataAdapter> per popolare il **clienti** tabella e un altro <xref:System.Data.SqlClient.SqlDataAdapter> per popolare il **ordini** tabella.</span><span class="sxs-lookup"><span data-stu-id="fb17c-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="fb17c-183">L'oggetto fortemente tipizzato **DataSet** definisce il **DataRelations**.</span><span class="sxs-lookup"><span data-stu-id="fb17c-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
    customers.Customers.NewCustomeromer()  
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
    customers.Customers.NewCustomeromer();  
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
  
## <a name="see-also"></a><span data-ttu-id="fb17c-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fb17c-184">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="fb17c-185">Set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="fb17c-185">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="fb17c-186">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="fb17c-186">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="fb17c-187">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="fb17c-187">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
