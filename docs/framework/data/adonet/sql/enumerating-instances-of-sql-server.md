---
title: Enumerazione di istanze di SQL Server
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: c59db5869ed848071611cdbf985b45dc59790d69
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979989"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a>Enumerazione di istanze di SQL Server (ADO.NET)
SQL Server consente alle applicazioni di trovare SQL Server istanze all'interno della rete corrente. Mediante la classe <xref:System.Data.Sql.SqlDataSourceEnumerator> queste informazioni vengono esposte allo sviluppatore dell'applicazione che in tal modo dispone di una <xref:System.Data.DataTable> contenente dati relativi a tutti i server visibili. Questa tabella restituita contiene un elenco di istanze del server disponibili nella rete che corrisponde all'elenco fornito quando un utente tenta di creare una nuova connessione ed espande l'elenco a discesa contenente tutti i server disponibili nella finestra di dialogo **Proprietà connessione** . I risultati visualizzati non sono sempre completi.  
  
> [!NOTE]
> Come nel caso della maggior parte dei servizi Windows, è consigliabile eseguire il servizio Visualizzatore SQL con meno privilegi possibile. Per ulteriori informazioni sul servizio Visualizzatore SQL e su come gestirne il comportamento, vedere la documentazione online di SQL Server.  
  
## <a name="retrieving-an-enumerator-instance"></a>Recupero di un'istanza di enumeratore  
 Per recuperare la tabella che contiene le informazioni sulle istanze di SQL Server disponibili, è innanzitutto necessario recuperare un enumeratore utilizzando la proprietà condivisa/statica <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>:  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 Dopo aver recuperato l'istanza statica, è possibile chiamare il metodo <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>, che restituisce un tipo <xref:System.Data.DataTable> contenente informazioni sui server disponibili:  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 La tabella restituita dalla chiamata al metodo contiene le seguenti colonne, tutte contenenti valori `string`:  
  
|Colonna|Descrizione|  
|------------|-----------------|  
|**ServerName**|Nome del server.|  
|**InstanceName**|Nome dell'istanza del server. Resta vuoto se il server è in esecuzione come istanza predefinita.|  
|**IsClustered**|Indica se il server è parte di un cluster.|  
|**Version**|Versione del server. Ad esempio:<br /><br /> -9.00. x (SQL Server 2005)<br />-10.0. XX (SQL Server 2008)<br />-10.50. x (SQL Server 2008 R2)<br />-11.0. XX (SQL Server 2012)|  
  
## <a name="enumeration-limitations"></a>Limitazioni delle enumerazioni  
 È possibile elencare o non elencare tutti i server disponibili. L'elenco può variare in base a fattori come i timeout e il traffico di rete. Pertanto l'elenco può risultare diverso durante due chiamate consecutive. Verranno elencati solo i server nella stessa rete. Normalmente i pacchetti di broadcast non passeranno dai router. Per questo motivo è possibile che l'utente non visualizzi un server elencato, ma tale server resterà stabile durante le chiamate.  
  
 Per i server elencati potrebbero essere disponibili anche informazioni aggiuntive quali `IsClustered` e la versione, a seconda del metodo con cui si è ottenuto l'elenco. I server elencati tramite il servizio Visualizzatore di SQL Server presenteranno maggiori dettagli rispetto a quelli rilevati tramite l'infrastruttura Windows, che consente di elencare solo i nomi.  
  
> [!NOTE]
> L'enumerazione di server è disponibile solo in caso di attendibilità totale. Gli assembly eseguiti in un ambiente di attendibilità parziale non saranno in grado di usare la funzionalità, anche se dispongono dell'autorizzazione CAS (Code Access Security, Sicurezza dall'accesso di codice) <xref:System.Data.SqlClient.SqlClientPermission>.  
  
 SQL Server fornisce informazioni per la <xref:System.Data.Sql.SqlDataSourceEnumerator> mediante l'utilizzo di un servizio Windows esterno denominato SQL Browser. Questo servizio è abilitato per impostazione predefinita, ma gli amministratori possono disattivarlo o disabilitarlo per rendere l'istanza del server invisibile a questa classe.  
  
## <a name="example"></a>Esempio  
 L'applicazione console riportata di seguito consente di recuperare informazioni su tutte le istanze di SQL Server visibili e di visualizzarle nella finestra della console.  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
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
  
## <a name="see-also"></a>Vedere anche

- [SQL Server e ADO.NET](index.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
