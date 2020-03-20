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
# <a name="schema-restrictions"></a>Restrizione dello schema
Il secondo parametro facoltativo del **GetSchema** metodo è le restrizioni che vengono utilizzate per limitare la quantità di informazioni sullo schema restituito e viene passato al **GetSchema** metodo come matrice di stringhe. La posizione nella matrice determina i valori che è possibile passare ed equivale al numero della restrizione.  
  
 Nella tabella seguente, ad esempio, vengono descritte le restrizioni supportate dalla raccolta di schemi "Tables" usando il provider di dati .NET Framework per SQL Server: Restrizioni aggiuntive per le raccolte di schemi di SQL Server vengono indicate alla fine di questo argomento.  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|TABLE_CATALOG|1|  
|Proprietario|@Owner|TABLE_SCHEMA|2|  
|Tabella|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
## <a name="specifying-restriction-values"></a>Impostazione dei valori di restrizione  
 Per usare una delle restrizioni della raccolta di schemi "Tables", è sufficiente creare una matrice di stringa con quattro elementi, quindi posizionare un valore nell'elemento che corrisponde al numero della restrizione. Ad esempio, per limitare le tabelle restituite dal metodo **GetSchema** solo a tali tabelle nello schema "Sales", impostare il secondo elemento della matrice su "Sales" prima di passarlo al metodo **GetSchema.**  
  
> [!NOTE]
> Le raccolte di restrizioni per `SqlClient` e `OracleClient` includono una colonna `ParameterName` aggiuntiva. La colonna di restrizione predefinita è ancora disponibile per garantire la compatibilità con le versioni precedenti, ma attualmente è ignorata. Per ridurre il rischio di attacchi SQL injection quando si specificano i valori di restrizione, si consiglia di usare query con parametri invece di sostituire le stringhe.  
  
> [!NOTE]
> Il numero di elementi nella matrice deve essere inferiore o uguale al numero di restrizioni supportato per la raccolta di schemi specificato, in caso contrario verrà generato un tipo <xref:System.ArgumentException>. Il numero di restrizioni può essere inferiore al numero massimo consentito. Le restrizioni mancanti verranno considerate null (senza restrizioni).  
  
 È possibile eseguire una query su un provider gestito .NET Framework per determinare l'elenco delle restrizioni supportate chiamando il **metodo GetSchema** con il nome dell'insieme di schemi di restrizioni, ovvero "Restrictions". In questo modo verrà restituito un oggetto <xref:System.Data.DataTable> con un elenco dei nomi delle raccolte, i nomi delle restrizioni, i valori di restrizione predefiniti e i numeri delle restrizioni.  
  
### <a name="example"></a>Esempio  
 Negli esempi seguenti viene <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A> illustrato come utilizzare il metodo del <xref:System.Data.SqlClient.SqlConnection> provider di dati .NET Framework per la classe SQL Server per recuperare informazioni sullo schema relative a tutte le tabelle contenute nel database di esempio **AdventureWorks** e per limitare le informazioni restituite solo a tali tabelle nello schema "Sales":  
  
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
  
## <a name="sql-server-schema-restrictions"></a>Restrizioni per gli schemi di SQL Server  
 Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server.  
  
### <a name="users"></a>Utenti  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|User_Name|@Name|name|1|  
  
### <a name="databases"></a>Database  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Nome|@Name|Nome|1|  
  
### <a name="tables"></a>Tabelle  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|TABLE_CATALOG|1|  
|Proprietario|@Owner|TABLE_SCHEMA|2|  
|Tabella|@Name|TABLE_NAME|3|  
|TableType|@TableType|TABLE_TYPE|4|  
  
### <a name="columns"></a>Colonne  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|TABLE_CATALOG|1|  
|Proprietario|@Owner|TABLE_SCHEMA|2|  
|Tabella|@Table|TABLE_NAME|3|  
|Colonna|@Column|COLUMN_NAME|4|  
  
### <a name="structuredtypemembers"></a>StructuredTypeMembers  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|TABLE_CATALOG|1|  
|Proprietario|@Owner|TABLE_SCHEMA|2|  
|Tabella|@Table|TABLE_NAME|3|  
|Colonna|@Column|COLUMN_NAME|4|  
  
### <a name="views"></a>Viste  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|TABLE_CATALOG|1|  
|Proprietario|@Owner|TABLE_SCHEMA|2|  
|Tabella|@Table|TABLE_NAME|3|  
  
### <a name="viewcolumns"></a>ViewColumns  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|VIEW_CATALOG|1|  
|Proprietario|@Owner|VIEW_SCHEMA|2|  
|Tabella|@Table|VIEW_NAME|3|  
|Colonna|@Column|COLUMN_NAME|4|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|SPECIFIC_CATALOG|1|  
|Proprietario|@Owner|SPECIFIC_SCHEMA|2|  
|Nome|@Name|SPECIFIC_NAME|3|  
|Parametro|@Parameter|PARAMETER_NAME|4|  
  
### <a name="procedures"></a>Procedure  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|SPECIFIC_CATALOG|1|  
|Proprietario|@Owner|SPECIFIC_SCHEMA|2|  
|Nome|@Name|SPECIFIC_NAME|3|  
|Type|@Type|ROUTINE_TYPE|4|  
  
### <a name="indexcolumns"></a>IndexColumns  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|db_name()|1|  
|Proprietario|@Owner|user_name()|2|  
|Tabella|@Table|o.name|3|  
|ConstraintName|@ConstraintName|x.name|4|  
|Colonna|@Column|c.name|5|  
  
### <a name="indexes"></a>Indici  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|db_name()|1|  
|Proprietario|@Owner|user_name()|2|  
|Tabella|@Table|o.name|3|  
  
### <a name="userdefinedtypes"></a>UserDefinedTypes  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|assembly_name|@AssemblyName|assemblies.name|1|  
|udt_name|@UDTName|types.assembly_class|2|  
  
### <a name="foreignkeys"></a>ForeignKeys  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|CONSTRAINT_CATALOG|1|  
|Proprietario|@Owner|CONSTRAINT_SCHEMA|2|  
|Tabella|@Table|TABLE_NAME|3|  
|Nome|@Name|CONSTRAINT_NAME|4|  
  
## <a name="sql-server-2008-schema-restrictions"></a>Restrizioni per gli schemi di SQL Server 2008  
 Nelle tabelle seguenti sono incluse le restrizioni per le raccolte di schemi di SQL Server 2008. Queste restrizioni sono valide a partire dalla versione 3.5 SP1 di .NET Framework e da SQL Server 2008. Le restrizioni non sono supportate nelle versioni precedenti di .NET Framework e di SQL Server.  
  
### <a name="columnsetcolumns"></a>ColumnSetColumns  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|TABLE_CATALOG|1|  
|Proprietario|@Owner|TABLE_SCHEMA|2|  
|Tabella|@Table|TABLE_NAME|3|  
  
### <a name="allcolumns"></a>AllColumns  
  
|Nome della restrizione|Nome parametro|Impostazione predefinita della restrizione|Numero della restrizione|  
|----------------------|--------------------|-------------------------|------------------------|  
|Catalogo|@Catalog|TABLE_CATALOG|1|  
|Proprietario|@Owner|TABLE_SCHEMA|2|  
|Tabella|@Table|TABLE_NAME|3|  
|Colonna|@Column|COLUMN_NAME|4|  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](ado-net-overview.md)
