---
title: Restrizione dello schema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c254865800694af8eb754c3e8d4072688fd7e89a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="schema-restrictions"></a><span data-ttu-id="1587f-102">Restrizione dello schema</span><span class="sxs-lookup"><span data-stu-id="1587f-102">Schema Restrictions</span></span>
<span data-ttu-id="1587f-103">Il secondo parametro facoltativo del **GetSchema** il metodo è le restrizioni che vengono usate per limitare la quantità di informazioni sullo schema restituite e viene passato per il **GetSchema** metodo come una matrice di stringhe .</span><span class="sxs-lookup"><span data-stu-id="1587f-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="1587f-104">La posizione nella matrice determina i valori che è possibile passare ed equivale al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="1587f-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="1587f-105">Nella tabella seguente, ad esempio, vengono descritte le restrizioni supportate dalla raccolta di schemi "Tables" usando il provider di dati .NET Framework per SQL Server:</span><span class="sxs-lookup"><span data-stu-id="1587f-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="1587f-106">Restrizioni aggiuntive per le raccolte di schemi di SQL Server vengono indicate alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="1587f-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="1587f-107">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-107">Restriction Name</span></span>|<span data-ttu-id="1587f-108">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-108">Parameter Name</span></span>|<span data-ttu-id="1587f-109">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-109">Restriction Default</span></span>|<span data-ttu-id="1587f-110">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-111">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-112">TABLE_CATALOG</span></span>|<span data-ttu-id="1587f-113">1</span><span class="sxs-lookup"><span data-stu-id="1587f-113">1</span></span>|  
|<span data-ttu-id="1587f-114">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-114">Owner</span></span>|@Owner|<span data-ttu-id="1587f-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="1587f-116">2</span><span class="sxs-lookup"><span data-stu-id="1587f-116">2</span></span>|  
|<span data-ttu-id="1587f-117">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-117">Table</span></span>|@Name|<span data-ttu-id="1587f-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-118">TABLE_NAME</span></span>|<span data-ttu-id="1587f-119">3</span><span class="sxs-lookup"><span data-stu-id="1587f-119">3</span></span>|  
|<span data-ttu-id="1587f-120">TableType</span><span class="sxs-lookup"><span data-stu-id="1587f-120">TableType</span></span>|@TableType|<span data-ttu-id="1587f-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1587f-121">TABLE_TYPE</span></span>|<span data-ttu-id="1587f-122">4</span><span class="sxs-lookup"><span data-stu-id="1587f-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="1587f-123">Impostazione dei valori di restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="1587f-124">Per usare una delle restrizioni della raccolta di schemi "Tables", è sufficiente creare una matrice di stringa con quattro elementi, quindi posizionare un valore nell'elemento che corrisponde al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="1587f-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="1587f-125">Ad esempio, per limitare le tabelle restituite dal **GetSchema** metodo solo le tabelle nello schema "Sales", impostare il secondo elemento della matrice su "Sales" prima di passarlo al **GetSchema** metodo.</span><span class="sxs-lookup"><span data-stu-id="1587f-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1587f-126">Le raccolte di restrizioni per `SqlClient` e `OracleClient` includono una colonna `ParameterName` aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="1587f-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="1587f-127">La colonna di restrizione predefinita è ancora disponibile per garantire la compatibilità con le versioni precedenti, ma attualmente è ignorata.</span><span class="sxs-lookup"><span data-stu-id="1587f-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="1587f-128">Per ridurre il rischio di attacchi SQL injection quando si specificano i valori di restrizione, si consiglia di usare query con parametri invece di sostituire le stringhe.</span><span class="sxs-lookup"><span data-stu-id="1587f-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1587f-129">Il numero di elementi nella matrice deve essere inferiore o uguale al numero di restrizioni supportato per la raccolta di schemi specificato, in caso contrario verrà generato un tipo <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="1587f-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="1587f-130">Il numero di restrizioni può essere inferiore al numero massimo consentito.</span><span class="sxs-lookup"><span data-stu-id="1587f-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="1587f-131">Le restrizioni mancanti verranno considerate null (senza restrizioni).</span><span class="sxs-lookup"><span data-stu-id="1587f-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="1587f-132">È possibile eseguire query di un provider gestito .NET Framework per determinare l'elenco delle restrizioni supportate chiamando il **GetSchema** metodo con il nome dell'insieme di schemi di restrizioni, ovvero "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="1587f-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="1587f-133">In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco dei nomi delle raccolte, i nomi delle restrizioni, i valori di restrizione predefiniti e i numeri delle restrizioni.</span><span class="sxs-lookup"><span data-stu-id="1587f-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="1587f-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="1587f-134">Example</span></span>  
 <span data-ttu-id="1587f-135">Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metodo del Provider di dati .NET Framework per SQL Server <xref:System.Data.SqlClient.SqlConnection> classe per recuperare informazioni sullo schema relative a tutte le tabelle contenute nel **AdventureWorks**database di esempio e per limitare le informazioni restituite alle sole tabelle nello schema "Sales":</span><span class="sxs-lookup"><span data-stu-id="1587f-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="1587f-136">Restrizioni per gli schemi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="1587f-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="1587f-137">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1587f-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="1587f-138">Utenti</span><span class="sxs-lookup"><span data-stu-id="1587f-138">Users</span></span>  
  
|<span data-ttu-id="1587f-139">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-139">Restriction Name</span></span>|<span data-ttu-id="1587f-140">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-140">Parameter Name</span></span>|<span data-ttu-id="1587f-141">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-141">Restriction Default</span></span>|<span data-ttu-id="1587f-142">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="1587f-143">User_Name</span></span>|@Name|<span data-ttu-id="1587f-144">name</span><span class="sxs-lookup"><span data-stu-id="1587f-144">name</span></span>|<span data-ttu-id="1587f-145">1</span><span class="sxs-lookup"><span data-stu-id="1587f-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="1587f-146">Database</span><span class="sxs-lookup"><span data-stu-id="1587f-146">Databases</span></span>  
  
|<span data-ttu-id="1587f-147">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-147">Restriction Name</span></span>|<span data-ttu-id="1587f-148">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-148">Parameter Name</span></span>|<span data-ttu-id="1587f-149">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-149">Restriction Default</span></span>|<span data-ttu-id="1587f-150">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-151">Nome</span><span class="sxs-lookup"><span data-stu-id="1587f-151">Name</span></span>|@Name|<span data-ttu-id="1587f-152">Nome</span><span class="sxs-lookup"><span data-stu-id="1587f-152">Name</span></span>|<span data-ttu-id="1587f-153">1</span><span class="sxs-lookup"><span data-stu-id="1587f-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="1587f-154">Tabelle</span><span class="sxs-lookup"><span data-stu-id="1587f-154">Tables</span></span>  
  
|<span data-ttu-id="1587f-155">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-155">Restriction Name</span></span>|<span data-ttu-id="1587f-156">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-156">Parameter Name</span></span>|<span data-ttu-id="1587f-157">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-157">Restriction Default</span></span>|<span data-ttu-id="1587f-158">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-159">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-160">TABLE_CATALOG</span></span>|<span data-ttu-id="1587f-161">1</span><span class="sxs-lookup"><span data-stu-id="1587f-161">1</span></span>|  
|<span data-ttu-id="1587f-162">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-162">Owner</span></span>|@Owner|<span data-ttu-id="1587f-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="1587f-164">2</span><span class="sxs-lookup"><span data-stu-id="1587f-164">2</span></span>|  
|<span data-ttu-id="1587f-165">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-165">Table</span></span>|@Name|<span data-ttu-id="1587f-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-166">TABLE_NAME</span></span>|<span data-ttu-id="1587f-167">3</span><span class="sxs-lookup"><span data-stu-id="1587f-167">3</span></span>|  
|<span data-ttu-id="1587f-168">TableType</span><span class="sxs-lookup"><span data-stu-id="1587f-168">TableType</span></span>|@TableType|<span data-ttu-id="1587f-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1587f-169">TABLE_TYPE</span></span>|<span data-ttu-id="1587f-170">4</span><span class="sxs-lookup"><span data-stu-id="1587f-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="1587f-171">Colonne</span><span class="sxs-lookup"><span data-stu-id="1587f-171">Columns</span></span>  
  
|<span data-ttu-id="1587f-172">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-172">Restriction Name</span></span>|<span data-ttu-id="1587f-173">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-173">Parameter Name</span></span>|<span data-ttu-id="1587f-174">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-174">Restriction Default</span></span>|<span data-ttu-id="1587f-175">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-176">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-177">TABLE_CATALOG</span></span>|<span data-ttu-id="1587f-178">1</span><span class="sxs-lookup"><span data-stu-id="1587f-178">1</span></span>|  
|<span data-ttu-id="1587f-179">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-179">Owner</span></span>|@Owner|<span data-ttu-id="1587f-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="1587f-181">2</span><span class="sxs-lookup"><span data-stu-id="1587f-181">2</span></span>|  
|<span data-ttu-id="1587f-182">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-182">Table</span></span>|@Table|<span data-ttu-id="1587f-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-183">TABLE_NAME</span></span>|<span data-ttu-id="1587f-184">3</span><span class="sxs-lookup"><span data-stu-id="1587f-184">3</span></span>|  
|<span data-ttu-id="1587f-185">Colonna</span><span class="sxs-lookup"><span data-stu-id="1587f-185">Column</span></span>|@Column|<span data-ttu-id="1587f-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-186">COLUMN_NAME</span></span>|<span data-ttu-id="1587f-187">4</span><span class="sxs-lookup"><span data-stu-id="1587f-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="1587f-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="1587f-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="1587f-189">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-189">Restriction Name</span></span>|<span data-ttu-id="1587f-190">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-190">Parameter Name</span></span>|<span data-ttu-id="1587f-191">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-191">Restriction Default</span></span>|<span data-ttu-id="1587f-192">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-193">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-194">TABLE_CATALOG</span></span>|<span data-ttu-id="1587f-195">1</span><span class="sxs-lookup"><span data-stu-id="1587f-195">1</span></span>|  
|<span data-ttu-id="1587f-196">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-196">Owner</span></span>|@Owner|<span data-ttu-id="1587f-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="1587f-198">2</span><span class="sxs-lookup"><span data-stu-id="1587f-198">2</span></span>|  
|<span data-ttu-id="1587f-199">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-199">Table</span></span>|@Table|<span data-ttu-id="1587f-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-200">TABLE_NAME</span></span>|<span data-ttu-id="1587f-201">3</span><span class="sxs-lookup"><span data-stu-id="1587f-201">3</span></span>|  
|<span data-ttu-id="1587f-202">Colonna</span><span class="sxs-lookup"><span data-stu-id="1587f-202">Column</span></span>|@Column|<span data-ttu-id="1587f-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-203">COLUMN_NAME</span></span>|<span data-ttu-id="1587f-204">4</span><span class="sxs-lookup"><span data-stu-id="1587f-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="1587f-205">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="1587f-205">Views</span></span>  
  
|<span data-ttu-id="1587f-206">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-206">Restriction Name</span></span>|<span data-ttu-id="1587f-207">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-207">Parameter Name</span></span>|<span data-ttu-id="1587f-208">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-208">Restriction Default</span></span>|<span data-ttu-id="1587f-209">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-210">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-211">TABLE_CATALOG</span></span>|<span data-ttu-id="1587f-212">1</span><span class="sxs-lookup"><span data-stu-id="1587f-212">1</span></span>|  
|<span data-ttu-id="1587f-213">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-213">Owner</span></span>|@Owner|<span data-ttu-id="1587f-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="1587f-215">2</span><span class="sxs-lookup"><span data-stu-id="1587f-215">2</span></span>|  
|<span data-ttu-id="1587f-216">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-216">Table</span></span>|@Table|<span data-ttu-id="1587f-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-217">TABLE_NAME</span></span>|<span data-ttu-id="1587f-218">3</span><span class="sxs-lookup"><span data-stu-id="1587f-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="1587f-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="1587f-219">ViewColumns</span></span>  
  
|<span data-ttu-id="1587f-220">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-220">Restriction Name</span></span>|<span data-ttu-id="1587f-221">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-221">Parameter Name</span></span>|<span data-ttu-id="1587f-222">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-222">Restriction Default</span></span>|<span data-ttu-id="1587f-223">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-224">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-225">VIEW_CATALOG</span></span>|<span data-ttu-id="1587f-226">1</span><span class="sxs-lookup"><span data-stu-id="1587f-226">1</span></span>|  
|<span data-ttu-id="1587f-227">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-227">Owner</span></span>|@Owner|<span data-ttu-id="1587f-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="1587f-229">2</span><span class="sxs-lookup"><span data-stu-id="1587f-229">2</span></span>|  
|<span data-ttu-id="1587f-230">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-230">Table</span></span>|@Table|<span data-ttu-id="1587f-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-231">VIEW_NAME</span></span>|<span data-ttu-id="1587f-232">3</span><span class="sxs-lookup"><span data-stu-id="1587f-232">3</span></span>|  
|<span data-ttu-id="1587f-233">Colonna</span><span class="sxs-lookup"><span data-stu-id="1587f-233">Column</span></span>|@Column|<span data-ttu-id="1587f-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-234">COLUMN_NAME</span></span>|<span data-ttu-id="1587f-235">4</span><span class="sxs-lookup"><span data-stu-id="1587f-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="1587f-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="1587f-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="1587f-237">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-237">Restriction Name</span></span>|<span data-ttu-id="1587f-238">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-238">Parameter Name</span></span>|<span data-ttu-id="1587f-239">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-239">Restriction Default</span></span>|<span data-ttu-id="1587f-240">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-241">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="1587f-243">1</span><span class="sxs-lookup"><span data-stu-id="1587f-243">1</span></span>|  
|<span data-ttu-id="1587f-244">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-244">Owner</span></span>|@Owner|<span data-ttu-id="1587f-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="1587f-246">2</span><span class="sxs-lookup"><span data-stu-id="1587f-246">2</span></span>|  
|<span data-ttu-id="1587f-247">Nome</span><span class="sxs-lookup"><span data-stu-id="1587f-247">Name</span></span>|@Name|<span data-ttu-id="1587f-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="1587f-249">3</span><span class="sxs-lookup"><span data-stu-id="1587f-249">3</span></span>|  
|<span data-ttu-id="1587f-250">Parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-250">Parameter</span></span>|@Parameter|<span data-ttu-id="1587f-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-251">PARAMETER_NAME</span></span>|<span data-ttu-id="1587f-252">4</span><span class="sxs-lookup"><span data-stu-id="1587f-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="1587f-253">Procedure</span><span class="sxs-lookup"><span data-stu-id="1587f-253">Procedures</span></span>  
  
|<span data-ttu-id="1587f-254">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-254">Restriction Name</span></span>|<span data-ttu-id="1587f-255">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-255">Parameter Name</span></span>|<span data-ttu-id="1587f-256">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-256">Restriction Default</span></span>|<span data-ttu-id="1587f-257">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-258">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="1587f-260">1</span><span class="sxs-lookup"><span data-stu-id="1587f-260">1</span></span>|  
|<span data-ttu-id="1587f-261">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-261">Owner</span></span>|@Owner|<span data-ttu-id="1587f-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="1587f-263">2</span><span class="sxs-lookup"><span data-stu-id="1587f-263">2</span></span>|  
|<span data-ttu-id="1587f-264">Nome</span><span class="sxs-lookup"><span data-stu-id="1587f-264">Name</span></span>|@Name|<span data-ttu-id="1587f-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="1587f-266">3</span><span class="sxs-lookup"><span data-stu-id="1587f-266">3</span></span>|  
|<span data-ttu-id="1587f-267">Tipo</span><span class="sxs-lookup"><span data-stu-id="1587f-267">Type</span></span>|@Type|<span data-ttu-id="1587f-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="1587f-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="1587f-269">4</span><span class="sxs-lookup"><span data-stu-id="1587f-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="1587f-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="1587f-270">IndexColumns</span></span>  
  
|<span data-ttu-id="1587f-271">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-271">Restriction Name</span></span>|<span data-ttu-id="1587f-272">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-272">Parameter Name</span></span>|<span data-ttu-id="1587f-273">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-273">Restriction Default</span></span>|<span data-ttu-id="1587f-274">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-275">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="1587f-276">db_name()</span></span>|<span data-ttu-id="1587f-277">1</span><span class="sxs-lookup"><span data-stu-id="1587f-277">1</span></span>|  
|<span data-ttu-id="1587f-278">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-278">Owner</span></span>|@Owner|<span data-ttu-id="1587f-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="1587f-279">user_name()</span></span>|<span data-ttu-id="1587f-280">2</span><span class="sxs-lookup"><span data-stu-id="1587f-280">2</span></span>|  
|<span data-ttu-id="1587f-281">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-281">Table</span></span>|@Table|<span data-ttu-id="1587f-282">o.name</span><span class="sxs-lookup"><span data-stu-id="1587f-282">o.name</span></span>|<span data-ttu-id="1587f-283">3</span><span class="sxs-lookup"><span data-stu-id="1587f-283">3</span></span>|  
|<span data-ttu-id="1587f-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="1587f-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="1587f-285">x.name</span><span class="sxs-lookup"><span data-stu-id="1587f-285">x.name</span></span>|<span data-ttu-id="1587f-286">4</span><span class="sxs-lookup"><span data-stu-id="1587f-286">4</span></span>|  
|<span data-ttu-id="1587f-287">Colonna</span><span class="sxs-lookup"><span data-stu-id="1587f-287">Column</span></span>|@Column|<span data-ttu-id="1587f-288">c.name</span><span class="sxs-lookup"><span data-stu-id="1587f-288">c.name</span></span>|<span data-ttu-id="1587f-289">5</span><span class="sxs-lookup"><span data-stu-id="1587f-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="1587f-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="1587f-290">Indexes</span></span>  
  
|<span data-ttu-id="1587f-291">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-291">Restriction Name</span></span>|<span data-ttu-id="1587f-292">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-292">Parameter Name</span></span>|<span data-ttu-id="1587f-293">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-293">Restriction Default</span></span>|<span data-ttu-id="1587f-294">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-295">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="1587f-296">db_name()</span></span>|<span data-ttu-id="1587f-297">1</span><span class="sxs-lookup"><span data-stu-id="1587f-297">1</span></span>|  
|<span data-ttu-id="1587f-298">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-298">Owner</span></span>|@Owner|<span data-ttu-id="1587f-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="1587f-299">user_name()</span></span>|<span data-ttu-id="1587f-300">2</span><span class="sxs-lookup"><span data-stu-id="1587f-300">2</span></span>|  
|<span data-ttu-id="1587f-301">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-301">Table</span></span>|@Table|<span data-ttu-id="1587f-302">o.name</span><span class="sxs-lookup"><span data-stu-id="1587f-302">o.name</span></span>|<span data-ttu-id="1587f-303">3</span><span class="sxs-lookup"><span data-stu-id="1587f-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="1587f-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="1587f-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="1587f-305">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-305">Restriction Name</span></span>|<span data-ttu-id="1587f-306">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-306">Parameter Name</span></span>|<span data-ttu-id="1587f-307">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-307">Restriction Default</span></span>|<span data-ttu-id="1587f-308">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="1587f-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="1587f-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="1587f-310">assemblies.name</span></span>|<span data-ttu-id="1587f-311">1</span><span class="sxs-lookup"><span data-stu-id="1587f-311">1</span></span>|  
|<span data-ttu-id="1587f-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="1587f-312">udt_name</span></span>|@UDTName|<span data-ttu-id="1587f-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="1587f-313">types.assembly_class</span></span>|<span data-ttu-id="1587f-314">2</span><span class="sxs-lookup"><span data-stu-id="1587f-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="1587f-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="1587f-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="1587f-316">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-316">Restriction Name</span></span>|<span data-ttu-id="1587f-317">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-317">Parameter Name</span></span>|<span data-ttu-id="1587f-318">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-318">Restriction Default</span></span>|<span data-ttu-id="1587f-319">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-320">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="1587f-322">1</span><span class="sxs-lookup"><span data-stu-id="1587f-322">1</span></span>|  
|<span data-ttu-id="1587f-323">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-323">Owner</span></span>|@Owner|<span data-ttu-id="1587f-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="1587f-325">2</span><span class="sxs-lookup"><span data-stu-id="1587f-325">2</span></span>|  
|<span data-ttu-id="1587f-326">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-326">Table</span></span>|@Table|<span data-ttu-id="1587f-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-327">TABLE_NAME</span></span>|<span data-ttu-id="1587f-328">3</span><span class="sxs-lookup"><span data-stu-id="1587f-328">3</span></span>|  
|<span data-ttu-id="1587f-329">Nome</span><span class="sxs-lookup"><span data-stu-id="1587f-329">Name</span></span>|@Name|<span data-ttu-id="1587f-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="1587f-331">4</span><span class="sxs-lookup"><span data-stu-id="1587f-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="1587f-332">Restrizioni per gli schemi di SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="1587f-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="1587f-333">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1587f-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="1587f-334">Queste restrizioni sono valide a partire dalla versione 3.5 SP1 di .NET Framework e da SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="1587f-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="1587f-335">Le restrizioni non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1587f-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="1587f-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="1587f-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="1587f-337">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-337">Restriction Name</span></span>|<span data-ttu-id="1587f-338">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-338">Parameter Name</span></span>|<span data-ttu-id="1587f-339">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-339">Restriction Default</span></span>|<span data-ttu-id="1587f-340">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-341">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-342">TABLE_CATALOG</span></span>|<span data-ttu-id="1587f-343">1</span><span class="sxs-lookup"><span data-stu-id="1587f-343">1</span></span>|  
|<span data-ttu-id="1587f-344">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-344">Owner</span></span>|@Owner|<span data-ttu-id="1587f-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="1587f-346">2</span><span class="sxs-lookup"><span data-stu-id="1587f-346">2</span></span>|  
|<span data-ttu-id="1587f-347">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-347">Table</span></span>|@Table|<span data-ttu-id="1587f-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-348">TABLE_NAME</span></span>|<span data-ttu-id="1587f-349">3</span><span class="sxs-lookup"><span data-stu-id="1587f-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="1587f-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="1587f-350">AllColumns</span></span>  
  
|<span data-ttu-id="1587f-351">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-351">Restriction Name</span></span>|<span data-ttu-id="1587f-352">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="1587f-352">Parameter Name</span></span>|<span data-ttu-id="1587f-353">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-353">Restriction Default</span></span>|<span data-ttu-id="1587f-354">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="1587f-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="1587f-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="1587f-355">Catalog</span></span>|@Catalog|<span data-ttu-id="1587f-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="1587f-356">TABLE_CATALOG</span></span>|<span data-ttu-id="1587f-357">1</span><span class="sxs-lookup"><span data-stu-id="1587f-357">1</span></span>|  
|<span data-ttu-id="1587f-358">Owner</span><span class="sxs-lookup"><span data-stu-id="1587f-358">Owner</span></span>|@Owner|<span data-ttu-id="1587f-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="1587f-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="1587f-360">2</span><span class="sxs-lookup"><span data-stu-id="1587f-360">2</span></span>|  
|<span data-ttu-id="1587f-361">Table</span><span class="sxs-lookup"><span data-stu-id="1587f-361">Table</span></span>|@Table|<span data-ttu-id="1587f-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-362">TABLE_NAME</span></span>|<span data-ttu-id="1587f-363">3</span><span class="sxs-lookup"><span data-stu-id="1587f-363">3</span></span>|  
|<span data-ttu-id="1587f-364">Colonna</span><span class="sxs-lookup"><span data-stu-id="1587f-364">Column</span></span>|@Column|<span data-ttu-id="1587f-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="1587f-365">COLUMN_NAME</span></span>|<span data-ttu-id="1587f-366">4</span><span class="sxs-lookup"><span data-stu-id="1587f-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1587f-367">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1587f-367">See Also</span></span>  
 [<span data-ttu-id="1587f-368">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="1587f-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
