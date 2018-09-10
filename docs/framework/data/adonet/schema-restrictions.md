---
title: Restrizione dello schema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: 040ecd8a2ce223f89601de735b77ccc81638c7af
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198608"
---
# <a name="schema-restrictions"></a><span data-ttu-id="9a7e6-102">Restrizione dello schema</span><span class="sxs-lookup"><span data-stu-id="9a7e6-102">Schema Restrictions</span></span>
<span data-ttu-id="9a7e6-103">Il secondo parametro facoltativo del **GetSchema** è il metodo le restrizioni che vengono usate per limitare la quantità di informazioni sullo schema restituite e viene passata al **GetSchema** metodo come una matrice di stringhe .</span><span class="sxs-lookup"><span data-stu-id="9a7e6-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="9a7e6-104">La posizione nella matrice determina i valori che è possibile passare ed equivale al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="9a7e6-105">Nella tabella seguente, ad esempio, vengono descritte le restrizioni supportate dalla raccolta di schemi "Tables" usando il provider di dati .NET Framework per SQL Server:</span><span class="sxs-lookup"><span data-stu-id="9a7e6-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="9a7e6-106">Restrizioni aggiuntive per le raccolte di schemi di SQL Server vengono indicate alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="9a7e6-107">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-107">Restriction Name</span></span>|<span data-ttu-id="9a7e6-108">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-108">Parameter Name</span></span>|<span data-ttu-id="9a7e6-109">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-109">Restriction Default</span></span>|<span data-ttu-id="9a7e6-110">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-111">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-112">TABLE_CATALOG</span></span>|<span data-ttu-id="9a7e6-113">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-113">1</span></span>|  
|<span data-ttu-id="9a7e6-114">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-114">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="9a7e6-116">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-116">2</span></span>|  
|<span data-ttu-id="9a7e6-117">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-117">Table</span></span>|@Name|<span data-ttu-id="9a7e6-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-118">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-119">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-119">3</span></span>|  
|<span data-ttu-id="9a7e6-120">TableType</span><span class="sxs-lookup"><span data-stu-id="9a7e6-120">TableType</span></span>|@TableType|<span data-ttu-id="9a7e6-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a7e6-121">TABLE_TYPE</span></span>|<span data-ttu-id="9a7e6-122">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="9a7e6-123">Impostazione dei valori di restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="9a7e6-124">Per usare una delle restrizioni della raccolta di schemi "Tables", è sufficiente creare una matrice di stringa con quattro elementi, quindi posizionare un valore nell'elemento che corrisponde al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="9a7e6-125">Ad esempio, per limitare le tabelle restituite dal **GetSchema** metodo alle sole tabelle nello schema "Sales", impostare il secondo elemento della matrice su "Sales" prima di passarlo al **GetSchema** (metodo).</span><span class="sxs-lookup"><span data-stu-id="9a7e6-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a7e6-126">Le raccolte di restrizioni per `SqlClient` e `OracleClient` includono una colonna `ParameterName` aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="9a7e6-127">La colonna di restrizione predefinita è ancora disponibile per garantire la compatibilità con le versioni precedenti, ma attualmente è ignorata.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="9a7e6-128">Per ridurre il rischio di attacchi SQL injection quando si specificano i valori di restrizione, si consiglia di usare query con parametri invece di sostituire le stringhe.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a7e6-129">Il numero di elementi nella matrice deve essere inferiore o uguale al numero di restrizioni supportato per la raccolta di schemi specificato, in caso contrario verrà generato un tipo <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="9a7e6-130">Il numero di restrizioni può essere inferiore al numero massimo consentito.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="9a7e6-131">Le restrizioni mancanti verranno considerate null (senza restrizioni).</span><span class="sxs-lookup"><span data-stu-id="9a7e6-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="9a7e6-132">È possibile eseguire query di un provider gestito .NET Framework per determinare l'elenco delle restrizioni supportate chiamando il **GetSchema** metodo con il nome della raccolta di schemi restrizioni, ovvero "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="9a7e6-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="9a7e6-133">In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco dei nomi delle raccolte, i nomi delle restrizioni, i valori di restrizione predefiniti e i numeri delle restrizioni.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="9a7e6-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="9a7e6-134">Example</span></span>  
 <span data-ttu-id="9a7e6-135">Gli esempi seguenti illustrano come usare il <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metodo del Provider di dati .NET Framework per SQL Server <xref:System.Data.SqlClient.SqlConnection> classe da cui recuperare informazioni sullo schema relative a tutte le tabelle contenute nel **AdventureWorks**database di esempio e per limitare le informazioni restituite alle sole tabelle nello schema "Sales":</span><span class="sxs-lookup"><span data-stu-id="9a7e6-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="9a7e6-136">Restrizioni per gli schemi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="9a7e6-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="9a7e6-137">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="9a7e6-138">Utenti</span><span class="sxs-lookup"><span data-stu-id="9a7e6-138">Users</span></span>  
  
|<span data-ttu-id="9a7e6-139">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-139">Restriction Name</span></span>|<span data-ttu-id="9a7e6-140">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-140">Parameter Name</span></span>|<span data-ttu-id="9a7e6-141">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-141">Restriction Default</span></span>|<span data-ttu-id="9a7e6-142">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-143">User_Name</span></span>|@Name|<span data-ttu-id="9a7e6-144">name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-144">name</span></span>|<span data-ttu-id="9a7e6-145">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="9a7e6-146">Database</span><span class="sxs-lookup"><span data-stu-id="9a7e6-146">Databases</span></span>  
  
|<span data-ttu-id="9a7e6-147">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-147">Restriction Name</span></span>|<span data-ttu-id="9a7e6-148">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-148">Parameter Name</span></span>|<span data-ttu-id="9a7e6-149">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-149">Restriction Default</span></span>|<span data-ttu-id="9a7e6-150">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-151">nome</span><span class="sxs-lookup"><span data-stu-id="9a7e6-151">Name</span></span>|@Name|<span data-ttu-id="9a7e6-152">nome</span><span class="sxs-lookup"><span data-stu-id="9a7e6-152">Name</span></span>|<span data-ttu-id="9a7e6-153">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="9a7e6-154">Tabelle</span><span class="sxs-lookup"><span data-stu-id="9a7e6-154">Tables</span></span>  
  
|<span data-ttu-id="9a7e6-155">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-155">Restriction Name</span></span>|<span data-ttu-id="9a7e6-156">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-156">Parameter Name</span></span>|<span data-ttu-id="9a7e6-157">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-157">Restriction Default</span></span>|<span data-ttu-id="9a7e6-158">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-159">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-160">TABLE_CATALOG</span></span>|<span data-ttu-id="9a7e6-161">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-161">1</span></span>|  
|<span data-ttu-id="9a7e6-162">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-162">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="9a7e6-164">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-164">2</span></span>|  
|<span data-ttu-id="9a7e6-165">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-165">Table</span></span>|@Name|<span data-ttu-id="9a7e6-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-166">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-167">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-167">3</span></span>|  
|<span data-ttu-id="9a7e6-168">TableType</span><span class="sxs-lookup"><span data-stu-id="9a7e6-168">TableType</span></span>|@TableType|<span data-ttu-id="9a7e6-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a7e6-169">TABLE_TYPE</span></span>|<span data-ttu-id="9a7e6-170">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="9a7e6-171">Colonne</span><span class="sxs-lookup"><span data-stu-id="9a7e6-171">Columns</span></span>  
  
|<span data-ttu-id="9a7e6-172">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-172">Restriction Name</span></span>|<span data-ttu-id="9a7e6-173">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-173">Parameter Name</span></span>|<span data-ttu-id="9a7e6-174">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-174">Restriction Default</span></span>|<span data-ttu-id="9a7e6-175">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-176">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-177">TABLE_CATALOG</span></span>|<span data-ttu-id="9a7e6-178">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-178">1</span></span>|  
|<span data-ttu-id="9a7e6-179">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-179">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="9a7e6-181">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-181">2</span></span>|  
|<span data-ttu-id="9a7e6-182">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-182">Table</span></span>|@Table|<span data-ttu-id="9a7e6-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-183">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-184">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-184">3</span></span>|  
|<span data-ttu-id="9a7e6-185">Colonna</span><span class="sxs-lookup"><span data-stu-id="9a7e6-185">Column</span></span>|@Column|<span data-ttu-id="9a7e6-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-186">COLUMN_NAME</span></span>|<span data-ttu-id="9a7e6-187">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="9a7e6-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="9a7e6-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="9a7e6-189">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-189">Restriction Name</span></span>|<span data-ttu-id="9a7e6-190">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-190">Parameter Name</span></span>|<span data-ttu-id="9a7e6-191">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-191">Restriction Default</span></span>|<span data-ttu-id="9a7e6-192">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-193">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-194">TABLE_CATALOG</span></span>|<span data-ttu-id="9a7e6-195">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-195">1</span></span>|  
|<span data-ttu-id="9a7e6-196">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-196">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="9a7e6-198">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-198">2</span></span>|  
|<span data-ttu-id="9a7e6-199">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-199">Table</span></span>|@Table|<span data-ttu-id="9a7e6-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-200">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-201">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-201">3</span></span>|  
|<span data-ttu-id="9a7e6-202">Colonna</span><span class="sxs-lookup"><span data-stu-id="9a7e6-202">Column</span></span>|@Column|<span data-ttu-id="9a7e6-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-203">COLUMN_NAME</span></span>|<span data-ttu-id="9a7e6-204">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="9a7e6-205">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="9a7e6-205">Views</span></span>  
  
|<span data-ttu-id="9a7e6-206">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-206">Restriction Name</span></span>|<span data-ttu-id="9a7e6-207">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-207">Parameter Name</span></span>|<span data-ttu-id="9a7e6-208">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-208">Restriction Default</span></span>|<span data-ttu-id="9a7e6-209">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-210">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-211">TABLE_CATALOG</span></span>|<span data-ttu-id="9a7e6-212">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-212">1</span></span>|  
|<span data-ttu-id="9a7e6-213">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-213">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="9a7e6-215">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-215">2</span></span>|  
|<span data-ttu-id="9a7e6-216">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-216">Table</span></span>|@Table|<span data-ttu-id="9a7e6-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-217">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-218">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="9a7e6-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="9a7e6-219">ViewColumns</span></span>  
  
|<span data-ttu-id="9a7e6-220">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-220">Restriction Name</span></span>|<span data-ttu-id="9a7e6-221">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-221">Parameter Name</span></span>|<span data-ttu-id="9a7e6-222">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-222">Restriction Default</span></span>|<span data-ttu-id="9a7e6-223">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-224">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-225">VIEW_CATALOG</span></span>|<span data-ttu-id="9a7e6-226">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-226">1</span></span>|  
|<span data-ttu-id="9a7e6-227">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-227">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="9a7e6-229">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-229">2</span></span>|  
|<span data-ttu-id="9a7e6-230">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-230">Table</span></span>|@Table|<span data-ttu-id="9a7e6-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-231">VIEW_NAME</span></span>|<span data-ttu-id="9a7e6-232">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-232">3</span></span>|  
|<span data-ttu-id="9a7e6-233">Colonna</span><span class="sxs-lookup"><span data-stu-id="9a7e6-233">Column</span></span>|@Column|<span data-ttu-id="9a7e6-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-234">COLUMN_NAME</span></span>|<span data-ttu-id="9a7e6-235">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="9a7e6-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="9a7e6-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="9a7e6-237">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-237">Restriction Name</span></span>|<span data-ttu-id="9a7e6-238">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-238">Parameter Name</span></span>|<span data-ttu-id="9a7e6-239">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-239">Restriction Default</span></span>|<span data-ttu-id="9a7e6-240">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-241">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="9a7e6-243">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-243">1</span></span>|  
|<span data-ttu-id="9a7e6-244">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-244">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="9a7e6-246">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-246">2</span></span>|  
|<span data-ttu-id="9a7e6-247">nome</span><span class="sxs-lookup"><span data-stu-id="9a7e6-247">Name</span></span>|@Name|<span data-ttu-id="9a7e6-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="9a7e6-249">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-249">3</span></span>|  
|<span data-ttu-id="9a7e6-250">Parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-250">Parameter</span></span>|@Parameter|<span data-ttu-id="9a7e6-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-251">PARAMETER_NAME</span></span>|<span data-ttu-id="9a7e6-252">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="9a7e6-253">Procedure</span><span class="sxs-lookup"><span data-stu-id="9a7e6-253">Procedures</span></span>  
  
|<span data-ttu-id="9a7e6-254">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-254">Restriction Name</span></span>|<span data-ttu-id="9a7e6-255">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-255">Parameter Name</span></span>|<span data-ttu-id="9a7e6-256">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-256">Restriction Default</span></span>|<span data-ttu-id="9a7e6-257">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-258">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="9a7e6-260">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-260">1</span></span>|  
|<span data-ttu-id="9a7e6-261">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-261">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="9a7e6-263">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-263">2</span></span>|  
|<span data-ttu-id="9a7e6-264">nome</span><span class="sxs-lookup"><span data-stu-id="9a7e6-264">Name</span></span>|@Name|<span data-ttu-id="9a7e6-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="9a7e6-266">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-266">3</span></span>|  
|<span data-ttu-id="9a7e6-267">Tipo</span><span class="sxs-lookup"><span data-stu-id="9a7e6-267">Type</span></span>|@Type|<span data-ttu-id="9a7e6-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="9a7e6-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="9a7e6-269">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="9a7e6-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="9a7e6-270">IndexColumns</span></span>  
  
|<span data-ttu-id="9a7e6-271">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-271">Restriction Name</span></span>|<span data-ttu-id="9a7e6-272">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-272">Parameter Name</span></span>|<span data-ttu-id="9a7e6-273">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-273">Restriction Default</span></span>|<span data-ttu-id="9a7e6-274">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-275">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="9a7e6-276">db_name()</span></span>|<span data-ttu-id="9a7e6-277">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-277">1</span></span>|  
|<span data-ttu-id="9a7e6-278">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-278">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="9a7e6-279">user_name()</span></span>|<span data-ttu-id="9a7e6-280">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-280">2</span></span>|  
|<span data-ttu-id="9a7e6-281">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-281">Table</span></span>|@Table|<span data-ttu-id="9a7e6-282">o.name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-282">o.name</span></span>|<span data-ttu-id="9a7e6-283">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-283">3</span></span>|  
|<span data-ttu-id="9a7e6-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="9a7e6-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="9a7e6-285">x.name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-285">x.name</span></span>|<span data-ttu-id="9a7e6-286">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-286">4</span></span>|  
|<span data-ttu-id="9a7e6-287">Colonna</span><span class="sxs-lookup"><span data-stu-id="9a7e6-287">Column</span></span>|@Column|<span data-ttu-id="9a7e6-288">c.name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-288">c.name</span></span>|<span data-ttu-id="9a7e6-289">5</span><span class="sxs-lookup"><span data-stu-id="9a7e6-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="9a7e6-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="9a7e6-290">Indexes</span></span>  
  
|<span data-ttu-id="9a7e6-291">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-291">Restriction Name</span></span>|<span data-ttu-id="9a7e6-292">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-292">Parameter Name</span></span>|<span data-ttu-id="9a7e6-293">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-293">Restriction Default</span></span>|<span data-ttu-id="9a7e6-294">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-295">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="9a7e6-296">db_name()</span></span>|<span data-ttu-id="9a7e6-297">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-297">1</span></span>|  
|<span data-ttu-id="9a7e6-298">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-298">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="9a7e6-299">user_name()</span></span>|<span data-ttu-id="9a7e6-300">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-300">2</span></span>|  
|<span data-ttu-id="9a7e6-301">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-301">Table</span></span>|@Table|<span data-ttu-id="9a7e6-302">o.name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-302">o.name</span></span>|<span data-ttu-id="9a7e6-303">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="9a7e6-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="9a7e6-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="9a7e6-305">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-305">Restriction Name</span></span>|<span data-ttu-id="9a7e6-306">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-306">Parameter Name</span></span>|<span data-ttu-id="9a7e6-307">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-307">Restriction Default</span></span>|<span data-ttu-id="9a7e6-308">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="9a7e6-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-310">assemblies.name</span></span>|<span data-ttu-id="9a7e6-311">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-311">1</span></span>|  
|<span data-ttu-id="9a7e6-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="9a7e6-312">udt_name</span></span>|@UDTName|<span data-ttu-id="9a7e6-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="9a7e6-313">types.assembly_class</span></span>|<span data-ttu-id="9a7e6-314">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="9a7e6-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="9a7e6-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="9a7e6-316">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-316">Restriction Name</span></span>|<span data-ttu-id="9a7e6-317">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-317">Parameter Name</span></span>|<span data-ttu-id="9a7e6-318">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-318">Restriction Default</span></span>|<span data-ttu-id="9a7e6-319">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-320">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="9a7e6-322">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-322">1</span></span>|  
|<span data-ttu-id="9a7e6-323">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-323">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="9a7e6-325">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-325">2</span></span>|  
|<span data-ttu-id="9a7e6-326">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-326">Table</span></span>|@Table|<span data-ttu-id="9a7e6-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-327">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-328">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-328">3</span></span>|  
|<span data-ttu-id="9a7e6-329">nome</span><span class="sxs-lookup"><span data-stu-id="9a7e6-329">Name</span></span>|@Name|<span data-ttu-id="9a7e6-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="9a7e6-331">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="9a7e6-332">Restrizioni per gli schemi di SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="9a7e6-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="9a7e6-333">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="9a7e6-334">Queste restrizioni sono valide a partire dalla versione 3.5 SP1 di .NET Framework e da SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="9a7e6-335">Le restrizioni non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9a7e6-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="9a7e6-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="9a7e6-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="9a7e6-337">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-337">Restriction Name</span></span>|<span data-ttu-id="9a7e6-338">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-338">Parameter Name</span></span>|<span data-ttu-id="9a7e6-339">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-339">Restriction Default</span></span>|<span data-ttu-id="9a7e6-340">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-341">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-342">TABLE_CATALOG</span></span>|<span data-ttu-id="9a7e6-343">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-343">1</span></span>|  
|<span data-ttu-id="9a7e6-344">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-344">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="9a7e6-346">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-346">2</span></span>|  
|<span data-ttu-id="9a7e6-347">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-347">Table</span></span>|@Table|<span data-ttu-id="9a7e6-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-348">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-349">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="9a7e6-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="9a7e6-350">AllColumns</span></span>  
  
|<span data-ttu-id="9a7e6-351">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-351">Restriction Name</span></span>|<span data-ttu-id="9a7e6-352">Nome del parametro</span><span class="sxs-lookup"><span data-stu-id="9a7e6-352">Parameter Name</span></span>|<span data-ttu-id="9a7e6-353">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-353">Restriction Default</span></span>|<span data-ttu-id="9a7e6-354">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="9a7e6-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="9a7e6-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="9a7e6-355">Catalog</span></span>|@Catalog|<span data-ttu-id="9a7e6-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="9a7e6-356">TABLE_CATALOG</span></span>|<span data-ttu-id="9a7e6-357">1</span><span class="sxs-lookup"><span data-stu-id="9a7e6-357">1</span></span>|  
|<span data-ttu-id="9a7e6-358">Owner</span><span class="sxs-lookup"><span data-stu-id="9a7e6-358">Owner</span></span>|@Owner|<span data-ttu-id="9a7e6-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="9a7e6-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="9a7e6-360">2</span><span class="sxs-lookup"><span data-stu-id="9a7e6-360">2</span></span>|  
|<span data-ttu-id="9a7e6-361">Tabella</span><span class="sxs-lookup"><span data-stu-id="9a7e6-361">Table</span></span>|@Table|<span data-ttu-id="9a7e6-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-362">TABLE_NAME</span></span>|<span data-ttu-id="9a7e6-363">3</span><span class="sxs-lookup"><span data-stu-id="9a7e6-363">3</span></span>|  
|<span data-ttu-id="9a7e6-364">Colonna</span><span class="sxs-lookup"><span data-stu-id="9a7e6-364">Column</span></span>|@Column|<span data-ttu-id="9a7e6-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="9a7e6-365">COLUMN_NAME</span></span>|<span data-ttu-id="9a7e6-366">4</span><span class="sxs-lookup"><span data-stu-id="9a7e6-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a7e6-367">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a7e6-367">See Also</span></span>  
 [<span data-ttu-id="9a7e6-368">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="9a7e6-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
