---
title: Restrizione dello schema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 1a2c32d133799ee5338c18d0f51bced49cb3dc4b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963190"
---
# <a name="schema-restrictions"></a><span data-ttu-id="feff3-102">Restrizione dello schema</span><span class="sxs-lookup"><span data-stu-id="feff3-102">Schema Restrictions</span></span>
<span data-ttu-id="feff3-103">Il secondo parametro facoltativo del metodo **GetSchema** è costituito dalle restrizioni utilizzate per limitare la quantità di informazioni sullo schema restituite e viene passato al metodo GetSchema come una matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="feff3-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="feff3-104">La posizione nella matrice determina i valori che è possibile passare ed equivale al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="feff3-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="feff3-105">Nella tabella seguente, ad esempio, vengono descritte le restrizioni supportate dalla raccolta di schemi "Tables" usando il provider di dati .NET Framework per SQL Server:</span><span class="sxs-lookup"><span data-stu-id="feff3-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="feff3-106">Restrizioni aggiuntive per le raccolte di schemi di SQL Server vengono indicate alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="feff3-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="feff3-107">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-107">Restriction Name</span></span>|<span data-ttu-id="feff3-108">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-108">Parameter Name</span></span>|<span data-ttu-id="feff3-109">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-109">Restriction Default</span></span>|<span data-ttu-id="feff3-110">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-111">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-112">TABLE_CATALOG</span></span>|<span data-ttu-id="feff3-113">1</span><span class="sxs-lookup"><span data-stu-id="feff3-113">1</span></span>|  
|<span data-ttu-id="feff3-114">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-114">Owner</span></span>|@Owner|<span data-ttu-id="feff3-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="feff3-116">2</span><span class="sxs-lookup"><span data-stu-id="feff3-116">2</span></span>|  
|<span data-ttu-id="feff3-117">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-117">Table</span></span>|@Name|<span data-ttu-id="feff3-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-118">TABLE_NAME</span></span>|<span data-ttu-id="feff3-119">3</span><span class="sxs-lookup"><span data-stu-id="feff3-119">3</span></span>|  
|<span data-ttu-id="feff3-120">TableType</span><span class="sxs-lookup"><span data-stu-id="feff3-120">TableType</span></span>|@TableType|<span data-ttu-id="feff3-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="feff3-121">TABLE_TYPE</span></span>|<span data-ttu-id="feff3-122">4</span><span class="sxs-lookup"><span data-stu-id="feff3-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="feff3-123">Impostazione dei valori di restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="feff3-124">Per usare una delle restrizioni della raccolta di schemi "Tables", è sufficiente creare una matrice di stringa con quattro elementi, quindi posizionare un valore nell'elemento che corrisponde al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="feff3-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="feff3-125">Ad esempio, per limitare le tabelle restituite dal metodo GetSchema solo alle tabelle nello schema "Sales", impostare il secondo elemento della matrice su "Sales" prima di passarlo al metodo GetSchema .</span><span class="sxs-lookup"><span data-stu-id="feff3-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="feff3-126">Le raccolte di restrizioni per `SqlClient` e `OracleClient` includono una colonna `ParameterName` aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="feff3-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="feff3-127">La colonna di restrizione predefinita è ancora disponibile per garantire la compatibilità con le versioni precedenti, ma attualmente è ignorata.</span><span class="sxs-lookup"><span data-stu-id="feff3-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="feff3-128">Per ridurre il rischio di attacchi SQL injection quando si specificano i valori di restrizione, si consiglia di usare query con parametri invece di sostituire le stringhe.</span><span class="sxs-lookup"><span data-stu-id="feff3-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="feff3-129">Il numero di elementi nella matrice deve essere inferiore o uguale al numero di restrizioni supportato per la raccolta di schemi specificato, in caso contrario verrà generato un tipo <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="feff3-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="feff3-130">Il numero di restrizioni può essere inferiore al numero massimo consentito.</span><span class="sxs-lookup"><span data-stu-id="feff3-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="feff3-131">Le restrizioni mancanti verranno considerate null (senza restrizioni).</span><span class="sxs-lookup"><span data-stu-id="feff3-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="feff3-132">È possibile eseguire una query su un provider gestito .NET Framework per determinare l'elenco delle restrizioni supportate chiamando il metodo GetSchema con il nome della raccolta di schemi delle restrizioni, ovvero "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="feff3-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="feff3-133">In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco dei nomi delle raccolte, i nomi delle restrizioni, i valori di restrizione predefiniti e i numeri delle restrizioni.</span><span class="sxs-lookup"><span data-stu-id="feff3-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="feff3-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="feff3-134">Example</span></span>  
 <span data-ttu-id="feff3-135">Negli esempi seguenti viene illustrato come utilizzare il <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metodo della .NET Framework provider di dati per la classe SQL Server <xref:System.Data.SqlClient.SqlConnection> per recuperare informazioni sullo schema relative a tutte le tabelle contenute nel database di esempio **AdventureWorks** . e per limitare le informazioni restituite alle sole tabelle nello schema "Sales":</span><span class="sxs-lookup"><span data-stu-id="feff3-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
```vb  
Imports System.Data.SqlClient  
  
Module Module1  
Sub Main()  
  Dim connectionString As String = _  
    "Data Source=(local);Database=AdventureWorks;" & _  
       "Integrated Security=true;";  
  
  Dim restrictions(3) As String  
  Using connection As New SqlConnection(connectionString)  
    connection.Open()  
  
    'Specify the restrictions.  
    restrictions(1) = "Sales"  
    Dim table As DataTable = connection.GetSchema("Tables", _  
       restrictions)  
  
    ' Display the contents of the table.  
      For Each row As DataRow In table.Rows  
         For Each col As DataColumn In table.Columns  
            Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
         Next  
         Console.WriteLine("============================")  
      Next  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Using  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.SqlClient;  
  
class Program  
{  
  static void Main()  
  {  
    string connectionString =   
       "Data Source=(local);Database=AdventureWorks;" +  
       "Integrated Security=true;";  
    using (SqlConnection connection =  
       new SqlConnection(connectionString))  
    {  
        connection.Open();  
  
        // Specify the restrictions.  
        string[] restrictions = new string[4];  
        restrictions[1] = "Sales";  
        System.Data.DataTable table = connection.GetSchema(  
          "Tables", restrictions);  
  
        // Display the contents of the table.  
        foreach (System.Data.DataRow row in table.Rows)  
        {  
            foreach (System.Data.DataColumn col in table.Columns)  
            {  
                Console.WriteLine("{0} = {1}",   
                  col.ColumnName, row[col]);  
            }  
            Console.WriteLine("============================");  
        }  
        Console.WriteLine("Press any key to continue.");  
        Console.ReadKey();  
    }  
  }  
  
  private static string GetConnectionString()  
  {  
     // To avoid storing the connection string in your code,  
     // you can retrieve it from a configuration file.  
     return "Data Source=(local);Database=AdventureWorks;" +  
        "Integrated Security=true;";  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
     foreach (System.Data.DataRow row in table.Rows)  
     {  
        foreach (System.Data.DataColumn col in table.Columns)  
        {  
           Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
        }  
     Console.WriteLine("============================");  
     }  
  }  
}  
```  
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="feff3-136">Restrizioni per gli schemi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="feff3-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="feff3-137">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="feff3-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="feff3-138">Utenti</span><span class="sxs-lookup"><span data-stu-id="feff3-138">Users</span></span>  
  
|<span data-ttu-id="feff3-139">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-139">Restriction Name</span></span>|<span data-ttu-id="feff3-140">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-140">Parameter Name</span></span>|<span data-ttu-id="feff3-141">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-141">Restriction Default</span></span>|<span data-ttu-id="feff3-142">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="feff3-143">User_Name</span></span>|@Name|<span data-ttu-id="feff3-144">name</span><span class="sxs-lookup"><span data-stu-id="feff3-144">name</span></span>|<span data-ttu-id="feff3-145">1</span><span class="sxs-lookup"><span data-stu-id="feff3-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="feff3-146">Database</span><span class="sxs-lookup"><span data-stu-id="feff3-146">Databases</span></span>  
  
|<span data-ttu-id="feff3-147">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-147">Restriction Name</span></span>|<span data-ttu-id="feff3-148">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-148">Parameter Name</span></span>|<span data-ttu-id="feff3-149">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-149">Restriction Default</span></span>|<span data-ttu-id="feff3-150">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-151">NOME</span><span class="sxs-lookup"><span data-stu-id="feff3-151">Name</span></span>|@Name|<span data-ttu-id="feff3-152">Name</span><span class="sxs-lookup"><span data-stu-id="feff3-152">Name</span></span>|<span data-ttu-id="feff3-153">1</span><span class="sxs-lookup"><span data-stu-id="feff3-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="feff3-154">Tabelle</span><span class="sxs-lookup"><span data-stu-id="feff3-154">Tables</span></span>  
  
|<span data-ttu-id="feff3-155">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-155">Restriction Name</span></span>|<span data-ttu-id="feff3-156">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-156">Parameter Name</span></span>|<span data-ttu-id="feff3-157">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-157">Restriction Default</span></span>|<span data-ttu-id="feff3-158">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-159">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-160">TABLE_CATALOG</span></span>|<span data-ttu-id="feff3-161">1</span><span class="sxs-lookup"><span data-stu-id="feff3-161">1</span></span>|  
|<span data-ttu-id="feff3-162">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-162">Owner</span></span>|@Owner|<span data-ttu-id="feff3-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="feff3-164">2</span><span class="sxs-lookup"><span data-stu-id="feff3-164">2</span></span>|  
|<span data-ttu-id="feff3-165">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-165">Table</span></span>|@Name|<span data-ttu-id="feff3-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-166">TABLE_NAME</span></span>|<span data-ttu-id="feff3-167">3</span><span class="sxs-lookup"><span data-stu-id="feff3-167">3</span></span>|  
|<span data-ttu-id="feff3-168">TableType</span><span class="sxs-lookup"><span data-stu-id="feff3-168">TableType</span></span>|@TableType|<span data-ttu-id="feff3-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="feff3-169">TABLE_TYPE</span></span>|<span data-ttu-id="feff3-170">4</span><span class="sxs-lookup"><span data-stu-id="feff3-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="feff3-171">Colonne</span><span class="sxs-lookup"><span data-stu-id="feff3-171">Columns</span></span>  
  
|<span data-ttu-id="feff3-172">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-172">Restriction Name</span></span>|<span data-ttu-id="feff3-173">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-173">Parameter Name</span></span>|<span data-ttu-id="feff3-174">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-174">Restriction Default</span></span>|<span data-ttu-id="feff3-175">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-176">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-177">TABLE_CATALOG</span></span>|<span data-ttu-id="feff3-178">1</span><span class="sxs-lookup"><span data-stu-id="feff3-178">1</span></span>|  
|<span data-ttu-id="feff3-179">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-179">Owner</span></span>|@Owner|<span data-ttu-id="feff3-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="feff3-181">2</span><span class="sxs-lookup"><span data-stu-id="feff3-181">2</span></span>|  
|<span data-ttu-id="feff3-182">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-182">Table</span></span>|@Table|<span data-ttu-id="feff3-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-183">TABLE_NAME</span></span>|<span data-ttu-id="feff3-184">3</span><span class="sxs-lookup"><span data-stu-id="feff3-184">3</span></span>|  
|<span data-ttu-id="feff3-185">Colonna</span><span class="sxs-lookup"><span data-stu-id="feff3-185">Column</span></span>|@Column|<span data-ttu-id="feff3-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-186">COLUMN_NAME</span></span>|<span data-ttu-id="feff3-187">4</span><span class="sxs-lookup"><span data-stu-id="feff3-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="feff3-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="feff3-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="feff3-189">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-189">Restriction Name</span></span>|<span data-ttu-id="feff3-190">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-190">Parameter Name</span></span>|<span data-ttu-id="feff3-191">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-191">Restriction Default</span></span>|<span data-ttu-id="feff3-192">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-193">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-194">TABLE_CATALOG</span></span>|<span data-ttu-id="feff3-195">1</span><span class="sxs-lookup"><span data-stu-id="feff3-195">1</span></span>|  
|<span data-ttu-id="feff3-196">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-196">Owner</span></span>|@Owner|<span data-ttu-id="feff3-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="feff3-198">2</span><span class="sxs-lookup"><span data-stu-id="feff3-198">2</span></span>|  
|<span data-ttu-id="feff3-199">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-199">Table</span></span>|@Table|<span data-ttu-id="feff3-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-200">TABLE_NAME</span></span>|<span data-ttu-id="feff3-201">3</span><span class="sxs-lookup"><span data-stu-id="feff3-201">3</span></span>|  
|<span data-ttu-id="feff3-202">Colonna</span><span class="sxs-lookup"><span data-stu-id="feff3-202">Column</span></span>|@Column|<span data-ttu-id="feff3-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-203">COLUMN_NAME</span></span>|<span data-ttu-id="feff3-204">4</span><span class="sxs-lookup"><span data-stu-id="feff3-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="feff3-205">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="feff3-205">Views</span></span>  
  
|<span data-ttu-id="feff3-206">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-206">Restriction Name</span></span>|<span data-ttu-id="feff3-207">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-207">Parameter Name</span></span>|<span data-ttu-id="feff3-208">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-208">Restriction Default</span></span>|<span data-ttu-id="feff3-209">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-210">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-211">TABLE_CATALOG</span></span>|<span data-ttu-id="feff3-212">1</span><span class="sxs-lookup"><span data-stu-id="feff3-212">1</span></span>|  
|<span data-ttu-id="feff3-213">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-213">Owner</span></span>|@Owner|<span data-ttu-id="feff3-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="feff3-215">2</span><span class="sxs-lookup"><span data-stu-id="feff3-215">2</span></span>|  
|<span data-ttu-id="feff3-216">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-216">Table</span></span>|@Table|<span data-ttu-id="feff3-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-217">TABLE_NAME</span></span>|<span data-ttu-id="feff3-218">3</span><span class="sxs-lookup"><span data-stu-id="feff3-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="feff3-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="feff3-219">ViewColumns</span></span>  
  
|<span data-ttu-id="feff3-220">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-220">Restriction Name</span></span>|<span data-ttu-id="feff3-221">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-221">Parameter Name</span></span>|<span data-ttu-id="feff3-222">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-222">Restriction Default</span></span>|<span data-ttu-id="feff3-223">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-224">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-225">VIEW_CATALOG</span></span>|<span data-ttu-id="feff3-226">1</span><span class="sxs-lookup"><span data-stu-id="feff3-226">1</span></span>|  
|<span data-ttu-id="feff3-227">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-227">Owner</span></span>|@Owner|<span data-ttu-id="feff3-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="feff3-229">2</span><span class="sxs-lookup"><span data-stu-id="feff3-229">2</span></span>|  
|<span data-ttu-id="feff3-230">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-230">Table</span></span>|@Table|<span data-ttu-id="feff3-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-231">VIEW_NAME</span></span>|<span data-ttu-id="feff3-232">3</span><span class="sxs-lookup"><span data-stu-id="feff3-232">3</span></span>|  
|<span data-ttu-id="feff3-233">Colonna</span><span class="sxs-lookup"><span data-stu-id="feff3-233">Column</span></span>|@Column|<span data-ttu-id="feff3-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-234">COLUMN_NAME</span></span>|<span data-ttu-id="feff3-235">4</span><span class="sxs-lookup"><span data-stu-id="feff3-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="feff3-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="feff3-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="feff3-237">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-237">Restriction Name</span></span>|<span data-ttu-id="feff3-238">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-238">Parameter Name</span></span>|<span data-ttu-id="feff3-239">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-239">Restriction Default</span></span>|<span data-ttu-id="feff3-240">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-241">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="feff3-243">1</span><span class="sxs-lookup"><span data-stu-id="feff3-243">1</span></span>|  
|<span data-ttu-id="feff3-244">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-244">Owner</span></span>|@Owner|<span data-ttu-id="feff3-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="feff3-246">2</span><span class="sxs-lookup"><span data-stu-id="feff3-246">2</span></span>|  
|<span data-ttu-id="feff3-247">Name</span><span class="sxs-lookup"><span data-stu-id="feff3-247">Name</span></span>|@Name|<span data-ttu-id="feff3-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="feff3-249">3</span><span class="sxs-lookup"><span data-stu-id="feff3-249">3</span></span>|  
|<span data-ttu-id="feff3-250">Parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-250">Parameter</span></span>|@Parameter|<span data-ttu-id="feff3-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-251">PARAMETER_NAME</span></span>|<span data-ttu-id="feff3-252">4</span><span class="sxs-lookup"><span data-stu-id="feff3-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="feff3-253">Procedure</span><span class="sxs-lookup"><span data-stu-id="feff3-253">Procedures</span></span>  
  
|<span data-ttu-id="feff3-254">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-254">Restriction Name</span></span>|<span data-ttu-id="feff3-255">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-255">Parameter Name</span></span>|<span data-ttu-id="feff3-256">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-256">Restriction Default</span></span>|<span data-ttu-id="feff3-257">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-258">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="feff3-260">1</span><span class="sxs-lookup"><span data-stu-id="feff3-260">1</span></span>|  
|<span data-ttu-id="feff3-261">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-261">Owner</span></span>|@Owner|<span data-ttu-id="feff3-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="feff3-263">2</span><span class="sxs-lookup"><span data-stu-id="feff3-263">2</span></span>|  
|<span data-ttu-id="feff3-264">Name</span><span class="sxs-lookup"><span data-stu-id="feff3-264">Name</span></span>|@Name|<span data-ttu-id="feff3-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="feff3-266">3</span><span class="sxs-lookup"><span data-stu-id="feff3-266">3</span></span>|  
|<span data-ttu-id="feff3-267">Type</span><span class="sxs-lookup"><span data-stu-id="feff3-267">Type</span></span>|@Type|<span data-ttu-id="feff3-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="feff3-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="feff3-269">4</span><span class="sxs-lookup"><span data-stu-id="feff3-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="feff3-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="feff3-270">IndexColumns</span></span>  
  
|<span data-ttu-id="feff3-271">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-271">Restriction Name</span></span>|<span data-ttu-id="feff3-272">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-272">Parameter Name</span></span>|<span data-ttu-id="feff3-273">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-273">Restriction Default</span></span>|<span data-ttu-id="feff3-274">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-275">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="feff3-276">db_name()</span></span>|<span data-ttu-id="feff3-277">1</span><span class="sxs-lookup"><span data-stu-id="feff3-277">1</span></span>|  
|<span data-ttu-id="feff3-278">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-278">Owner</span></span>|@Owner|<span data-ttu-id="feff3-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="feff3-279">user_name()</span></span>|<span data-ttu-id="feff3-280">2</span><span class="sxs-lookup"><span data-stu-id="feff3-280">2</span></span>|  
|<span data-ttu-id="feff3-281">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-281">Table</span></span>|@Table|<span data-ttu-id="feff3-282">o.name</span><span class="sxs-lookup"><span data-stu-id="feff3-282">o.name</span></span>|<span data-ttu-id="feff3-283">3</span><span class="sxs-lookup"><span data-stu-id="feff3-283">3</span></span>|  
|<span data-ttu-id="feff3-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="feff3-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="feff3-285">x.name</span><span class="sxs-lookup"><span data-stu-id="feff3-285">x.name</span></span>|<span data-ttu-id="feff3-286">4</span><span class="sxs-lookup"><span data-stu-id="feff3-286">4</span></span>|  
|<span data-ttu-id="feff3-287">Colonna</span><span class="sxs-lookup"><span data-stu-id="feff3-287">Column</span></span>|@Column|<span data-ttu-id="feff3-288">c.name</span><span class="sxs-lookup"><span data-stu-id="feff3-288">c.name</span></span>|<span data-ttu-id="feff3-289">5</span><span class="sxs-lookup"><span data-stu-id="feff3-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="feff3-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="feff3-290">Indexes</span></span>  
  
|<span data-ttu-id="feff3-291">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-291">Restriction Name</span></span>|<span data-ttu-id="feff3-292">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-292">Parameter Name</span></span>|<span data-ttu-id="feff3-293">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-293">Restriction Default</span></span>|<span data-ttu-id="feff3-294">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-295">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="feff3-296">db_name()</span></span>|<span data-ttu-id="feff3-297">1</span><span class="sxs-lookup"><span data-stu-id="feff3-297">1</span></span>|  
|<span data-ttu-id="feff3-298">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-298">Owner</span></span>|@Owner|<span data-ttu-id="feff3-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="feff3-299">user_name()</span></span>|<span data-ttu-id="feff3-300">2</span><span class="sxs-lookup"><span data-stu-id="feff3-300">2</span></span>|  
|<span data-ttu-id="feff3-301">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-301">Table</span></span>|@Table|<span data-ttu-id="feff3-302">o.name</span><span class="sxs-lookup"><span data-stu-id="feff3-302">o.name</span></span>|<span data-ttu-id="feff3-303">3</span><span class="sxs-lookup"><span data-stu-id="feff3-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="feff3-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="feff3-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="feff3-305">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-305">Restriction Name</span></span>|<span data-ttu-id="feff3-306">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-306">Parameter Name</span></span>|<span data-ttu-id="feff3-307">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-307">Restriction Default</span></span>|<span data-ttu-id="feff3-308">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="feff3-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="feff3-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="feff3-310">assemblies.name</span></span>|<span data-ttu-id="feff3-311">1</span><span class="sxs-lookup"><span data-stu-id="feff3-311">1</span></span>|  
|<span data-ttu-id="feff3-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="feff3-312">udt_name</span></span>|@UDTName|<span data-ttu-id="feff3-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="feff3-313">types.assembly_class</span></span>|<span data-ttu-id="feff3-314">2</span><span class="sxs-lookup"><span data-stu-id="feff3-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="feff3-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="feff3-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="feff3-316">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-316">Restriction Name</span></span>|<span data-ttu-id="feff3-317">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-317">Parameter Name</span></span>|<span data-ttu-id="feff3-318">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-318">Restriction Default</span></span>|<span data-ttu-id="feff3-319">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-320">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="feff3-322">1</span><span class="sxs-lookup"><span data-stu-id="feff3-322">1</span></span>|  
|<span data-ttu-id="feff3-323">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-323">Owner</span></span>|@Owner|<span data-ttu-id="feff3-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="feff3-325">2</span><span class="sxs-lookup"><span data-stu-id="feff3-325">2</span></span>|  
|<span data-ttu-id="feff3-326">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-326">Table</span></span>|@Table|<span data-ttu-id="feff3-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-327">TABLE_NAME</span></span>|<span data-ttu-id="feff3-328">3</span><span class="sxs-lookup"><span data-stu-id="feff3-328">3</span></span>|  
|<span data-ttu-id="feff3-329">Name</span><span class="sxs-lookup"><span data-stu-id="feff3-329">Name</span></span>|@Name|<span data-ttu-id="feff3-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="feff3-331">4</span><span class="sxs-lookup"><span data-stu-id="feff3-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="feff3-332">Restrizioni per gli schemi di SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="feff3-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="feff3-333">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="feff3-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="feff3-334">Queste restrizioni sono valide a partire dalla versione 3.5 SP1 di .NET Framework e da SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="feff3-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="feff3-335">Le restrizioni non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="feff3-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="feff3-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="feff3-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="feff3-337">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-337">Restriction Name</span></span>|<span data-ttu-id="feff3-338">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-338">Parameter Name</span></span>|<span data-ttu-id="feff3-339">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-339">Restriction Default</span></span>|<span data-ttu-id="feff3-340">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-341">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-342">TABLE_CATALOG</span></span>|<span data-ttu-id="feff3-343">1</span><span class="sxs-lookup"><span data-stu-id="feff3-343">1</span></span>|  
|<span data-ttu-id="feff3-344">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-344">Owner</span></span>|@Owner|<span data-ttu-id="feff3-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="feff3-346">2</span><span class="sxs-lookup"><span data-stu-id="feff3-346">2</span></span>|  
|<span data-ttu-id="feff3-347">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-347">Table</span></span>|@Table|<span data-ttu-id="feff3-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-348">TABLE_NAME</span></span>|<span data-ttu-id="feff3-349">3</span><span class="sxs-lookup"><span data-stu-id="feff3-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="feff3-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="feff3-350">AllColumns</span></span>  
  
|<span data-ttu-id="feff3-351">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-351">Restriction Name</span></span>|<span data-ttu-id="feff3-352">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="feff3-352">Parameter Name</span></span>|<span data-ttu-id="feff3-353">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-353">Restriction Default</span></span>|<span data-ttu-id="feff3-354">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="feff3-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="feff3-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="feff3-355">Catalog</span></span>|@Catalog|<span data-ttu-id="feff3-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="feff3-356">TABLE_CATALOG</span></span>|<span data-ttu-id="feff3-357">1</span><span class="sxs-lookup"><span data-stu-id="feff3-357">1</span></span>|  
|<span data-ttu-id="feff3-358">Proprietario</span><span class="sxs-lookup"><span data-stu-id="feff3-358">Owner</span></span>|@Owner|<span data-ttu-id="feff3-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="feff3-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="feff3-360">2</span><span class="sxs-lookup"><span data-stu-id="feff3-360">2</span></span>|  
|<span data-ttu-id="feff3-361">Tabella</span><span class="sxs-lookup"><span data-stu-id="feff3-361">Table</span></span>|@Table|<span data-ttu-id="feff3-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-362">TABLE_NAME</span></span>|<span data-ttu-id="feff3-363">3</span><span class="sxs-lookup"><span data-stu-id="feff3-363">3</span></span>|  
|<span data-ttu-id="feff3-364">Colonna</span><span class="sxs-lookup"><span data-stu-id="feff3-364">Column</span></span>|@Column|<span data-ttu-id="feff3-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="feff3-365">COLUMN_NAME</span></span>|<span data-ttu-id="feff3-366">4</span><span class="sxs-lookup"><span data-stu-id="feff3-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="feff3-367">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="feff3-367">See also</span></span>

- [<span data-ttu-id="feff3-368">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="feff3-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
