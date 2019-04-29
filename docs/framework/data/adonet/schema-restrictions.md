---
title: Restrizione dello schema
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 73d2980e-e73c-4987-913a-8ddc93d09144
ms.openlocfilehash: b5044d39d1dc5d2fa7d2ce691cdda7075fa0e32a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878410"
---
# <a name="schema-restrictions"></a><span data-ttu-id="d0893-102">Restrizione dello schema</span><span class="sxs-lookup"><span data-stu-id="d0893-102">Schema Restrictions</span></span>
<span data-ttu-id="d0893-103">Il secondo parametro facoltativo del **GetSchema** è il metodo le restrizioni che vengono usate per limitare la quantità di informazioni sullo schema restituite e viene passata al **GetSchema** metodo come una matrice di stringhe .</span><span class="sxs-lookup"><span data-stu-id="d0893-103">The second optional parameter of the **GetSchema** method is the restrictions that are used to limit the amount of schema information returned, and it is passed to the **GetSchema** method as an array of strings.</span></span> <span data-ttu-id="d0893-104">La posizione nella matrice determina i valori che è possibile passare ed equivale al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="d0893-104">The position in the array determines the values that you can pass, and this is equivalent to the restriction number.</span></span>  
  
 <span data-ttu-id="d0893-105">Nella tabella seguente, ad esempio, vengono descritte le restrizioni supportate dalla raccolta di schemi "Tables" usando il provider di dati .NET Framework per SQL Server:</span><span class="sxs-lookup"><span data-stu-id="d0893-105">For example, the following table describes the restrictions supported by the "Tables" schema collection using the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="d0893-106">Restrizioni aggiuntive per le raccolte di schemi di SQL Server vengono indicate alla fine di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="d0893-106">Additional restrictions for SQL Server schema collections are listed at the end of this topic.</span></span>  
  
|<span data-ttu-id="d0893-107">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-107">Restriction Name</span></span>|<span data-ttu-id="d0893-108">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-108">Parameter Name</span></span>|<span data-ttu-id="d0893-109">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-109">Restriction Default</span></span>|<span data-ttu-id="d0893-110">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-110">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-111">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-111">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-112">TABLE_CATALOG</span></span>|<span data-ttu-id="d0893-113">1</span><span class="sxs-lookup"><span data-stu-id="d0893-113">1</span></span>|  
|<span data-ttu-id="d0893-114">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-114">Owner</span></span>|@Owner|<span data-ttu-id="d0893-115">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-115">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0893-116">2</span><span class="sxs-lookup"><span data-stu-id="d0893-116">2</span></span>|  
|<span data-ttu-id="d0893-117">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-117">Table</span></span>|@Name|<span data-ttu-id="d0893-118">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-118">TABLE_NAME</span></span>|<span data-ttu-id="d0893-119">3</span><span class="sxs-lookup"><span data-stu-id="d0893-119">3</span></span>|  
|<span data-ttu-id="d0893-120">TableType</span><span class="sxs-lookup"><span data-stu-id="d0893-120">TableType</span></span>|@TableType|<span data-ttu-id="d0893-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d0893-121">TABLE_TYPE</span></span>|<span data-ttu-id="d0893-122">4</span><span class="sxs-lookup"><span data-stu-id="d0893-122">4</span></span>|  
  
## <a name="specifying-restriction-values"></a><span data-ttu-id="d0893-123">Impostazione dei valori di restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-123">Specifying Restriction Values</span></span>  
 <span data-ttu-id="d0893-124">Per usare una delle restrizioni della raccolta di schemi "Tables", è sufficiente creare una matrice di stringa con quattro elementi, quindi posizionare un valore nell'elemento che corrisponde al numero della restrizione.</span><span class="sxs-lookup"><span data-stu-id="d0893-124">To use one of the restrictions of the "Tables" schema collection, simply create an array of strings with four elements, then place a value in the element that matches the restriction number.</span></span> <span data-ttu-id="d0893-125">Ad esempio, per limitare le tabelle restituite dal **GetSchema** metodo alle sole tabelle nello schema "Sales", impostare il secondo elemento della matrice su "Sales" prima di passarlo al **GetSchema** (metodo).</span><span class="sxs-lookup"><span data-stu-id="d0893-125">For example, to restrict the tables returned by the **GetSchema** method to only those tables in the "Sales" schema, set the second element of the array to "Sales" before passing it to the **GetSchema** method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0893-126">Le raccolte di restrizioni per `SqlClient` e `OracleClient` includono una colonna `ParameterName` aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d0893-126">The restrictions collections for `SqlClient` and `OracleClient` have an additional `ParameterName` column.</span></span> <span data-ttu-id="d0893-127">La colonna di restrizione predefinita è ancora disponibile per garantire la compatibilità con le versioni precedenti, ma attualmente è ignorata.</span><span class="sxs-lookup"><span data-stu-id="d0893-127">The restriction default column is still there for backwards compatibility, but is currently ignored.</span></span> <span data-ttu-id="d0893-128">Per ridurre il rischio di attacchi SQL injection quando si specificano i valori di restrizione, si consiglia di usare query con parametri invece di sostituire le stringhe.</span><span class="sxs-lookup"><span data-stu-id="d0893-128">Parameterized queries rather than string replacement should be used to minimize the risk of an SQL injection attack when specifying restriction values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0893-129">Il numero di elementi nella matrice deve essere inferiore o uguale al numero di restrizioni supportato per la raccolta di schemi specificato, in caso contrario verrà generato un tipo <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="d0893-129">The number of elements in the array must be less than or equal to the number of restrictions supported for the specified schema collection else an <xref:System.ArgumentException> will be thrown.</span></span> <span data-ttu-id="d0893-130">Il numero di restrizioni può essere inferiore al numero massimo consentito.</span><span class="sxs-lookup"><span data-stu-id="d0893-130">There can be fewer than the maximum number of restrictions.</span></span> <span data-ttu-id="d0893-131">Le restrizioni mancanti verranno considerate null (senza restrizioni).</span><span class="sxs-lookup"><span data-stu-id="d0893-131">The missing restrictions are assumed to be null (unrestricted).</span></span>  
  
 <span data-ttu-id="d0893-132">È possibile eseguire query di un provider gestito .NET Framework per determinare l'elenco delle restrizioni supportate chiamando il **GetSchema** metodo con il nome della raccolta di schemi restrizioni, ovvero "Restrictions".</span><span class="sxs-lookup"><span data-stu-id="d0893-132">You can query a .NET Framework managed provider to determine the list of supported restrictions by calling the **GetSchema** method with the name of the restrictions schema collection, which is "Restrictions".</span></span> <span data-ttu-id="d0893-133">In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco dei nomi delle raccolte, i nomi delle restrizioni, i valori di restrizione predefiniti e i numeri delle restrizioni.</span><span class="sxs-lookup"><span data-stu-id="d0893-133">This will return a <xref:System.Data.DataTable> with a list of the collection names, the restriction names, the default restriction values, and the restriction numbers.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d0893-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="d0893-134">Example</span></span>  
 <span data-ttu-id="d0893-135">Gli esempi seguenti illustrano come usare il <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> metodo del Provider di dati .NET Framework per SQL Server <xref:System.Data.SqlClient.SqlConnection> classe da cui recuperare informazioni sullo schema relative a tutte le tabelle contenute nel **AdventureWorks**database di esempio e per limitare le informazioni restituite alle sole tabelle nello schema "Sales":</span><span class="sxs-lookup"><span data-stu-id="d0893-135">The following examples demonstrate how to use the <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> method of the .NET Framework Data Provider for the SQL Server <xref:System.Data.SqlClient.SqlConnection> class to retrieve schema information about all of the tables contained in the **AdventureWorks** sample database, and to restrict the information returned to only those tables in the "Sales" schema:</span></span>  
  
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
  
## <a name="sql-server-schema-restrictions"></a><span data-ttu-id="d0893-136">Restrizioni per gli schemi di SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0893-136">SQL Server Schema Restrictions</span></span>  
 <span data-ttu-id="d0893-137">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d0893-137">The following tables list the restrictions for SQL Server schema collections.</span></span>  
  
### <a name="users"></a><span data-ttu-id="d0893-138">Utenti</span><span class="sxs-lookup"><span data-stu-id="d0893-138">Users</span></span>  
  
|<span data-ttu-id="d0893-139">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-139">Restriction Name</span></span>|<span data-ttu-id="d0893-140">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-140">Parameter Name</span></span>|<span data-ttu-id="d0893-141">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-141">Restriction Default</span></span>|<span data-ttu-id="d0893-142">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-142">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-143">User_Name</span><span class="sxs-lookup"><span data-stu-id="d0893-143">User_Name</span></span>|@Name|<span data-ttu-id="d0893-144">name</span><span class="sxs-lookup"><span data-stu-id="d0893-144">name</span></span>|<span data-ttu-id="d0893-145">1</span><span class="sxs-lookup"><span data-stu-id="d0893-145">1</span></span>|  
  
### <a name="databases"></a><span data-ttu-id="d0893-146">Database</span><span class="sxs-lookup"><span data-stu-id="d0893-146">Databases</span></span>  
  
|<span data-ttu-id="d0893-147">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-147">Restriction Name</span></span>|<span data-ttu-id="d0893-148">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-148">Parameter Name</span></span>|<span data-ttu-id="d0893-149">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-149">Restriction Default</span></span>|<span data-ttu-id="d0893-150">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-150">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-151">Nome</span><span class="sxs-lookup"><span data-stu-id="d0893-151">Name</span></span>|@Name|<span data-ttu-id="d0893-152">Nome</span><span class="sxs-lookup"><span data-stu-id="d0893-152">Name</span></span>|<span data-ttu-id="d0893-153">1</span><span class="sxs-lookup"><span data-stu-id="d0893-153">1</span></span>|  
  
### <a name="tables"></a><span data-ttu-id="d0893-154">Tabelle</span><span class="sxs-lookup"><span data-stu-id="d0893-154">Tables</span></span>  
  
|<span data-ttu-id="d0893-155">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-155">Restriction Name</span></span>|<span data-ttu-id="d0893-156">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-156">Parameter Name</span></span>|<span data-ttu-id="d0893-157">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-157">Restriction Default</span></span>|<span data-ttu-id="d0893-158">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-158">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-159">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-159">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-160">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-160">TABLE_CATALOG</span></span>|<span data-ttu-id="d0893-161">1</span><span class="sxs-lookup"><span data-stu-id="d0893-161">1</span></span>|  
|<span data-ttu-id="d0893-162">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-162">Owner</span></span>|@Owner|<span data-ttu-id="d0893-163">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-163">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0893-164">2</span><span class="sxs-lookup"><span data-stu-id="d0893-164">2</span></span>|  
|<span data-ttu-id="d0893-165">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-165">Table</span></span>|@Name|<span data-ttu-id="d0893-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-166">TABLE_NAME</span></span>|<span data-ttu-id="d0893-167">3</span><span class="sxs-lookup"><span data-stu-id="d0893-167">3</span></span>|  
|<span data-ttu-id="d0893-168">TableType</span><span class="sxs-lookup"><span data-stu-id="d0893-168">TableType</span></span>|@TableType|<span data-ttu-id="d0893-169">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d0893-169">TABLE_TYPE</span></span>|<span data-ttu-id="d0893-170">4</span><span class="sxs-lookup"><span data-stu-id="d0893-170">4</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="d0893-171">Colonne</span><span class="sxs-lookup"><span data-stu-id="d0893-171">Columns</span></span>  
  
|<span data-ttu-id="d0893-172">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-172">Restriction Name</span></span>|<span data-ttu-id="d0893-173">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-173">Parameter Name</span></span>|<span data-ttu-id="d0893-174">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-174">Restriction Default</span></span>|<span data-ttu-id="d0893-175">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-175">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-176">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-176">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-177">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-177">TABLE_CATALOG</span></span>|<span data-ttu-id="d0893-178">1</span><span class="sxs-lookup"><span data-stu-id="d0893-178">1</span></span>|  
|<span data-ttu-id="d0893-179">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-179">Owner</span></span>|@Owner|<span data-ttu-id="d0893-180">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-180">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0893-181">2</span><span class="sxs-lookup"><span data-stu-id="d0893-181">2</span></span>|  
|<span data-ttu-id="d0893-182">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-182">Table</span></span>|@Table|<span data-ttu-id="d0893-183">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-183">TABLE_NAME</span></span>|<span data-ttu-id="d0893-184">3</span><span class="sxs-lookup"><span data-stu-id="d0893-184">3</span></span>|  
|<span data-ttu-id="d0893-185">Colonna</span><span class="sxs-lookup"><span data-stu-id="d0893-185">Column</span></span>|@Column|<span data-ttu-id="d0893-186">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-186">COLUMN_NAME</span></span>|<span data-ttu-id="d0893-187">4</span><span class="sxs-lookup"><span data-stu-id="d0893-187">4</span></span>|  
  
### <a name="structuredtypemembers"></a><span data-ttu-id="d0893-188">StructuredTypeMembers</span><span class="sxs-lookup"><span data-stu-id="d0893-188">StructuredTypeMembers</span></span>  
  
|<span data-ttu-id="d0893-189">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-189">Restriction Name</span></span>|<span data-ttu-id="d0893-190">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-190">Parameter Name</span></span>|<span data-ttu-id="d0893-191">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-191">Restriction Default</span></span>|<span data-ttu-id="d0893-192">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-192">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-193">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-193">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-194">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-194">TABLE_CATALOG</span></span>|<span data-ttu-id="d0893-195">1</span><span class="sxs-lookup"><span data-stu-id="d0893-195">1</span></span>|  
|<span data-ttu-id="d0893-196">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-196">Owner</span></span>|@Owner|<span data-ttu-id="d0893-197">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-197">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0893-198">2</span><span class="sxs-lookup"><span data-stu-id="d0893-198">2</span></span>|  
|<span data-ttu-id="d0893-199">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-199">Table</span></span>|@Table|<span data-ttu-id="d0893-200">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-200">TABLE_NAME</span></span>|<span data-ttu-id="d0893-201">3</span><span class="sxs-lookup"><span data-stu-id="d0893-201">3</span></span>|  
|<span data-ttu-id="d0893-202">Colonna</span><span class="sxs-lookup"><span data-stu-id="d0893-202">Column</span></span>|@Column|<span data-ttu-id="d0893-203">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-203">COLUMN_NAME</span></span>|<span data-ttu-id="d0893-204">4</span><span class="sxs-lookup"><span data-stu-id="d0893-204">4</span></span>|  
  
### <a name="views"></a><span data-ttu-id="d0893-205">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="d0893-205">Views</span></span>  
  
|<span data-ttu-id="d0893-206">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-206">Restriction Name</span></span>|<span data-ttu-id="d0893-207">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-207">Parameter Name</span></span>|<span data-ttu-id="d0893-208">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-208">Restriction Default</span></span>|<span data-ttu-id="d0893-209">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-209">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-210">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-210">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-211">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-211">TABLE_CATALOG</span></span>|<span data-ttu-id="d0893-212">1</span><span class="sxs-lookup"><span data-stu-id="d0893-212">1</span></span>|  
|<span data-ttu-id="d0893-213">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-213">Owner</span></span>|@Owner|<span data-ttu-id="d0893-214">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-214">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0893-215">2</span><span class="sxs-lookup"><span data-stu-id="d0893-215">2</span></span>|  
|<span data-ttu-id="d0893-216">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-216">Table</span></span>|@Table|<span data-ttu-id="d0893-217">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-217">TABLE_NAME</span></span>|<span data-ttu-id="d0893-218">3</span><span class="sxs-lookup"><span data-stu-id="d0893-218">3</span></span>|  
  
### <a name="viewcolumns"></a><span data-ttu-id="d0893-219">ViewColumns</span><span class="sxs-lookup"><span data-stu-id="d0893-219">ViewColumns</span></span>  
  
|<span data-ttu-id="d0893-220">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-220">Restriction Name</span></span>|<span data-ttu-id="d0893-221">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-221">Parameter Name</span></span>|<span data-ttu-id="d0893-222">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-222">Restriction Default</span></span>|<span data-ttu-id="d0893-223">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-223">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-224">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-224">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-225">VIEW_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-225">VIEW_CATALOG</span></span>|<span data-ttu-id="d0893-226">1</span><span class="sxs-lookup"><span data-stu-id="d0893-226">1</span></span>|  
|<span data-ttu-id="d0893-227">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-227">Owner</span></span>|@Owner|<span data-ttu-id="d0893-228">VIEW_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-228">VIEW_SCHEMA</span></span>|<span data-ttu-id="d0893-229">2</span><span class="sxs-lookup"><span data-stu-id="d0893-229">2</span></span>|  
|<span data-ttu-id="d0893-230">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-230">Table</span></span>|@Table|<span data-ttu-id="d0893-231">VIEW_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-231">VIEW_NAME</span></span>|<span data-ttu-id="d0893-232">3</span><span class="sxs-lookup"><span data-stu-id="d0893-232">3</span></span>|  
|<span data-ttu-id="d0893-233">Colonna</span><span class="sxs-lookup"><span data-stu-id="d0893-233">Column</span></span>|@Column|<span data-ttu-id="d0893-234">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-234">COLUMN_NAME</span></span>|<span data-ttu-id="d0893-235">4</span><span class="sxs-lookup"><span data-stu-id="d0893-235">4</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="d0893-236">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="d0893-236">ProcedureParameters</span></span>  
  
|<span data-ttu-id="d0893-237">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-237">Restriction Name</span></span>|<span data-ttu-id="d0893-238">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-238">Parameter Name</span></span>|<span data-ttu-id="d0893-239">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-239">Restriction Default</span></span>|<span data-ttu-id="d0893-240">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-240">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-241">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-241">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-242">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-242">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d0893-243">1</span><span class="sxs-lookup"><span data-stu-id="d0893-243">1</span></span>|  
|<span data-ttu-id="d0893-244">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-244">Owner</span></span>|@Owner|<span data-ttu-id="d0893-245">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-245">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d0893-246">2</span><span class="sxs-lookup"><span data-stu-id="d0893-246">2</span></span>|  
|<span data-ttu-id="d0893-247">Nome</span><span class="sxs-lookup"><span data-stu-id="d0893-247">Name</span></span>|@Name|<span data-ttu-id="d0893-248">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-248">SPECIFIC_NAME</span></span>|<span data-ttu-id="d0893-249">3</span><span class="sxs-lookup"><span data-stu-id="d0893-249">3</span></span>|  
|<span data-ttu-id="d0893-250">Parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-250">Parameter</span></span>|@Parameter|<span data-ttu-id="d0893-251">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-251">PARAMETER_NAME</span></span>|<span data-ttu-id="d0893-252">4</span><span class="sxs-lookup"><span data-stu-id="d0893-252">4</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="d0893-253">Procedure</span><span class="sxs-lookup"><span data-stu-id="d0893-253">Procedures</span></span>  
  
|<span data-ttu-id="d0893-254">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-254">Restriction Name</span></span>|<span data-ttu-id="d0893-255">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-255">Parameter Name</span></span>|<span data-ttu-id="d0893-256">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-256">Restriction Default</span></span>|<span data-ttu-id="d0893-257">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-257">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-258">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-259">SPECIFIC_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-259">SPECIFIC_CATALOG</span></span>|<span data-ttu-id="d0893-260">1</span><span class="sxs-lookup"><span data-stu-id="d0893-260">1</span></span>|  
|<span data-ttu-id="d0893-261">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-261">Owner</span></span>|@Owner|<span data-ttu-id="d0893-262">SPECIFIC_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-262">SPECIFIC_SCHEMA</span></span>|<span data-ttu-id="d0893-263">2</span><span class="sxs-lookup"><span data-stu-id="d0893-263">2</span></span>|  
|<span data-ttu-id="d0893-264">Nome</span><span class="sxs-lookup"><span data-stu-id="d0893-264">Name</span></span>|@Name|<span data-ttu-id="d0893-265">SPECIFIC_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-265">SPECIFIC_NAME</span></span>|<span data-ttu-id="d0893-266">3</span><span class="sxs-lookup"><span data-stu-id="d0893-266">3</span></span>|  
|<span data-ttu-id="d0893-267">Tipo</span><span class="sxs-lookup"><span data-stu-id="d0893-267">Type</span></span>|@Type|<span data-ttu-id="d0893-268">ROUTINE_TYPE</span><span class="sxs-lookup"><span data-stu-id="d0893-268">ROUTINE_TYPE</span></span>|<span data-ttu-id="d0893-269">4</span><span class="sxs-lookup"><span data-stu-id="d0893-269">4</span></span>|  
  
### <a name="indexcolumns"></a><span data-ttu-id="d0893-270">IndexColumns</span><span class="sxs-lookup"><span data-stu-id="d0893-270">IndexColumns</span></span>  
  
|<span data-ttu-id="d0893-271">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-271">Restriction Name</span></span>|<span data-ttu-id="d0893-272">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-272">Parameter Name</span></span>|<span data-ttu-id="d0893-273">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-273">Restriction Default</span></span>|<span data-ttu-id="d0893-274">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-274">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-275">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-275">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-276">db_name()</span><span class="sxs-lookup"><span data-stu-id="d0893-276">db_name()</span></span>|<span data-ttu-id="d0893-277">1</span><span class="sxs-lookup"><span data-stu-id="d0893-277">1</span></span>|  
|<span data-ttu-id="d0893-278">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-278">Owner</span></span>|@Owner|<span data-ttu-id="d0893-279">user_name()</span><span class="sxs-lookup"><span data-stu-id="d0893-279">user_name()</span></span>|<span data-ttu-id="d0893-280">2</span><span class="sxs-lookup"><span data-stu-id="d0893-280">2</span></span>|  
|<span data-ttu-id="d0893-281">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-281">Table</span></span>|@Table|<span data-ttu-id="d0893-282">o.name</span><span class="sxs-lookup"><span data-stu-id="d0893-282">o.name</span></span>|<span data-ttu-id="d0893-283">3</span><span class="sxs-lookup"><span data-stu-id="d0893-283">3</span></span>|  
|<span data-ttu-id="d0893-284">ConstraintName</span><span class="sxs-lookup"><span data-stu-id="d0893-284">ConstraintName</span></span>|@ConstraintName|<span data-ttu-id="d0893-285">x.name</span><span class="sxs-lookup"><span data-stu-id="d0893-285">x.name</span></span>|<span data-ttu-id="d0893-286">4</span><span class="sxs-lookup"><span data-stu-id="d0893-286">4</span></span>|  
|<span data-ttu-id="d0893-287">Colonna</span><span class="sxs-lookup"><span data-stu-id="d0893-287">Column</span></span>|@Column|<span data-ttu-id="d0893-288">c.name</span><span class="sxs-lookup"><span data-stu-id="d0893-288">c.name</span></span>|<span data-ttu-id="d0893-289">5</span><span class="sxs-lookup"><span data-stu-id="d0893-289">5</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="d0893-290">Indexes</span><span class="sxs-lookup"><span data-stu-id="d0893-290">Indexes</span></span>  
  
|<span data-ttu-id="d0893-291">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-291">Restriction Name</span></span>|<span data-ttu-id="d0893-292">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-292">Parameter Name</span></span>|<span data-ttu-id="d0893-293">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-293">Restriction Default</span></span>|<span data-ttu-id="d0893-294">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-294">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-295">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-295">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-296">db_name()</span><span class="sxs-lookup"><span data-stu-id="d0893-296">db_name()</span></span>|<span data-ttu-id="d0893-297">1</span><span class="sxs-lookup"><span data-stu-id="d0893-297">1</span></span>|  
|<span data-ttu-id="d0893-298">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-298">Owner</span></span>|@Owner|<span data-ttu-id="d0893-299">user_name()</span><span class="sxs-lookup"><span data-stu-id="d0893-299">user_name()</span></span>|<span data-ttu-id="d0893-300">2</span><span class="sxs-lookup"><span data-stu-id="d0893-300">2</span></span>|  
|<span data-ttu-id="d0893-301">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-301">Table</span></span>|@Table|<span data-ttu-id="d0893-302">o.name</span><span class="sxs-lookup"><span data-stu-id="d0893-302">o.name</span></span>|<span data-ttu-id="d0893-303">3</span><span class="sxs-lookup"><span data-stu-id="d0893-303">3</span></span>|  
  
### <a name="userdefinedtypes"></a><span data-ttu-id="d0893-304">UserDefinedTypes</span><span class="sxs-lookup"><span data-stu-id="d0893-304">UserDefinedTypes</span></span>  
  
|<span data-ttu-id="d0893-305">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-305">Restriction Name</span></span>|<span data-ttu-id="d0893-306">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-306">Parameter Name</span></span>|<span data-ttu-id="d0893-307">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-307">Restriction Default</span></span>|<span data-ttu-id="d0893-308">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-308">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-309">assembly_name</span><span class="sxs-lookup"><span data-stu-id="d0893-309">assembly_name</span></span>|@AssemblyName|<span data-ttu-id="d0893-310">assemblies.name</span><span class="sxs-lookup"><span data-stu-id="d0893-310">assemblies.name</span></span>|<span data-ttu-id="d0893-311">1</span><span class="sxs-lookup"><span data-stu-id="d0893-311">1</span></span>|  
|<span data-ttu-id="d0893-312">udt_name</span><span class="sxs-lookup"><span data-stu-id="d0893-312">udt_name</span></span>|@UDTName|<span data-ttu-id="d0893-313">types.assembly_class</span><span class="sxs-lookup"><span data-stu-id="d0893-313">types.assembly_class</span></span>|<span data-ttu-id="d0893-314">2</span><span class="sxs-lookup"><span data-stu-id="d0893-314">2</span></span>|  
  
### <a name="foreignkeys"></a><span data-ttu-id="d0893-315">ForeignKeys</span><span class="sxs-lookup"><span data-stu-id="d0893-315">ForeignKeys</span></span>  
  
|<span data-ttu-id="d0893-316">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-316">Restriction Name</span></span>|<span data-ttu-id="d0893-317">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-317">Parameter Name</span></span>|<span data-ttu-id="d0893-318">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-318">Restriction Default</span></span>|<span data-ttu-id="d0893-319">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-319">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-320">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-320">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-321">CONSTRAINT_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-321">CONSTRAINT_CATALOG</span></span>|<span data-ttu-id="d0893-322">1</span><span class="sxs-lookup"><span data-stu-id="d0893-322">1</span></span>|  
|<span data-ttu-id="d0893-323">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-323">Owner</span></span>|@Owner|<span data-ttu-id="d0893-324">CONSTRAINT_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-324">CONSTRAINT_SCHEMA</span></span>|<span data-ttu-id="d0893-325">2</span><span class="sxs-lookup"><span data-stu-id="d0893-325">2</span></span>|  
|<span data-ttu-id="d0893-326">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-326">Table</span></span>|@Table|<span data-ttu-id="d0893-327">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-327">TABLE_NAME</span></span>|<span data-ttu-id="d0893-328">3</span><span class="sxs-lookup"><span data-stu-id="d0893-328">3</span></span>|  
|<span data-ttu-id="d0893-329">Nome</span><span class="sxs-lookup"><span data-stu-id="d0893-329">Name</span></span>|@Name|<span data-ttu-id="d0893-330">CONSTRAINT_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-330">CONSTRAINT_NAME</span></span>|<span data-ttu-id="d0893-331">4</span><span class="sxs-lookup"><span data-stu-id="d0893-331">4</span></span>|  
  
## <a name="sql-server-2008-schema-restrictions"></a><span data-ttu-id="d0893-332">Restrizioni per gli schemi di SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="d0893-332">SQL Server 2008 Schema Restrictions</span></span>  
 <span data-ttu-id="d0893-333">Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d0893-333">The following tables list the restrictions for SQL Server 2008 schema collections.</span></span> <span data-ttu-id="d0893-334">Queste restrizioni sono valide a partire dalla versione 3.5 SP1 di .NET Framework e da SQL Server 2008.</span><span class="sxs-lookup"><span data-stu-id="d0893-334">These restrictions are valid beginning with version 3.5 SP1 of the .NET Framework and SQL Server 2008.</span></span> <span data-ttu-id="d0893-335">Le restrizioni non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="d0893-335">They are not supported in earlier versions of the .NET Framework and SQL Server.</span></span>  
  
### <a name="columnsetcolumns"></a><span data-ttu-id="d0893-336">ColumnSetColumns</span><span class="sxs-lookup"><span data-stu-id="d0893-336">ColumnSetColumns</span></span>  
  
|<span data-ttu-id="d0893-337">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-337">Restriction Name</span></span>|<span data-ttu-id="d0893-338">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-338">Parameter Name</span></span>|<span data-ttu-id="d0893-339">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-339">Restriction Default</span></span>|<span data-ttu-id="d0893-340">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-340">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-341">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-341">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-342">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-342">TABLE_CATALOG</span></span>|<span data-ttu-id="d0893-343">1</span><span class="sxs-lookup"><span data-stu-id="d0893-343">1</span></span>|  
|<span data-ttu-id="d0893-344">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-344">Owner</span></span>|@Owner|<span data-ttu-id="d0893-345">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-345">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0893-346">2</span><span class="sxs-lookup"><span data-stu-id="d0893-346">2</span></span>|  
|<span data-ttu-id="d0893-347">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-347">Table</span></span>|@Table|<span data-ttu-id="d0893-348">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-348">TABLE_NAME</span></span>|<span data-ttu-id="d0893-349">3</span><span class="sxs-lookup"><span data-stu-id="d0893-349">3</span></span>|  
  
### <a name="allcolumns"></a><span data-ttu-id="d0893-350">AllColumns</span><span class="sxs-lookup"><span data-stu-id="d0893-350">AllColumns</span></span>  
  
|<span data-ttu-id="d0893-351">Nome della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-351">Restriction Name</span></span>|<span data-ttu-id="d0893-352">Nome parametro</span><span class="sxs-lookup"><span data-stu-id="d0893-352">Parameter Name</span></span>|<span data-ttu-id="d0893-353">Impostazione predefinita della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-353">Restriction Default</span></span>|<span data-ttu-id="d0893-354">Numero della restrizione</span><span class="sxs-lookup"><span data-stu-id="d0893-354">Restriction Number</span></span>|  
|----------------------|--------------------|-------------------------|------------------------|  
|<span data-ttu-id="d0893-355">Catalog</span><span class="sxs-lookup"><span data-stu-id="d0893-355">Catalog</span></span>|@Catalog|<span data-ttu-id="d0893-356">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="d0893-356">TABLE_CATALOG</span></span>|<span data-ttu-id="d0893-357">1</span><span class="sxs-lookup"><span data-stu-id="d0893-357">1</span></span>|  
|<span data-ttu-id="d0893-358">Owner</span><span class="sxs-lookup"><span data-stu-id="d0893-358">Owner</span></span>|@Owner|<span data-ttu-id="d0893-359">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="d0893-359">TABLE_SCHEMA</span></span>|<span data-ttu-id="d0893-360">2</span><span class="sxs-lookup"><span data-stu-id="d0893-360">2</span></span>|  
|<span data-ttu-id="d0893-361">Tabella</span><span class="sxs-lookup"><span data-stu-id="d0893-361">Table</span></span>|@Table|<span data-ttu-id="d0893-362">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-362">TABLE_NAME</span></span>|<span data-ttu-id="d0893-363">3</span><span class="sxs-lookup"><span data-stu-id="d0893-363">3</span></span>|  
|<span data-ttu-id="d0893-364">Colonna</span><span class="sxs-lookup"><span data-stu-id="d0893-364">Column</span></span>|@Column|<span data-ttu-id="d0893-365">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="d0893-365">COLUMN_NAME</span></span>|<span data-ttu-id="d0893-366">4</span><span class="sxs-lookup"><span data-stu-id="d0893-366">4</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0893-367">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d0893-367">See also</span></span>

- [<span data-ttu-id="d0893-368">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="d0893-368">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
