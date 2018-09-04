---
title: Annotazione di dataset tipizzati
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: c66a11e0662cd007797243c136ec0617ce5be47c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43513147"
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="bdde4-102">Annotazione di dataset tipizzati</span><span class="sxs-lookup"><span data-stu-id="bdde4-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="bdde4-103">Le annotazioni consentono di modificare i nomi degli elementi nel <xref:System.Data.DataSet> tipizzato senza modificare lo schema sottostante.</span><span class="sxs-lookup"><span data-stu-id="bdde4-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="bdde4-104">Modifica i nomi degli elementi dello schema sottostante causerebbe l'oggetto tipizzato **set di dati** per fare riferimento a oggetti che non esiste nell'origine dati, nonché perderebbe un riferimento agli oggetti che sono presenti nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="bdde4-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="bdde4-105">Uso delle annotazioni, è possibile personalizzare i nomi degli oggetti in tipizzato **set di dati** con nomi più significativi, rendendo più leggibile codice e tipizzato **DataSet** più semplice per i client da usare, lasciando intatto lo schema sottostante.</span><span class="sxs-lookup"><span data-stu-id="bdde4-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="bdde4-106">Ad esempio, l'elemento schema seguente per il **clienti** tabella del **Northwind** database comporta la un **DataRow** il nome dell'oggetto  **CustomersRow** e una <xref:System.Data.DataRowCollection> denominate **clienti**.</span><span class="sxs-lookup"><span data-stu-id="bdde4-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="bdde4-107">Un **DataRowCollection** nome del **clienti** risulta significativo nel codice client, ma un **DataRow** nome del **CustomersRow** è fuorviante perché è un singolo oggetto.</span><span class="sxs-lookup"><span data-stu-id="bdde4-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="bdde4-108">Inoltre, in comune scenari, l'oggetto si riferisce al senza il **riga** identificatore e invece sarebbe riferimento semplicemente come un **cliente** oggetto.</span><span class="sxs-lookup"><span data-stu-id="bdde4-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="bdde4-109">La soluzione consiste nell'annotare lo schema e identificare nuovi nomi per il **DataRow** e **DataRowCollection** oggetti.</span><span class="sxs-lookup"><span data-stu-id="bdde4-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="bdde4-110">Di seguito viene riportata una versione annotata dello schema precedente.</span><span class="sxs-lookup"><span data-stu-id="bdde4-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="bdde4-111">Specifica un **typedName** pari a **Customer** comporterà un **DataRow** il nome dell'oggetto **cliente**.</span><span class="sxs-lookup"><span data-stu-id="bdde4-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="bdde4-112">Che specifica un **typedPlural** pari a **clienti** mantiene il **DataRowCollection** nome del **clienti**.</span><span class="sxs-lookup"><span data-stu-id="bdde4-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="bdde4-113">Nella seguente tabella sono indicate le annotazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="bdde4-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="bdde4-114">Annotazione</span><span class="sxs-lookup"><span data-stu-id="bdde4-114">Annotation</span></span>|<span data-ttu-id="bdde4-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdde4-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="bdde4-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="bdde4-116">**typedName**</span></span>|<span data-ttu-id="bdde4-117">Nome dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="bdde4-117">Name of the object.</span></span>|  
|<span data-ttu-id="bdde4-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="bdde4-118">**typedPlural**</span></span>|<span data-ttu-id="bdde4-119">Nome della raccolta di oggetti.</span><span class="sxs-lookup"><span data-stu-id="bdde4-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="bdde4-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="bdde4-120">**typedParent**</span></span>|<span data-ttu-id="bdde4-121">Nome dell'oggetto quando si fa riferimento a tale oggetto in una relazione padre.</span><span class="sxs-lookup"><span data-stu-id="bdde4-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="bdde4-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="bdde4-122">**typedChildren**</span></span>|<span data-ttu-id="bdde4-123">Nome del metodo per la restituzione di oggetti da una relazione figlio.</span><span class="sxs-lookup"><span data-stu-id="bdde4-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="bdde4-124">**nullValue**</span><span class="sxs-lookup"><span data-stu-id="bdde4-124">**nullValue**</span></span>|<span data-ttu-id="bdde4-125">Valore se il valore sottostante è **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="bdde4-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="bdde4-126">Vedere la tabella seguente per **nullValue** annotazioni.</span><span class="sxs-lookup"><span data-stu-id="bdde4-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="bdde4-127">Il valore predefinito è **throw**.</span><span class="sxs-lookup"><span data-stu-id="bdde4-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="bdde4-128">Nella tabella seguente mostra i valori che possono essere specificati per il **nullValue** annotazione.</span><span class="sxs-lookup"><span data-stu-id="bdde4-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="bdde4-129">Valore nullValue</span><span class="sxs-lookup"><span data-stu-id="bdde4-129">nullValue Value</span></span>|<span data-ttu-id="bdde4-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdde4-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="bdde4-131">*Valore di sostituzione*</span><span class="sxs-lookup"><span data-stu-id="bdde4-131">*Replacement Value*</span></span>|<span data-ttu-id="bdde4-132">Specifica il valore da restituire.</span><span class="sxs-lookup"><span data-stu-id="bdde4-132">Specify a value to be returned.</span></span> <span data-ttu-id="bdde4-133">È necessario che il valore restituito corrisponda al tipo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="bdde4-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="bdde4-134">Usare ad esempio `nullValue="0"` per restituire 0 per i campi integer null.</span><span class="sxs-lookup"><span data-stu-id="bdde4-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="bdde4-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="bdde4-135">**_throw**</span></span>|<span data-ttu-id="bdde4-136">Generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bdde4-136">Throw an exception.</span></span> <span data-ttu-id="bdde4-137">Questa è l'impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bdde4-137">This is the default.</span></span>|  
|<span data-ttu-id="bdde4-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="bdde4-138">**_null**</span></span>|<span data-ttu-id="bdde4-139">Consente di restituire un riferimento null o di generare un'eccezione se viene rilevato un tipo primitivo.</span><span class="sxs-lookup"><span data-stu-id="bdde4-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="bdde4-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="bdde4-140">**_empty**</span></span>|<span data-ttu-id="bdde4-141">Per le stringhe, restituire **String. Empty**, in caso contrario, restituisce un oggetto creato da un costruttore vuoto.</span><span class="sxs-lookup"><span data-stu-id="bdde4-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="bdde4-142">Se viene rilevato un tipo primitivo, consente di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="bdde4-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="bdde4-143">La tabella seguente mostra i valori predefiniti per gli oggetti in un oggetto tipizzato **set di dati** e le annotazioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="bdde4-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="bdde4-144">Oggetto/Metodo/Evento</span><span class="sxs-lookup"><span data-stu-id="bdde4-144">Object/Method/Event</span></span>|<span data-ttu-id="bdde4-145">Default</span><span class="sxs-lookup"><span data-stu-id="bdde4-145">Default</span></span>|<span data-ttu-id="bdde4-146">Annotazione</span><span class="sxs-lookup"><span data-stu-id="bdde4-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="bdde4-147">**Oggetto DataTable**</span><span class="sxs-lookup"><span data-stu-id="bdde4-147">**DataTable**</span></span>|<span data-ttu-id="bdde4-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="bdde4-148">TableNameDataTable</span></span>|<span data-ttu-id="bdde4-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="bdde4-149">typedPlural</span></span>|  
|<span data-ttu-id="bdde4-150">**DataTable** metodi</span><span class="sxs-lookup"><span data-stu-id="bdde4-150">**DataTable** Methods</span></span>|<span data-ttu-id="bdde4-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="bdde4-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="bdde4-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="bdde4-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="bdde4-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="bdde4-153">DeleteTableNameRow</span></span>|<span data-ttu-id="bdde4-154">typedName</span><span class="sxs-lookup"><span data-stu-id="bdde4-154">typedName</span></span>|  
|<span data-ttu-id="bdde4-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="bdde4-155">**DataRowCollection**</span></span>|<span data-ttu-id="bdde4-156">TableName</span><span class="sxs-lookup"><span data-stu-id="bdde4-156">TableName</span></span>|<span data-ttu-id="bdde4-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="bdde4-157">typedPlural</span></span>|  
|<span data-ttu-id="bdde4-158">**DataRow**</span><span class="sxs-lookup"><span data-stu-id="bdde4-158">**DataRow**</span></span>|<span data-ttu-id="bdde4-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="bdde4-159">TableNameRow</span></span>|<span data-ttu-id="bdde4-160">typedName</span><span class="sxs-lookup"><span data-stu-id="bdde4-160">typedName</span></span>|  
|<span data-ttu-id="bdde4-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="bdde4-161">**DataColumn**</span></span>|<span data-ttu-id="bdde4-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="bdde4-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="bdde4-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="bdde4-163">DataRow.ColumnName</span></span>|<span data-ttu-id="bdde4-164">typedName</span><span class="sxs-lookup"><span data-stu-id="bdde4-164">typedName</span></span>|  
|<span data-ttu-id="bdde4-165">**Property**</span><span class="sxs-lookup"><span data-stu-id="bdde4-165">**Property**</span></span>|<span data-ttu-id="bdde4-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="bdde4-166">PropertyName</span></span>|<span data-ttu-id="bdde4-167">typedName</span><span class="sxs-lookup"><span data-stu-id="bdde4-167">typedName</span></span>|  
|<span data-ttu-id="bdde4-168">**Figlio** della funzione di accesso</span><span class="sxs-lookup"><span data-stu-id="bdde4-168">**Child** Accessor</span></span>|<span data-ttu-id="bdde4-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="bdde4-169">GetChildTableNameRows</span></span>|<span data-ttu-id="bdde4-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="bdde4-170">typedChildren</span></span>|  
|<span data-ttu-id="bdde4-171">**Padre** della funzione di accesso</span><span class="sxs-lookup"><span data-stu-id="bdde4-171">**Parent** Accessor</span></span>|<span data-ttu-id="bdde4-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="bdde4-172">TableNameRow</span></span>|<span data-ttu-id="bdde4-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="bdde4-173">typedParent</span></span>|  
|<span data-ttu-id="bdde4-174">**Set di dati** eventi</span><span class="sxs-lookup"><span data-stu-id="bdde4-174">**DataSet** Events</span></span>|<span data-ttu-id="bdde4-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="bdde4-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="bdde4-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="bdde4-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="bdde4-177">typedName</span><span class="sxs-lookup"><span data-stu-id="bdde4-177">typedName</span></span>|  
  
 <span data-ttu-id="bdde4-178">Usare tipizzata **set di dati** annotazioni, è necessario includere quanto segue **xmlns** riferimento nello schema XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="bdde4-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="bdde4-179">(Per creare uno schema xsd dalle tabelle di database, vedere <xref:System.Data.DataSet.WriteXmlSchema%2A> oppure [utilizzo di dataset in Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span><span class="sxs-lookup"><span data-stu-id="bdde4-179">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).</span></span>  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="bdde4-180">Di seguito è riportato un esempio di schema con annotazioni che espone il **clienti** tabella del **Northwind** database con una relazione con il **ordini** tabella inclusa.</span><span class="sxs-lookup"><span data-stu-id="bdde4-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
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
  
 <span data-ttu-id="bdde4-181">Esempio di codice seguente usa un oggetto fortemente tipizzato **set di dati** creata dallo schema di esempio.</span><span class="sxs-lookup"><span data-stu-id="bdde4-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="bdde4-182">Usa una <xref:System.Data.SqlClient.SqlDataAdapter> per popolare le **clienti** tabella e un altro <xref:System.Data.SqlClient.SqlDataAdapter> per popolare il **ordini** tabella.</span><span class="sxs-lookup"><span data-stu-id="bdde4-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="bdde4-183">L'oggetto fortemente tipizzato **set di dati** definisce le **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="bdde4-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bdde4-184">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdde4-184">See Also</span></span>  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [<span data-ttu-id="bdde4-185">Set di dati tipizzati</span><span class="sxs-lookup"><span data-stu-id="bdde4-185">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [<span data-ttu-id="bdde4-186">Oggetti DataSet, DataTable e DataView</span><span class="sxs-lookup"><span data-stu-id="bdde4-186">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="bdde4-187">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="bdde4-187">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
