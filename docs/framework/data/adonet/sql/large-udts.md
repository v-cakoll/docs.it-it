---
title: Tipi di grandi dimensioni definiti dall'utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 8b2f195b2cb4c365693dc0f250a577a93cf25eee
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181532"
---
# <a name="large-udts"></a><span data-ttu-id="684b1-102">Tipi di grandi dimensioni definiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="684b1-102">Large UDTs</span></span>
<span data-ttu-id="684b1-103">I tipi definiti dall'utente (UDT) consentono agli sviluppatori di estendere il sistema di tipi scalari del server archiviando oggetti CLR (Common Language Runtime) in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="684b1-103">User-defined types (UDTs) allow a developer to extend the server's scalar type system by storing common language runtime (CLR) objects in a SQL Server database.</span></span> <span data-ttu-id="684b1-104">I tipi UDT possono contenere più elementi e presentare comportamenti diversi dai tipi di dati alias tradizionali, costituiti da un singolo tipo di dati di sistema SQL Server.</span><span class="sxs-lookup"><span data-stu-id="684b1-104">UDTs can contain multiple elements and can have behaviors, unlike the traditional alias data types, which consist of a single SQL Server system data type.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="684b1-105">Per sfruttare il supporto SqlClient migliorato per i tipi UDT di grandi dimensioni, è necessario installare .NET Framework 3.5 SP1 (o versione successiva).</span><span class="sxs-lookup"><span data-stu-id="684b1-105">You must install the .NET Framework 3.5 SP1 (or later) to take advantage of the enhanced SqlClient support for large UDTs.</span></span>  
  
 <span data-ttu-id="684b1-106">In precedenza, i tipi UDT avevano una dimensione massima di 8 kilobyte.</span><span class="sxs-lookup"><span data-stu-id="684b1-106">Previously, UDTs were restricted to a maximum size of 8 kilobytes.</span></span> <span data-ttu-id="684b1-107">In SQL Server 2008 questa limitazione è stata rimossa per i tipi UDT che hanno un formato <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span><span class="sxs-lookup"><span data-stu-id="684b1-107">In SQL Server 2008, this restriction has been removed for UDTs that have a format of <xref:Microsoft.SqlServer.Server.Format.UserDefined>.</span></span>  
  
 <span data-ttu-id="684b1-108">Per informazioni complete sui tipi definiti dall'utente, vedere la documentazione online di SQL Server relativa alla versione di SQL Server in uso.</span><span class="sxs-lookup"><span data-stu-id="684b1-108">For the complete documentation for user-defined types, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 **<span data-ttu-id="684b1-109">Documentazione online di SQL Server</span><span class="sxs-lookup"><span data-stu-id="684b1-109">SQL Server Books Online</span></span>**  
  
1.  [<span data-ttu-id="684b1-110">Tipi definiti dall'utente CLR</span><span class="sxs-lookup"><span data-stu-id="684b1-110">CLR User-Defined Types</span></span>](https://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a><span data-ttu-id="684b1-111">Recupero di schemi UDT tramite GetSchema</span><span class="sxs-lookup"><span data-stu-id="684b1-111">Retrieving UDT Schemas Using GetSchema</span></span>  
 <span data-ttu-id="684b1-112">Il metodo <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> di <xref:System.Data.SqlClient.SqlConnection> restituisce informazioni sullo schema del database in un oggetto <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="684b1-112">The <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of <xref:System.Data.SqlClient.SqlConnection> returns database schema information in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="684b1-113">Per altre informazioni, vedere [raccolte di schemi di SQL Server](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md).</span><span class="sxs-lookup"><span data-stu-id="684b1-113">For more information, see [SQL Server Schema Collections](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md).</span></span>  
  
### <a name="getschematable-column-values-for-udts"></a><span data-ttu-id="684b1-114">Valori della colonna GetSchemaTable per i tipi UDT</span><span class="sxs-lookup"><span data-stu-id="684b1-114">GetSchemaTable Column Values for UDTs</span></span>  
 <span data-ttu-id="684b1-115">Il metodo <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> di <xref:System.Data.SqlClient.SqlDataReader> restituisce un oggetto <xref:System.Data.DataTable> che descrive i metadati della colonna.</span><span class="sxs-lookup"><span data-stu-id="684b1-115">The <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A> method of a <xref:System.Data.SqlClient.SqlDataReader> returns a <xref:System.Data.DataTable> that describes column metadata.</span></span> <span data-ttu-id="684b1-116">La tabella seguente descrive le differenze tra i metadati della colonna per i tipi UDT di grandi dimensioni tra SQL Server 2005 e SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="684b1-116">The following table describes the differences in the column metadata for large UDTs between SQL Server 2005 and SQL Server 2008.</span></span>  
  
|<span data-ttu-id="684b1-117">Colonna SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="684b1-117">SqlDataReader column</span></span>|<span data-ttu-id="684b1-118">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="684b1-118">SQL Server 2005</span></span>|<span data-ttu-id="684b1-119">SQL Server 2008 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="684b1-119">SQL Server 2008 and later</span></span>|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|<span data-ttu-id="684b1-120">Variabile</span><span class="sxs-lookup"><span data-stu-id="684b1-120">Varies</span></span>|<span data-ttu-id="684b1-121">Variabile</span><span class="sxs-lookup"><span data-stu-id="684b1-121">Varies</span></span>|  
|`NumericPrecision`|<span data-ttu-id="684b1-122">255</span><span class="sxs-lookup"><span data-stu-id="684b1-122">255</span></span>|<span data-ttu-id="684b1-123">255</span><span class="sxs-lookup"><span data-stu-id="684b1-123">255</span></span>|  
|`NumericScale`|<span data-ttu-id="684b1-124">255</span><span class="sxs-lookup"><span data-stu-id="684b1-124">255</span></span>|<span data-ttu-id="684b1-125">255</span><span class="sxs-lookup"><span data-stu-id="684b1-125">255</span></span>|  
|`DataType`|`Byte[]`|<span data-ttu-id="684b1-126">Istanza UDT</span><span class="sxs-lookup"><span data-stu-id="684b1-126">UDT instance</span></span>|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|<span data-ttu-id="684b1-127">Istanza UDT</span><span class="sxs-lookup"><span data-stu-id="684b1-127">UDT instance</span></span>|  
|`ProviderType`|<span data-ttu-id="684b1-128">21 (`SqlDbType.VarBinary`)</span><span class="sxs-lookup"><span data-stu-id="684b1-128">21 (`SqlDbType.VarBinary`)</span></span>|<span data-ttu-id="684b1-129">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="684b1-129">29 (`SqlDbType.Udt`)</span></span>|  
|`NonVersionedProviderType`|<span data-ttu-id="684b1-130">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="684b1-130">29 (`SqlDbType.Udt`)</span></span>|<span data-ttu-id="684b1-131">29 (`SqlDbType.Udt`)</span><span class="sxs-lookup"><span data-stu-id="684b1-131">29 (`SqlDbType.Udt`)</span></span>|  
|`DataTypeName`|`SqlDbType.VarBinary`|<span data-ttu-id="684b1-132">Specificato come nome in tre parti *SchemaName*.</span><span class="sxs-lookup"><span data-stu-id="684b1-132">The three part name specified as *Database.SchemaName.TypeName*.</span></span>|  
|`IsLong`|<span data-ttu-id="684b1-133">Variabile</span><span class="sxs-lookup"><span data-stu-id="684b1-133">Varies</span></span>|<span data-ttu-id="684b1-134">Variabile</span><span class="sxs-lookup"><span data-stu-id="684b1-134">Varies</span></span>|  
  
## <a name="sqldatareader-considerations"></a><span data-ttu-id="684b1-135">Considerazioni su SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="684b1-135">SqlDataReader Considerations</span></span>  
 <span data-ttu-id="684b1-136"><xref:System.Data.SqlClient.SqlDataReader> è stato esteso a partire da SQL Server 2008 per supportare il recupero di valori UDT di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="684b1-136">The <xref:System.Data.SqlClient.SqlDataReader> has been extended beginning in SQL Server 2008 to support retrieving large UDT values.</span></span> <span data-ttu-id="684b1-137">La modalità di elaborazione dei valori UDT di grandi dimensioni da parte di <xref:System.Data.SqlClient.SqlDataReader> dipende dalla versione di SQL Server in uso, nonché dal valore di `Type System Version` specificato nella stringa di connessione.</span><span class="sxs-lookup"><span data-stu-id="684b1-137">How large UDT values are processed by a <xref:System.Data.SqlClient.SqlDataReader> depends on the version of SQL Server you are using, as well as on the `Type System Version` specified in the connection string.</span></span> <span data-ttu-id="684b1-138">Per altre informazioni, vedere <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="684b1-138">For more information, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="684b1-139">I seguenti metodi di <xref:System.Data.SqlClient.SqlDataReader> restituiranno <xref:System.Data.SqlTypes.SqlBinary> anziché un tipo definito dall'utente quando `Type System Version` è impostato su SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="684b1-139">The following methods of <xref:System.Data.SqlClient.SqlDataReader> will return a <xref:System.Data.SqlTypes.SqlBinary> instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 <span data-ttu-id="684b1-140">I seguenti metodi restituiranno una matrice di `Byte[]` anziché un tipo definito dall'utente quando `Type System Version` è impostato su SQL Server 2005:</span><span class="sxs-lookup"><span data-stu-id="684b1-140">The following methods will return an array of `Byte[]` instead of a UDT when the `Type System Version` is set to SQL Server 2005:</span></span>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
-   <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 <span data-ttu-id="684b1-141">Si noti che per la versione corrente di ADO.NET non vengono eseguite conversioni.</span><span class="sxs-lookup"><span data-stu-id="684b1-141">Note that no conversions are made for the current version of ADO.NET.</span></span>  
  
## <a name="specifying-sqlparameters"></a><span data-ttu-id="684b1-142">Impostazione di SqlParameters</span><span class="sxs-lookup"><span data-stu-id="684b1-142">Specifying SqlParameters</span></span>  
 <span data-ttu-id="684b1-143">Le proprietà <xref:System.Data.SqlClient.SqlParameter> seguenti sono state estese per l'uso con i tipi UDT di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="684b1-143">The following <xref:System.Data.SqlClient.SqlParameter> properties have been extended to work with large UDTs.</span></span>  
  
|<span data-ttu-id="684b1-144">Proprietà SqlParameter</span><span class="sxs-lookup"><span data-stu-id="684b1-144">SqlParameter Property</span></span>|<span data-ttu-id="684b1-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="684b1-145">Description</span></span>|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|<span data-ttu-id="684b1-146">Ottiene o imposta un oggetto che rappresenta il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="684b1-146">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="684b1-147">Il valore predefinito è Null.</span><span class="sxs-lookup"><span data-stu-id="684b1-147">The default is null.</span></span> <span data-ttu-id="684b1-148">La proprietà può essere `SqlBinary`, `Byte[]` o un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="684b1-148">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|<span data-ttu-id="684b1-149">Ottiene o imposta un oggetto che rappresenta il valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="684b1-149">Gets or sets an object that represents the value of the parameter.</span></span> <span data-ttu-id="684b1-150">Il valore predefinito è Null.</span><span class="sxs-lookup"><span data-stu-id="684b1-150">The default is null.</span></span> <span data-ttu-id="684b1-151">La proprietà può essere `SqlBinary`, `Byte[]` o un oggetto gestito.</span><span class="sxs-lookup"><span data-stu-id="684b1-151">The property can be `SqlBinary`, `Byte[]`, or a managed object.</span></span>|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|<span data-ttu-id="684b1-152">Ottiene o imposta la dimensione del valore del parametro da risolvere.</span><span class="sxs-lookup"><span data-stu-id="684b1-152">Gets or sets the size of the parameter value to resolve.</span></span> <span data-ttu-id="684b1-153">Il valore predefinito è 0.</span><span class="sxs-lookup"><span data-stu-id="684b1-153">The default value is 0.</span></span> <span data-ttu-id="684b1-154">La proprietà può essere un integer che rappresenta la dimensione del valore del parametro.</span><span class="sxs-lookup"><span data-stu-id="684b1-154">The property can be an integer that represents the size of the parameter value.</span></span> <span data-ttu-id="684b1-155">Per i tipi UDT di grandi dimensioni, può trattarsi delle dimensioni effettive del tipo UDT oppure può essere pari a -1 per i tipi sconosciuti.</span><span class="sxs-lookup"><span data-stu-id="684b1-155">For large UDTs, it can be the actual size of the UDT, or -1 for unknown.</span></span>|  
  
## <a name="retrieving-data-example"></a><span data-ttu-id="684b1-156">Esempio di recupero di dati</span><span class="sxs-lookup"><span data-stu-id="684b1-156">Retrieving Data Example</span></span>  
 <span data-ttu-id="684b1-157">Nel frammento di codice seguente viene illustrato come recuperare i dati UDT di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="684b1-157">The following code fragment demonstrates how to retrieve large UDT data.</span></span> <span data-ttu-id="684b1-158">La variabile `connectionString` presuppone una connessione valida a un database di SQL Server e la variabile `commandString` presuppone un'istruzione SELECT valida con la colonna della chiave primaria elencata per prima.</span><span class="sxs-lookup"><span data-stu-id="684b1-158">The `connectionString` variable assumes a valid connection to a SQL Server database and the `commandString` variable assumes a valid SELECT statement with the primary key column listed first.</span></span>  
  
```csharp  
using (SqlConnection connection = new SqlConnection(   
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a><span data-ttu-id="684b1-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="684b1-159">See also</span></span>

- [<span data-ttu-id="684b1-160">Configurazione dei parametri e tipi di dati dei parametri</span><span class="sxs-lookup"><span data-stu-id="684b1-160">Configuring Parameters and Parameter Data Types</span></span>](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [<span data-ttu-id="684b1-161">Recupero di informazioni dello schema del database</span><span class="sxs-lookup"><span data-stu-id="684b1-161">Retrieving Database Schema Information</span></span>](../../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [<span data-ttu-id="684b1-162">Mapping dei tipi di dati SQL Server</span><span class="sxs-lookup"><span data-stu-id="684b1-162">SQL Server Data Type Mappings</span></span>](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [<span data-ttu-id="684b1-163">Dati binari e con valori elevati SQL Server</span><span class="sxs-lookup"><span data-stu-id="684b1-163">SQL Server Binary and Large-Value Data</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="684b1-164">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="684b1-164">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
