---
title: Restrizione dello schema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 17c42c5131252993d1f16e4a2f7a6450f0984d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149011"
---
# <a name="schema-restrictions"></a><span data-ttu-id="15c5c-102">Restrizione dello schema</span><span class="sxs-lookup"><span data-stu-id="15c5c-102">Schema Restrictions</span></span>
<span data-ttu-id="15c5c-103">Il secondo parametro facoltativo del **GetSchema** metodo è le restrizioni che vengono utilizzate per limitare la quantità di informazioni sullo schema restituito e viene passato al **GetSchema** metodo come matrice di stringhe.</span><span class="sxs-lookup"><span data-stu-id="15c5c-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="15c5c-104">La posizione nella matrice determina i valori che è possibile passare ed equivale al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="15c5c-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="15c5c-105">Nella tabella seguente, ad esempio, vengono descritte le restrizioni supportate dalla raccolta di schemi "Tables" usando il provider di dati .NET Framework per SQL Server:</span><span class="sxs-lookup"><span data-stu-id="15c5c-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="15c5c-106">Restrizioni aggiuntive per le raccolte di schemi di SQL Server vengono indicate alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="15c5c-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="15c5c-107">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-107">Restriction Name</span></span>|<span data-ttu-id="15c5c-108">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-108">Parameter Name</span></span>|<span data-ttu-id="15c5c-109">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-109">Restriction Default</span></span>|<span data-ttu-id="15c5c-110">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-111">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-111">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-112">TABLE_CATALOG</span></span>|<span data-ttu-id="15c5c-113">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-113">1</span></span>|  
|<span data-ttu-id="15c5c-114">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-114">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="15c5c-116">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-116">2</span></span>|  
|<span data-ttu-id="15c5c-117">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-117">Table</span></span>|@Name|<span data-ttu-id="15c5c-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-118">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-119">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-119">3</span></span>|  
|<span data-ttu-id="15c5c-120">TableType</span><span class="sxs-lookup"><span data-stu-id="15c5c-120">TableType</span></span>|@TableType|<span data-ttu-id="15c5c-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="15c5c-121">TABLE_TYPE</span></span>|<span data-ttu-id="15c5c-122">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="15c5c-123">Impostazione dei valori di restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="15c5c-124">Per usare una delle restrizioni della raccolta di schemi "Tables", è sufficiente creare una matrice di stringa con quattro elementi, quindi posizionare un valore nell'elemento che corrisponde al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="15c5c-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="15c5c-125">Ad esempio, per limitare le tabelle restituite dal metodo **GetSchema** solo a tali tabelle nello schema "Sales", impostare il secondo elemento della matrice su "Sales" prima di passarlo al metodo **GetSchema.**</span><span class="sxs-lookup"><span data-stu-id="15c5c-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15c5c-126">Le raccolte di restrizioni per `SqlClient` e `OracleClient` includono una colonna `ParameterName` aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="15c5c-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="15c5c-127">La colonna di restrizione predefinita è ancora disponibile per garantire la compatibilità con le versioni precedenti, ma attualmente è ignorata.</span><span class="sxs-lookup"><span data-stu-id="15c5c-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="15c5c-128">Per ridurre il rischio di attacchi SQL injection quando si specificano i valori di restrizione, si consiglia di usare query con parametri invece di sostituire le stringhe.</span><span class="sxs-lookup"><span data-stu-id="15c5c-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15c5c-129">Il numero di elementi nella matrice deve essere inferiore o uguale al numero di restrizioni supportato per la raccolta di schemi specificato, in caso contrario verrà generato un tipo <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="15c5c-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="15c5c-130">Il numero di restrizioni può essere inferiore al numero massimo consentito.</span><span class="sxs-lookup"><span data-stu-id="15c5c-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="15c5c-131">Le restrizioni mancanti verranno considerate null (senza restrizioni).</span><span class="sxs-lookup"><span data-stu-id="15c5c-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="15c5c-132">È possibile eseguire una query su un provider gestito .NET Framework per determinare l'elenco delle restrizioni supportate chiamando il **metodo GetSchema** con il nome dell'insieme di schemi di restrizioni, ovvero "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="15c5c-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="15c5c-133">In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco dei nomi delle raccolte, i nomi delle restrizioni, i valori di restrizione predefiniti e i numeri delle restrizioni.</span><span class="sxs-lookup"><span data-stu-id="15c5c-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="15c5c-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="15c5c-134">Example</span></span>  
 <span data-ttu-id="15c5c-135">Negli esempi seguenti viene <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> illustrato come utilizzare il metodo del <xref:System.Data.SqlClient.SqlConnection> provider di dati .NET Framework per la classe SQL Server per recuperare informazioni sullo schema relative a tutte le tabelle contenute nel database di esempio **AdventureWorks** e per limitare le informazioni restituite solo a tali tabelle nello schema "Sales":</span><span class="sxs-lookup"><span data-stu-id="15c5c-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="15c5c-136">Restrizioni per gli schemi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="15c5c-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="15c5c-137">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="15c5c-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="15c5c-138">Utenti</span><span class="sxs-lookup"><span data-stu-id="15c5c-138">Users</span></span>  
  
|<span data-ttu-id="15c5c-139">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-139">Restriction Name</span></span>|<span data-ttu-id="15c5c-140">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-140">Parameter Name</span></span>|<span data-ttu-id="15c5c-141">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-141">Restriction Default</span></span>|<span data-ttu-id="15c5c-142">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="15c5c-143">User_Name</span></span>|@Name|<span data-ttu-id="15c5c-144">name</span><span class="sxs-lookup"><span data-stu-id="15c5c-144">name</span></span>|<span data-ttu-id="15c5c-145">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="15c5c-146">Database</span><span class="sxs-lookup"><span data-stu-id="15c5c-146">Databases</span></span>  
  
|<span data-ttu-id="15c5c-147">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-147">Restriction Name</span></span>|<span data-ttu-id="15c5c-148">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-148">Parameter Name</span></span>|<span data-ttu-id="15c5c-149">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-149">Restriction Default</span></span>|<span data-ttu-id="15c5c-150">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-151">Nome</span><span class="sxs-lookup"><span data-stu-id="15c5c-151">Name</span></span>|@Name|<span data-ttu-id="15c5c-152">Nome</span><span class="sxs-lookup"><span data-stu-id="15c5c-152">Name</span></span>|<span data-ttu-id="15c5c-153">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="15c5c-154">Tabelle</span><span class="sxs-lookup"><span data-stu-id="15c5c-154">Tables</span></span>  
  
|<span data-ttu-id="15c5c-155">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-155">Restriction Name</span></span>|<span data-ttu-id="15c5c-156">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-156">Parameter Name</span></span>|<span data-ttu-id="15c5c-157">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-157">Restriction Default</span></span>|<span data-ttu-id="15c5c-158">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-159">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-159">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-160">TABLE_CATALOG</span></span>|<span data-ttu-id="15c5c-161">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-161">1</span></span>|  
|<span data-ttu-id="15c5c-162">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-162">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="15c5c-164">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-164">2</span></span>|  
|<span data-ttu-id="15c5c-165">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-165">Table</span></span>|@Name|<span data-ttu-id="15c5c-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-166">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-167">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-167">3</span></span>|  
|<span data-ttu-id="15c5c-168">TableType</span><span class="sxs-lookup"><span data-stu-id="15c5c-168">TableType</span></span>|@TableType|<span data-ttu-id="15c5c-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="15c5c-169">TABLE_TYPE</span></span>|<span data-ttu-id="15c5c-170">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="15c5c-171">Colonne</span><span class="sxs-lookup"><span data-stu-id="15c5c-171">Columns</span></span>  
  
|<span data-ttu-id="15c5c-172">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-172">Restriction Name</span></span>|<span data-ttu-id="15c5c-173">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-173">Parameter Name</span></span>|<span data-ttu-id="15c5c-174">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-174">Restriction Default</span></span>|<span data-ttu-id="15c5c-175">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-176">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-176">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-177">TABLE_CATALOG</span></span>|<span data-ttu-id="15c5c-178">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-178">1</span></span>|  
|<span data-ttu-id="15c5c-179">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-179">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="15c5c-181">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-181">2</span></span>|  
|<span data-ttu-id="15c5c-182">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-182">Table</span></span>|@Table|<span data-ttu-id="15c5c-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-183">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-184">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-184">3</span></span>|  
|<span data-ttu-id="15c5c-185">Colonna</span><span class="sxs-lookup"><span data-stu-id="15c5c-185">Column</span></span>|@Column|<span data-ttu-id="15c5c-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-186">COLUMN_NAME</span></span>|<span data-ttu-id="15c5c-187">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="15c5c-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="15c5c-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="15c5c-189">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-189">Restriction Name</span></span>|<span data-ttu-id="15c5c-190">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-190">Parameter Name</span></span>|<span data-ttu-id="15c5c-191">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-191">Restriction Default</span></span>|<span data-ttu-id="15c5c-192">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-193">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-193">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-194">TABLE_CATALOG</span></span>|<span data-ttu-id="15c5c-195">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-195">1</span></span>|  
|<span data-ttu-id="15c5c-196">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-196">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="15c5c-198">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-198">2</span></span>|  
|<span data-ttu-id="15c5c-199">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-199">Table</span></span>|@Table|<span data-ttu-id="15c5c-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-200">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-201">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-201">3</span></span>|  
|<span data-ttu-id="15c5c-202">Colonna</span><span class="sxs-lookup"><span data-stu-id="15c5c-202">Column</span></span>|@Column|<span data-ttu-id="15c5c-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-203">COLUMN_NAME</span></span>|<span data-ttu-id="15c5c-204">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="15c5c-205">Viste</span><span class="sxs-lookup"><span data-stu-id="15c5c-205">Views</span></span>  
  
|<span data-ttu-id="15c5c-206">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-206">Restriction Name</span></span>|<span data-ttu-id="15c5c-207">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-207">Parameter Name</span></span>|<span data-ttu-id="15c5c-208">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-208">Restriction Default</span></span>|<span data-ttu-id="15c5c-209">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-210">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-210">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-211">TABLE_CATALOG</span></span>|<span data-ttu-id="15c5c-212">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-212">1</span></span>|  
|<span data-ttu-id="15c5c-213">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-213">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="15c5c-215">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-215">2</span></span>|  
|<span data-ttu-id="15c5c-216">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-216">Table</span></span>|@Table|<span data-ttu-id="15c5c-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-217">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-218">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="15c5c-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="15c5c-219">ViewColumns</span></span>  
  
|<span data-ttu-id="15c5c-220">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-220">Restriction Name</span></span>|<span data-ttu-id="15c5c-221">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-221">Parameter Name</span></span>|<span data-ttu-id="15c5c-222">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-222">Restriction Default</span></span>|<span data-ttu-id="15c5c-223">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-224">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-224">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-225">VIEW_CATALOG</span></span>|<span data-ttu-id="15c5c-226">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-226">1</span></span>|  
|<span data-ttu-id="15c5c-227">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-227">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="15c5c-229">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-229">2</span></span>|  
|<span data-ttu-id="15c5c-230">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-230">Table</span></span>|@Table|<span data-ttu-id="15c5c-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-231">VIEW_NAME</span></span>|<span data-ttu-id="15c5c-232">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-232">3</span></span>|  
|<span data-ttu-id="15c5c-233">Colonna</span><span class="sxs-lookup"><span data-stu-id="15c5c-233">Column</span></span>|@Column|<span data-ttu-id="15c5c-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-234">COLUMN_NAME</span></span>|<span data-ttu-id="15c5c-235">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="15c5c-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="15c5c-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="15c5c-237">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-237">Restriction Name</span></span>|<span data-ttu-id="15c5c-238">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-238">Parameter Name</span></span>|<span data-ttu-id="15c5c-239">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-239">Restriction Default</span></span>|<span data-ttu-id="15c5c-240">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-241">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-241">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="15c5c-243">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-243">1</span></span>|  
|<span data-ttu-id="15c5c-244">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-244">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="15c5c-246">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-246">2</span></span>|  
|<span data-ttu-id="15c5c-247">Nome</span><span class="sxs-lookup"><span data-stu-id="15c5c-247">Name</span></span>|@Name|<span data-ttu-id="15c5c-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="15c5c-249">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-249">3</span></span>|  
|<span data-ttu-id="15c5c-250">Parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-250">Parameter</span></span>|@Parameter|<span data-ttu-id="15c5c-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-251">PARAMETER_NAME</span></span>|<span data-ttu-id="15c5c-252">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="15c5c-253">Procedure</span><span class="sxs-lookup"><span data-stu-id="15c5c-253">Procedures</span></span>  
  
|<span data-ttu-id="15c5c-254">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-254">Restriction Name</span></span>|<span data-ttu-id="15c5c-255">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-255">Parameter Name</span></span>|<span data-ttu-id="15c5c-256">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-256">Restriction Default</span></span>|<span data-ttu-id="15c5c-257">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-258">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-258">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="15c5c-260">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-260">1</span></span>|  
|<span data-ttu-id="15c5c-261">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-261">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="15c5c-263">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-263">2</span></span>|  
|<span data-ttu-id="15c5c-264">Nome</span><span class="sxs-lookup"><span data-stu-id="15c5c-264">Name</span></span>|@Name|<span data-ttu-id="15c5c-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="15c5c-266">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-266">3</span></span>|  
|<span data-ttu-id="15c5c-267">Type</span><span class="sxs-lookup"><span data-stu-id="15c5c-267">Type</span></span>|@Type|<span data-ttu-id="15c5c-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="15c5c-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="15c5c-269">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="15c5c-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="15c5c-270">IndexColumns</span></span>  
  
|<span data-ttu-id="15c5c-271">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-271">Restriction Name</span></span>|<span data-ttu-id="15c5c-272">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-272">Parameter Name</span></span>|<span data-ttu-id="15c5c-273">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-273">Restriction Default</span></span>|<span data-ttu-id="15c5c-274">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-275">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-275">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="15c5c-276">db_name()</span></span>|<span data-ttu-id="15c5c-277">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-277">1</span></span>|  
|<span data-ttu-id="15c5c-278">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-278">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="15c5c-279">user_name()</span></span>|<span data-ttu-id="15c5c-280">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-280">2</span></span>|  
|<span data-ttu-id="15c5c-281">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-281">Table</span></span>|@Table|<span data-ttu-id="15c5c-282">o.name</span><span class="sxs-lookup"><span data-stu-id="15c5c-282">o.name</span></span>|<span data-ttu-id="15c5c-283">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-283">3</span></span>|  
|<span data-ttu-id="15c5c-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="15c5c-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="15c5c-285">x.name</span><span class="sxs-lookup"><span data-stu-id="15c5c-285">x.name</span></span>|<span data-ttu-id="15c5c-286">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-286">4</span></span>|  
|<span data-ttu-id="15c5c-287">Colonna</span><span class="sxs-lookup"><span data-stu-id="15c5c-287">Column</span></span>|@Column|<span data-ttu-id="15c5c-288">c.name</span><span class="sxs-lookup"><span data-stu-id="15c5c-288">c.name</span></span>|<span data-ttu-id="15c5c-289">5</span><span class="sxs-lookup"><span data-stu-id="15c5c-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="15c5c-290">Indici</span><span class="sxs-lookup"><span data-stu-id="15c5c-290">Indexes</span></span>  
  
|<span data-ttu-id="15c5c-291">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-291">Restriction Name</span></span>|<span data-ttu-id="15c5c-292">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-292">Parameter Name</span></span>|<span data-ttu-id="15c5c-293">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-293">Restriction Default</span></span>|<span data-ttu-id="15c5c-294">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-295">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-295">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="15c5c-296">db_name()</span></span>|<span data-ttu-id="15c5c-297">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-297">1</span></span>|  
|<span data-ttu-id="15c5c-298">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-298">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="15c5c-299">user_name()</span></span>|<span data-ttu-id="15c5c-300">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-300">2</span></span>|  
|<span data-ttu-id="15c5c-301">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-301">Table</span></span>|@Table|<span data-ttu-id="15c5c-302">o.name</span><span class="sxs-lookup"><span data-stu-id="15c5c-302">o.name</span></span>|<span data-ttu-id="15c5c-303">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="15c5c-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="15c5c-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="15c5c-305">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-305">Restriction Name</span></span>|<span data-ttu-id="15c5c-306">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-306">Parameter Name</span></span>|<span data-ttu-id="15c5c-307">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-307">Restriction Default</span></span>|<span data-ttu-id="15c5c-308">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="15c5c-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="15c5c-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="15c5c-310">assemblies.name</span></span>|<span data-ttu-id="15c5c-311">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-311">1</span></span>|  
|<span data-ttu-id="15c5c-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="15c5c-312">udt_name</span></span>|@UDTName|<span data-ttu-id="15c5c-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="15c5c-313">types.assembly_class</span></span>|<span data-ttu-id="15c5c-314">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="15c5c-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="15c5c-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="15c5c-316">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-316">Restriction Name</span></span>|<span data-ttu-id="15c5c-317">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-317">Parameter Name</span></span>|<span data-ttu-id="15c5c-318">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-318">Restriction Default</span></span>|<span data-ttu-id="15c5c-319">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-320">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-320">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="15c5c-322">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-322">1</span></span>|  
|<span data-ttu-id="15c5c-323">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-323">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="15c5c-325">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-325">2</span></span>|  
|<span data-ttu-id="15c5c-326">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-326">Table</span></span>|@Table|<span data-ttu-id="15c5c-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-327">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-328">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-328">3</span></span>|  
|<span data-ttu-id="15c5c-329">Nome</span><span class="sxs-lookup"><span data-stu-id="15c5c-329">Name</span></span>|@Name|<span data-ttu-id="15c5c-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="15c5c-331">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="15c5c-332">Restrizioni per gli schemi di SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="15c5c-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="15c5c-333">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="15c5c-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="15c5c-334">Queste restrizioni sono valide a partire dalla versione 3.5 SP1 di .NET Framework e da SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="15c5c-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="15c5c-335">Le restrizioni non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="15c5c-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="15c5c-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="15c5c-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="15c5c-337">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-337">Restriction Name</span></span>|<span data-ttu-id="15c5c-338">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-338">Parameter Name</span></span>|<span data-ttu-id="15c5c-339">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-339">Restriction Default</span></span>|<span data-ttu-id="15c5c-340">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-341">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-341">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-342">TABLE_CATALOG</span></span>|<span data-ttu-id="15c5c-343">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-343">1</span></span>|  
|<span data-ttu-id="15c5c-344">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-344">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="15c5c-346">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-346">2</span></span>|  
|<span data-ttu-id="15c5c-347">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-347">Table</span></span>|@Table|<span data-ttu-id="15c5c-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-348">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-349">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="15c5c-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="15c5c-350">AllColumns</span></span>  
  
|<span data-ttu-id="15c5c-351">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-351">Restriction Name</span></span>|<span data-ttu-id="15c5c-352">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="15c5c-352">Parameter Name</span></span>|<span data-ttu-id="15c5c-353">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-353">Restriction Default</span></span>|<span data-ttu-id="15c5c-354">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="15c5c-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="15c5c-355">Catalogo</span><span class="sxs-lookup"><span data-stu-id="15c5c-355">Catalog</span></span>|@Catalog|<span data-ttu-id="15c5c-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="15c5c-356">TABLE_CATALOG</span></span>|<span data-ttu-id="15c5c-357">1</span><span class="sxs-lookup"><span data-stu-id="15c5c-357">1</span></span>|  
|<span data-ttu-id="15c5c-358">Proprietario</span><span class="sxs-lookup"><span data-stu-id="15c5c-358">Owner</span></span>|@Owner|<span data-ttu-id="15c5c-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="15c5c-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="15c5c-360">2</span><span class="sxs-lookup"><span data-stu-id="15c5c-360">2</span></span>|  
|<span data-ttu-id="15c5c-361">Tabella</span><span class="sxs-lookup"><span data-stu-id="15c5c-361">Table</span></span>|@Table|<span data-ttu-id="15c5c-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-362">TABLE_NAME</span></span>|<span data-ttu-id="15c5c-363">3</span><span class="sxs-lookup"><span data-stu-id="15c5c-363">3</span></span>|  
|<span data-ttu-id="15c5c-364">Colonna</span><span class="sxs-lookup"><span data-stu-id="15c5c-364">Column</span></span>|@Column|<span data-ttu-id="15c5c-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="15c5c-365">COLUMN_NAME</span></span>|<span data-ttu-id="15c5c-366">4</span><span class="sxs-lookup"><span data-stu-id="15c5c-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15c5c-367">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15c5c-367">See also</span></span>

- [<span data-ttu-id="15c5c-368">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="15c5c-368">ADO.NET Overview</span></span>](ado-net-overview.md)
