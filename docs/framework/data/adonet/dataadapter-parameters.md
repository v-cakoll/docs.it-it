---
title: Parametri DataAdapter
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f21e6aba-b76d-46ad-a83e-2ad8e0af1e12
ms.openlocfilehash: 9954570dcf33c5eea4dcccf880de2c307de0aeca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151546"
---
# <a name="dataadapter-parameters"></a><span data-ttu-id="886a1-102">Parametri DataAdapter</span><span class="sxs-lookup"><span data-stu-id="886a1-102">DataAdapter Parameters</span></span>
<span data-ttu-id="886a1-103"><xref:System.Data.Common.DbDataAdapter> dispone di quattro proprietà che consentono di recuperare e aggiornare i dati dell'origine dati. La proprietà <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> restituisce i dati dall'origine dati, mentre le proprietà <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A>, <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> e <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> vengono usate per gestire le modifiche nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="886a1-103">The <xref:System.Data.Common.DbDataAdapter> has four properties that are used to retrieve data from and update data to the data source: the <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A> property returns data from the data source; and the <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> , <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A>, and <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> properties are used to manage changes at the data source.</span></span> <span data-ttu-id="886a1-104">La proprietà `SelectCommand` deve essere impostata prima di chiamare il metodo `Fill` di `DataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="886a1-104">The `SelectCommand` property must be set before you call the `Fill` method of the `DataAdapter`.</span></span> <span data-ttu-id="886a1-105">È necessario impostare la proprietà `InsertCommand`, `UpdateCommand` o `DeleteCommand` prima di chiamare il metodo `Update` di `DataAdapter` a seconda delle modifiche apportate ai dati in <xref:System.Data.DataTable>,</span><span class="sxs-lookup"><span data-stu-id="886a1-105">The `InsertCommand`, `UpdateCommand`, or `DeleteCommand` properties must be set before the `Update` method of the `DataAdapter` is called, depending on what changes were made to the data in the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="886a1-106">Se ad esempio sono state aggiunte righe, è necessario impostare la proprietà `InsertCommand` prima di chiamare `Update`.</span><span class="sxs-lookup"><span data-stu-id="886a1-106">For example, if rows have been added, the `InsertCommand` must be set before you call `Update`.</span></span> <span data-ttu-id="886a1-107">Quando `Update` elabora una riga inserita, aggiornata o eliminata, `DataAdapter` usa la rispettiva proprietà `Command` per l'operazione.</span><span class="sxs-lookup"><span data-stu-id="886a1-107">When `Update` is processing an inserted, updated, or deleted row, the `DataAdapter` uses the respective `Command` property to process the action.</span></span> <span data-ttu-id="886a1-108">Le informazioni correnti sulla riga modificata vengono passate all'oggetto `Command` mediante la raccolta `Parameters`.</span><span class="sxs-lookup"><span data-stu-id="886a1-108">Current information about the modified row is passed to the `Command` object through the `Parameters` collection.</span></span>  
  
 <span data-ttu-id="886a1-109">Quando si aggiorna una riga nell'origine dati, si chiama l'istruzione UPDATE, che utilizza un identificatore univoco per identificare la riga nella tabella da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="886a1-109">When you update a row at the data source, you call the UPDATE statement, which uses a unique identifier to identify the row in the table to be updated.</span></span> <span data-ttu-id="886a1-110">In genere, il valore dell'identificatore univoco corrisponde a quello del campo di una chiave primaria.</span><span class="sxs-lookup"><span data-stu-id="886a1-110">The unique identifier is typically the value of a primary key field.</span></span> <span data-ttu-id="886a1-111">Nell'istruzione UPDATE vengono usati i parametri che contengono sia l'identificatore univoco che le colonne e i valori da aggiornare, come illustrato nell'istruzione Transact-SQL seguente.</span><span class="sxs-lookup"><span data-stu-id="886a1-111">The UPDATE statement uses parameters that contain both the unique identifier and the columns and values to be updated, as shown in the following Transact-SQL statement.</span></span>  
  
```sql
UPDATE Customers SET CompanyName = @CompanyName
  WHERE CustomerID = @CustomerID  
```  
  
> [!NOTE]
> <span data-ttu-id="886a1-112">La sintassi per i segnaposto dei parametri varia in base all'origine dati.</span><span class="sxs-lookup"><span data-stu-id="886a1-112">The syntax for parameter placeholders depends on the data source.</span></span> <span data-ttu-id="886a1-113">In questo esempio vengono mostrati i segnaposto per un'origine dati SQL Server.</span><span class="sxs-lookup"><span data-stu-id="886a1-113">This example shows placeholders for a SQL Server data source.</span></span> <span data-ttu-id="886a1-114">Per i parametri <xref:System.Data.OleDb> e <xref:System.Data.Odbc> vengono usati come segnaposto i punti interrogativi (?).</span><span class="sxs-lookup"><span data-stu-id="886a1-114">Use question mark (?) placeholders for <xref:System.Data.OleDb> and <xref:System.Data.Odbc> parameters.</span></span>  
  
 <span data-ttu-id="886a1-115">In questo esempio di `CompanyName` Visual Basic, il `@CompanyName` campo viene aggiornato `CustomerID` con il valore `@CustomerID` del parametro per la riga in cui è uguale al valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="886a1-115">In this Visual Basic example, the `CompanyName` field is updated with the value of the `@CompanyName` parameter for the row where `CustomerID` equals the value of the `@CustomerID` parameter.</span></span> <span data-ttu-id="886a1-116">I parametri recuperano informazioni dalla <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> riga <xref:System.Data.SqlClient.SqlParameter> modificata utilizzando la proprietà dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="886a1-116">The parameters retrieve information from the modified row using the <xref:System.Data.SqlClient.SqlParameter.SourceColumn%2A> property of the <xref:System.Data.SqlClient.SqlParameter> object.</span></span> <span data-ttu-id="886a1-117">Di seguito sono riportati i parametri della precedente istruzione UPDATE di esempio.</span><span class="sxs-lookup"><span data-stu-id="886a1-117">The following are the parameters for the previous sample UPDATE statement.</span></span> <span data-ttu-id="886a1-118">Nel codice si presuppone che la variabile `adapter` rappresenti un oggetto <xref:System.Data.SqlClient.SqlDataAdapter> valido.</span><span class="sxs-lookup"><span data-stu-id="886a1-118">The code assumes that the variable `adapter` represents a valid <xref:System.Data.SqlClient.SqlDataAdapter> object.</span></span>  
  
```vb
adapter.Parameters.Add( _  
  "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
Dim parameter As SqlParameter = _  
  adapter.UpdateCommand.Parameters.Add("@CustomerID", _  
  SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
```  
  
 <span data-ttu-id="886a1-119">Il metodo `Add` della raccolta `Parameters` accetta il nome del parametro, il tipo di dati, le dimensioni (se applicabili al tipo) e il nome dell'oggetto <xref:System.Data.Common.DbParameter.SourceColumn%2A> da `DataTable`.</span><span class="sxs-lookup"><span data-stu-id="886a1-119">The `Add` method of the `Parameters` collection takes the name of the parameter, the data type, the size (if applicable to the type), and the name of the <xref:System.Data.Common.DbParameter.SourceColumn%2A> from the `DataTable`.</span></span> <span data-ttu-id="886a1-120">Notare che la proprietà <xref:System.Data.Common.DbParameter.SourceVersion%2A> del parametro `@CustomerID` è impostata su `Original`.</span><span class="sxs-lookup"><span data-stu-id="886a1-120">Notice that the <xref:System.Data.Common.DbParameter.SourceVersion%2A> of the `@CustomerID` parameter is set to `Original`.</span></span> <span data-ttu-id="886a1-121">Questo valore assicura che l'aggiornamento della riga esistente nell'origine dati venga eseguito se il valore della colonna o delle colonne identificative è stato cambiato nell'oggetto <xref:System.Data.DataRow> modificato.</span><span class="sxs-lookup"><span data-stu-id="886a1-121">This guarantees that the existing row in the data source is updated if the value of the identifying column or columns has been changed in the modified <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="886a1-122">In questo caso il valore `Original` della riga corrisponde al valore corrente nell'origine dati e il valore `Current` della riga contiene il valore aggiornato.</span><span class="sxs-lookup"><span data-stu-id="886a1-122">In that case, the `Original` row value would match the current value at the data source, and the `Current` row value would contain the updated value.</span></span> <span data-ttu-id="886a1-123">`SourceVersion` non è impostato per il parametro `@CompanyName`, pertanto verrà usato il valore di riga `Current` predefinito.</span><span class="sxs-lookup"><span data-stu-id="886a1-123">The `SourceVersion` for the `@CompanyName` parameter is not set and uses the default, `Current` row value.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="886a1-124">Per entrambe `Fill` le `DataAdapter` operazioni `Get` di `DataReader`e i metodi del tipo .NET Framework viene dedotto dal tipo restituito dal provider di dati .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="886a1-124">For both the `Fill` operations of the `DataAdapter` and the `Get` methods of the `DataReader`, the .NET Framework type is inferred from the type returned from the .NET Framework data provider.</span></span> <span data-ttu-id="886a1-125">I tipi e i metodi delle funzioni di accesso .NET Framework dedotti per i tipi di dati di Microsoft SQL Server, OLE DB e ODBC sono descritti in Mapping dei tipi di dati [in ADO.NET](data-type-mappings-in-ado-net.md).</span><span class="sxs-lookup"><span data-stu-id="886a1-125">The inferred .NET Framework types and accessor methods for Microsoft SQL Server, OLE DB, and ODBC data types are described in [Data Type Mappings in ADO.NET](data-type-mappings-in-ado-net.md).</span></span>  
  
## <a name="parametersourcecolumn-parametersourceversion"></a><span data-ttu-id="886a1-126">Parameter.SourceColumn e Parameter.SourceVersion</span><span class="sxs-lookup"><span data-stu-id="886a1-126">Parameter.SourceColumn, Parameter.SourceVersion</span></span>  
 <span data-ttu-id="886a1-127">È possibile passare `SourceColumn` e `SourceVersion` come argomenti del costruttore `Parameter` o impostarli come proprietà di un oggetto `Parameter` esistente.</span><span class="sxs-lookup"><span data-stu-id="886a1-127">The `SourceColumn` and `SourceVersion` may be passed as arguments to the `Parameter` constructor, or set as properties of an existing `Parameter`.</span></span> <span data-ttu-id="886a1-128">`SourceColumn` è il nome dell'oggetto <xref:System.Data.DataColumn> derivato da <xref:System.Data.DataRow> in cui viene recuperato il valore di `Parameter`.</span><span class="sxs-lookup"><span data-stu-id="886a1-128">The `SourceColumn` is the name of the <xref:System.Data.DataColumn> from the <xref:System.Data.DataRow> where the value of the `Parameter` will be retrieved.</span></span> <span data-ttu-id="886a1-129">`SourceVersion` specifica la versione di `DataRow` usata da `DataAdapter` per recuperare il valore.</span><span class="sxs-lookup"><span data-stu-id="886a1-129">The `SourceVersion` specifies the `DataRow` version that the `DataAdapter` uses to retrieve the value.</span></span>  
  
 <span data-ttu-id="886a1-130">Nella tabella seguente sono elencati i valori di enumerazione <xref:System.Data.DataRowVersion> disponibili per l'uso con `SourceVersion`.</span><span class="sxs-lookup"><span data-stu-id="886a1-130">The following table shows the <xref:System.Data.DataRowVersion> enumeration values available for use with `SourceVersion`.</span></span>  
  
|<span data-ttu-id="886a1-131">Enumerazione DataRowVersion</span><span class="sxs-lookup"><span data-stu-id="886a1-131">DataRowVersion Enumeration</span></span>|<span data-ttu-id="886a1-132">Descrizione</span><span class="sxs-lookup"><span data-stu-id="886a1-132">Description</span></span>|  
|--------------------------------|-----------------|  
|`Current`|<span data-ttu-id="886a1-133">Il parametro usa il valore corrente della colonna.</span><span class="sxs-lookup"><span data-stu-id="886a1-133">The parameter uses the current value of the column.</span></span> <span data-ttu-id="886a1-134">Questa è la modalità predefinita.</span><span class="sxs-lookup"><span data-stu-id="886a1-134">This is the default.</span></span>|  
|`Default`|<span data-ttu-id="886a1-135">Il parametro usa il valore `DefaultValue` della colonna.</span><span class="sxs-lookup"><span data-stu-id="886a1-135">The parameter uses the `DefaultValue` of the column.</span></span>|  
|`Original`|<span data-ttu-id="886a1-136">Il parametro usa il valore originale della colonna.</span><span class="sxs-lookup"><span data-stu-id="886a1-136">The parameter uses the original value of the column.</span></span>|  
|`Proposed`|<span data-ttu-id="886a1-137">Il parametro usa un valore proposto.</span><span class="sxs-lookup"><span data-stu-id="886a1-137">The parameter uses a proposed value.</span></span>|  
  
 <span data-ttu-id="886a1-138">Nell'esempio di codice `SqlClient` della sezione successiva viene definito un parametro per un oggetto <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> in cui la colonna `CustomerID` viene usata come `SourceColumn` per due parametri: `@CustomerID` (`SET CustomerID = @CustomerID`) e `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span><span class="sxs-lookup"><span data-stu-id="886a1-138">The `SqlClient` code example in the next section defines a parameter for an <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> in which the `CustomerID` column is used as a `SourceColumn` for two parameters: `@CustomerID` (`SET CustomerID = @CustomerID`), and `@OldCustomerID` (`WHERE CustomerID = @OldCustomerID`).</span></span> <span data-ttu-id="886a1-139">Il `@CustomerID` parametro viene utilizzato per aggiornare la `DataRow`colonna **CustomerID** al valore corrente nell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="886a1-139">The `@CustomerID` parameter is used to update the **CustomerID** column to the current value in the `DataRow`.</span></span> <span data-ttu-id="886a1-140">Di conseguenza, `CustomerID` `SourceColumn` viene `SourceVersion` `Current` utilizzato il con un di.</span><span class="sxs-lookup"><span data-stu-id="886a1-140">As a result, the `CustomerID` `SourceColumn` with a `SourceVersion` of `Current` is used.</span></span> <span data-ttu-id="886a1-141">Il `@OldCustomerID` parametro viene utilizzato per identificare la riga corrente nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="886a1-141">The `@OldCustomerID` parameter is used to identify the current row in the data source.</span></span> <span data-ttu-id="886a1-142">Poiché il valore della colonna corrispondente viene individuato nella versione `Original` della riga, verrà usato lo stesso oggetto `SourceColumn` (`CustomerID`) con `SourceVersion``Original`.</span><span class="sxs-lookup"><span data-stu-id="886a1-142">Because the matching column value is found in the `Original` version of the row, the same `SourceColumn` (`CustomerID`) with a `SourceVersion` of `Original` is used.</span></span>  
  
## <a name="working-with-sqlclient-parameters"></a><span data-ttu-id="886a1-143">Uso di parametri SqlClient</span><span class="sxs-lookup"><span data-stu-id="886a1-143">Working with SqlClient Parameters</span></span>  
 <span data-ttu-id="886a1-144">Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Data.SqlClient.SqlDataAdapter> e impostare <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> su <xref:System.Data.MissingSchemaAction.AddWithKey> per recuperare informazioni aggiuntive sullo schema dal database.</span><span class="sxs-lookup"><span data-stu-id="886a1-144">The following example demonstrates how to create a <xref:System.Data.SqlClient.SqlDataAdapter> and set the <xref:System.Data.Common.DataAdapter.MissingSchemaAction%2A> to <xref:System.Data.MissingSchemaAction.AddWithKey> in order to retrieve additional schema information from the database.</span></span> <span data-ttu-id="886a1-145">Vengono impostate le proprietà <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A> e <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> e i relativi oggetti <xref:System.Data.SqlClient.SqlParameter> corrispondenti vengono aggiunti alla raccolta <xref:System.Data.SqlClient.SqlCommand.Parameters%2A>.</span><span class="sxs-lookup"><span data-stu-id="886a1-145">The <xref:System.Data.SqlClient.SqlDataAdapter.SelectCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>, <xref:System.Data.SqlClient.SqlDataAdapter.UpdateCommand%2A>, and <xref:System.Data.SqlClient.SqlDataAdapter.DeleteCommand%2A> properties set and their corresponding <xref:System.Data.SqlClient.SqlParameter> objects added to the <xref:System.Data.SqlClient.SqlCommand.Parameters%2A> collection.</span></span> <span data-ttu-id="886a1-146">Il metodo restituisce un oggetto `SqlDataAdapter`.</span><span class="sxs-lookup"><span data-stu-id="886a1-146">The method returns a `SqlDataAdapter` object.</span></span>  
  
 [!code-csharp[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/CS/source.cs#1)]
 [!code-vb[Classic WebData SqlDataAdapter.SqlDataAdapter Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/Classic WebData SqlDataAdapter.SqlDataAdapter Example/VB/source.vb#1)]  
  
## <a name="oledb-parameter-placeholders"></a><span data-ttu-id="886a1-147">Segnaposti di parametri OleDb</span><span class="sxs-lookup"><span data-stu-id="886a1-147">OleDb Parameter Placeholders</span></span>  
 <span data-ttu-id="886a1-148">Per gli oggetti <xref:System.Data.OleDb.OleDbDataAdapter> e <xref:System.Data.Odbc.OdbcDataAdapter>, è necessario usare il punto interrogativo (?) come segnaposto per identificare i parametri.</span><span class="sxs-lookup"><span data-stu-id="886a1-148">For the <xref:System.Data.OleDb.OleDbDataAdapter> and <xref:System.Data.Odbc.OdbcDataAdapter> objects, you must use question mark (?) placeholders to identify the parameters.</span></span>  
  
```vb  
Dim selectSQL As String = _  
  "SELECT CustomerID, CompanyName FROM Customers " & _  
  "WHERE CountryRegion = ? AND City = ?"  
Dim insertSQL AS String = _  
  "INSERT INTO Customers (CustomerID, CompanyName) VALUES (?, ?)"  
Dim updateSQL AS String = _  
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " & _  
  WHERE CustomerID = ?"  
Dim deleteSQL As String = "DELETE FROM Customers WHERE CustomerID = ?"  
```  
  
```csharp  
string selectSQL =
  "SELECT CustomerID, CompanyName FROM Customers " +  
  "WHERE CountryRegion = ? AND City = ?";  
string insertSQL =
  "INSERT INTO Customers (CustomerID, CompanyName) " +  
  "VALUES (?, ?)";  
string updateSQL =
  "UPDATE Customers SET CustomerID = ?, CompanyName = ? " +  
  "WHERE CustomerID = ? ";  
string deleteSQL = "DELETE FROM Customers WHERE CustomerID = ?";  
```  
  
 <span data-ttu-id="886a1-149">Le istruzioni delle query con parametri definiscono i parametri di input e di output che è necessario creare.</span><span class="sxs-lookup"><span data-stu-id="886a1-149">The parameterized query statements define which input and output parameters must be created.</span></span> <span data-ttu-id="886a1-150">Per creare un parametro, usare il metodo `Parameters.Add` o il costruttore `Parameter` per specificare il nome della colonna, il tipo di dati e le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="886a1-150">To create a parameter, use the `Parameters.Add` method or the `Parameter` constructor to specify the column name, data type, and size.</span></span> <span data-ttu-id="886a1-151">Per tipi di dati intrinseci, ad esempio `Integer`, non è necessario includere le dimensioni oppure è possibile specificare quelle predefinite.</span><span class="sxs-lookup"><span data-stu-id="886a1-151">For intrinsic data types, such as `Integer`, you do not have to include the size, or you can specify the default size.</span></span>  
  
 <span data-ttu-id="886a1-152">Nell'esempio di codice seguente vengono creati i parametri per un'istruzione SQL e viene quindi compilato un `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="886a1-152">The following code example creates the parameters for a SQL statement and then fills a `DataSet`.</span></span>  
  
## <a name="oledb-example"></a><span data-ttu-id="886a1-153">Esempio di OleDb</span><span class="sxs-lookup"><span data-stu-id="886a1-153">OleDb Example</span></span>  
  
```vb  
' Assumes that connection is a valid OleDbConnection object.  
Dim adapter As OleDbDataAdapter = New OleDbDataAdapter
  
Dim selectCMD AS OleDbCommand = New OleDbCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add parameters and set values.  
selectCMD.Parameters.Add( _  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add( _  
  "@City", OleDbType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OleDbConnection object.  
OleDbDataAdapter adapter = new OleDbDataAdapter();  
  
OleDbCommand selectCMD = new OleDbCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
// Add parameters and set values.  
selectCMD.Parameters.Add(  
  "@CountryRegion", OleDbType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add(  
  "@City", OleDbType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
## <a name="odbc-parameters"></a><span data-ttu-id="886a1-154">Parametri Odbc</span><span class="sxs-lookup"><span data-stu-id="886a1-154">Odbc Parameters</span></span>  
  
```vb  
' Assumes that connection is a valid OdbcConnection object.  
Dim adapter As OdbcDataAdapter = New OdbcDataAdapter  
  
Dim selectCMD AS OdbcCommand = New OdbcCommand(selectSQL, connection)  
adapter.SelectCommand = selectCMD  
  
' Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK"  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London"  
  
Dim customers As DataSet = New DataSet  
adapter.Fill(customers, "Customers")  
```  
  
```csharp  
// Assumes that connection is a valid OdbcConnection object.  
OdbcDataAdapter adapter = new OdbcDataAdapter();  
  
OdbcCommand selectCMD = new OdbcCommand(selectSQL, connection);  
adapter.SelectCommand = selectCMD;  
  
//Add Parameters and set values.  
selectCMD.Parameters.Add("@CountryRegion", OdbcType.VarChar, 15).Value = "UK";  
selectCMD.Parameters.Add("@City", OdbcType.VarChar, 15).Value = "London";  
  
DataSet customers = new DataSet();  
adapter.Fill(customers, "Customers");  
```  
  
> [!NOTE]
> <span data-ttu-id="886a1-155">Se non viene fornito un nome di parametro per un parametro, al parametro viene assegnato un nome predefinito incrementale del parametro*N* *,* a partire da "Parametro1".</span><span class="sxs-lookup"><span data-stu-id="886a1-155">If a parameter name is not supplied for a parameter, the parameter is given an incremental default name of Parameter*N* *,* starting with "Parameter1".</span></span> <span data-ttu-id="886a1-156">È consigliabile evitare la convenzione di denominazione*Parametro N* quando si specifica un nome `ParameterCollection`di parametro, poiché il nome fornito potrebbe entrare in conflitto con un nome di parametro predefinito esistente nell'oggetto .</span><span class="sxs-lookup"><span data-stu-id="886a1-156">We recommend that you avoid the Parameter*N* naming convention when you supply a parameter name, because the name that you supply might conflict with an existing default parameter name in the `ParameterCollection`.</span></span> <span data-ttu-id="886a1-157">Se il nome fornito è già presente, viene generata un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="886a1-157">If the supplied name already exists, an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="886a1-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="886a1-158">See also</span></span>

- [<span data-ttu-id="886a1-159">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="886a1-159">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="886a1-160">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="886a1-160">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="886a1-161">Aggiornamento di origini dati con DataAdapter</span><span class="sxs-lookup"><span data-stu-id="886a1-161">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="886a1-162">Modifica di dati con stored procedure</span><span class="sxs-lookup"><span data-stu-id="886a1-162">Modifying Data with Stored Procedures</span></span>](modifying-data-with-stored-procedures.md)
- [<span data-ttu-id="886a1-163">Mapping dei tipi di dati in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="886a1-163">Data Type Mappings in ADO.NET</span></span>](data-type-mappings-in-ado-net.md)
- [<span data-ttu-id="886a1-164">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="886a1-164">ADO.NET Overview</span></span>](ado-net-overview.md)
