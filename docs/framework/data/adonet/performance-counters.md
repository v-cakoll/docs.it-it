---
title: Contatori delle prestazioni
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b121b71-78f8-4ae2-9aa1-0b2e15778e57
ms.openlocfilehash: 985951180a5c8ee09460b7fe4bf3213b986c3bb6
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980067"
---
# <a name="performance-counters-in-adonet"></a>Contatori di prestazioni in ADO.NET
In ADO.NET 2.0 è stato introdotto il supporto espanso per i contatori delle prestazioni, che include il supporto per <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient>. I contatori delle prestazioni <xref:System.Data.SqlClient> disponibili nelle versioni precedenti di ADO.NET sono stati deprecati e sostituiti con i nuovi contatori delle prestazioni descritti in questo argomento. È possibile usare i contatori delle prestazioni di ADO.NET per monitorare lo stato dell'applicazione e le risorse di connessione che usa. I contatori delle prestazioni possono essere monitorati tramite Performance Monitor di Windows. In alternativa, è possibile accedervi a livello di codice usando la classe <xref:System.Diagnostics.PerformanceCounter> nello spazio dei nomi <xref:System.Diagnostics>.  
  
## <a name="available-performance-counters"></a>Contatori delle prestazioni disponibili  
 Attualmente per <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient> sono disponibili 14 contatori delle prestazioni diversi, come descritto nella tabella seguente. Si noti che i nomi dei singoli contatori non sono localizzati nelle versioni internazionali di Microsoft .NET Framework.  
  
|Contatore delle prestazioni|Descrizione|  
|-------------------------|-----------------|  
|`HardConnectsPerSecond`|Numero di connessioni al secondo eseguite a un server database.|  
|`HardDisconnectsPerSecond`|Numero di disconnessioni al secondo eseguite a un server database.|  
|`NumberOfActiveConnectionPoolGroups`|Numero di gruppi univoci di pool di connessioni attivi. Questo contatore è controllato dal numero di stringhe di connessione univoche disponibili in AppDomain.|  
|`NumberOfActiveConnectionPools`|Numero complessivo di pool di connessioni.|  
|`NumberOfActiveConnections`|Numero di connessioni attive al momento in uso. **Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita. Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).|  
|`NumberOfFreeConnections`|Numero di connessioni disponibili per l'uso nei pool di connessioni. **Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita. Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).|  
|`NumberOfInactiveConnectionPoolGroups`|Numero di gruppi univoci di pool di connessioni attivi contrassegnati per l'eliminazione. Questo contatore è controllato dal numero di stringhe di connessione univoche disponibili in AppDomain.|  
|`NumberOfInactiveConnectionPools`|Numero di pool di connessioni inattivi in cui non si è verificata alcuna attività recente e che sono in attesa di essere eliminati.|  
|`NumberOfNonPooledConnections`|Numero di connessioni attive che non sono in pool.|  
|`NumberOfPooledConnections`|Numero di connessioni attive gestite dall'infrastruttura del pool di connessioni.|  
|`NumberOfReclaimedConnections`|Numero di connessioni che sono state recuperate tramite Garbage Collection laddove per l'applicazione non è stato chiamato `Close` o `Dispose`. La mancata chiusura o eliminazione esplicita delle connessioni influisce negativamente sulle prestazioni.|  
|`NumberOfStasisConnections`|Numero di connessioni attualmente in attesa del completamento di un'azione e che non sono pertanto disponibili per l'uso da parte dell'applicazione.|  
|`SoftConnectsPerSecond`|Numero di connessioni attive rimosse dal pool di connessioni. **Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita. Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).|  
|`SoftDisconnectsPerSecond`|Numero di connessioni attive restituite al pool di connessioni. **Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita. Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).|  
  
### <a name="connection-pool-groups-and-connection-pools"></a>Gruppi e pool di connessioni e pool di connessioni  
 Quando si usa l'autenticazione di Windows (sicurezza integrata), è necessario monitorare i contatori delle prestazioni `NumberOfActiveConnectionPoolGroups` e `NumberOfActiveConnectionPools`. Il motivo è che questi gruppi di pool di connessioni sono mappati a stringhe di connessione univoche. Quando si usa la sicurezza integrata, i pool di connessioni vengono mappati a stringhe di connessione e inoltre creano pool distinti per le singole identità di Windows. Ad esempio, se Fred e Julie, ognuno all'interno dello stesso AppDomain, usano la stessa stringa di connessione `"Data Source=MySqlServer;Integrated Security=true"`, viene creato un gruppo di pool di connessioni per la stringa di connessione e due pool aggiuntivi, uno per Fred e l'altro per Julie. Se Giorgio e Martha usano una stringa di connessione con un account di accesso SQL Server identico `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`, viene creato un solo pool per l'identità **lowPrivUser** .  
  
<a name="ActivatingOffByDefault"></a>   
### <a name="activating-off-by-default-counters"></a>Attivazione di contatori disattivati per impostazione predefinita  
 I contatori delle prestazioni `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond` e `SoftConnectsPerSecond` sono disattivati per impostazione predefinita. Aggiungere le informazioni seguenti al file di configurazione dell'applicazione per abilitarli:  
  
```xml  
<system.diagnostics>  
  <switches>  
    <add name="ConnectionPoolPerformanceCounterDetail"  
         value="4"/>  
  </switches>  
</system.diagnostics>  
```  
  
## <a name="retrieving-performance-counter-values"></a>Recupero di valori dei contatori delle prestazioni  
 Nell'applicazione console seguente viene illustrato come recuperare i valori dei contatori delle prestazioni nell'applicazione. Affinché vengano restituite informazioni per tutti i contatori delle prestazioni di ADO.NET, è necessario che le connessioni siano aperte a attive.  
  
> [!NOTE]
> In questo esempio viene utilizzato il database **AdventureWorks** di esempio incluso in SQL Server. Per le stringhe di connessione indicate nel codice di esempio si presuppone che il database sia installato e disponibile nel computer locale con il nome di istanza SqlExpress e che siano stati creati account di accesso di SQL Server corrispondenti a quelli specificati nelle stringhe di connessione. Può essere necessario abilitare gli account di accesso di SQL Server se il server è stato configurato con le impostazioni di sicurezza predefinite, che consentono solo l'autenticazione di Windows. Apportare le modifiche necessarie alle stringhe di connessione in base all'ambiente.  
  
### <a name="example"></a>Esempio  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System.Data.SqlClient  
Imports System.Diagnostics  
Imports System.Runtime.InteropServices  
  
Class Program  
  
    Private PerfCounters(9) As PerformanceCounter  
    Private connection As SqlConnection = New SqlConnection  
  
    Public Shared Sub Main()  
        Dim prog As Program = New Program  
        ' Open a connection and create the performance counters.   
        prog.connection.ConnectionString = _  
           GetIntegratedSecurityConnectionString()  
        prog.SetUpPerformanceCounters()  
        Console.WriteLine("Available Performance Counters:")  
  
        ' Create the connections and display the results.  
        prog.CreateConnections()  
        Console.WriteLine("Press Enter to finish.")  
        Console.ReadLine()  
    End Sub  
  
    Private Sub CreateConnections()  
        ' List the Performance counters.  
        WritePerformanceCounters()  
  
        ' Create 4 connections and display counter information.  
        Dim connection1 As SqlConnection = New SqlConnection( _  
           GetIntegratedSecurityConnectionString)  
        connection1.Open()  
        Console.WriteLine("Opened the 1st Connection:")  
        WritePerformanceCounters()  
  
        Dim connection2 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionStringDifferent)  
        connection2.Open()  
        Console.WriteLine("Opened the 2nd Connection:")  
        WritePerformanceCounters()  
  
        Console.WriteLine("Opened the 3rd Connection:")  
        Dim connection3 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection3.Open()  
        WritePerformanceCounters()  
  
        Dim connection4 As SqlConnection = New SqlConnection( _  
           GetSqlConnectionString)  
        connection4.Open()  
        Console.WriteLine("Opened the 4th Connection:")  
        WritePerformanceCounters()  
  
        connection1.Close()  
        Console.WriteLine("Closed the 1st Connection:")  
        WritePerformanceCounters()  
  
        connection2.Close()  
        Console.WriteLine("Closed the 2nd Connection:")  
        WritePerformanceCounters()  
  
        connection3.Close()  
        Console.WriteLine("Closed the 3rd Connection:")  
        WritePerformanceCounters()  
  
        connection4.Close()  
        Console.WriteLine("Closed the 4th Connection:")  
        WritePerformanceCounters()  
    End Sub  
  
    Private Enum ADO_Net_Performance_Counters  
        NumberOfActiveConnectionPools  
        NumberOfReclaimedConnections  
        HardConnectsPerSecond  
        HardDisconnectsPerSecond  
        NumberOfActiveConnectionPoolGroups  
        NumberOfInactiveConnectionPoolGroups  
        NumberOfInactiveConnectionPools  
        NumberOfNonPooledConnections  
        NumberOfPooledConnections  
        NumberOfStasisConnections  
        ' The following performance counters are more expensive to track.  
        ' Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        '     SoftConnectsPerSecond  
        '     SoftDisconnectsPerSecond  
        '     NumberOfActiveConnections  
        '     NumberOfFreeConnections  
    End Enum  
  
    Private Sub SetUpPerformanceCounters()  
        connection.Close()  
        Me.PerfCounters(9) = New PerformanceCounter()  
  
        Dim instanceName As String = GetInstanceName()  
        Dim apc As Type = GetType(ADO_Net_Performance_Counters)  
        Dim i As Integer = 0  
        Dim s As String = ""  
        For Each s In [Enum].GetNames(apc)  
            Me.PerfCounters(i) = New PerformanceCounter()  
            Me.PerfCounters(i).CategoryName = ".NET Data Provider for SqlServer"  
            Me.PerfCounters(i).CounterName = s  
            Me.PerfCounters(i).InstanceName = instanceName  
            i = (i + 1)  
        Next  
    End Sub  
  
    Private Declare Function GetCurrentProcessId Lib "kernel32.dll" () As Integer  
  
    Private Function GetInstanceName() As String  
        'This works for Winforms apps.   
        Dim instanceName As String = _  
           System.Reflection.Assembly.GetEntryAssembly.GetName.Name  
  
        ' Must replace special characters like (, ), #, /, \\   
        Dim instanceName2 As String = _  
           AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
           .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        'For ASP.NET applications your instanceName will be your CurrentDomain's   
        'FriendlyName. Replace the line above that sets the instanceName with this:   
        'instanceName = AppDomain.CurrentDomain.FriendlyName.ToString.Replace("(", "[") _  
        '    .Replace(")", "]").Replace("#", "_").Replace("/", "_").Replace("\\", "_")  
  
        Dim pid As String = GetCurrentProcessId.ToString  
        instanceName = (instanceName + ("[" & (pid & "]")))  
        Console.WriteLine("Instance Name: {0}", instanceName)  
        Console.WriteLine("---------------------------")  
        Return instanceName  
    End Function  
  
    Private Sub WritePerformanceCounters()  
        Console.WriteLine("---------------------------")  
        For Each p As PerformanceCounter In Me.PerfCounters  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue)  
        Next  
        Console.WriteLine("---------------------------")  
    End Sub  
  
    Private Shared Function GetIntegratedSecurityConnectionString() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Data Source=.\SqlExpress;Integrated Security=True;" &   
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionString() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" &   
          "Initial Catalog=AdventureWorks")  
    End Function  
  
    Private Shared Function GetSqlConnectionStringDifferent() As String  
        ' To avoid storing the connection string in your code,   
        ' you can retrieve it from a configuration file.   
        Return ("Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" & _  
          "User Id=LowPriv;Password=Data!05;")  
    End Function  
End Class  
```  

```csharp  
using System;  
using System.Data.SqlClient;  
using System.Diagnostics;  
using System.Runtime.InteropServices;  
  
class Program  
{  
    PerformanceCounter[] PerfCounters = new PerformanceCounter[10];  
    SqlConnection connection = new SqlConnection();  
  
    static void Main()  
    {  
        Program prog = new Program();  
        // Open a connection and create the performance counters.  
        prog.connection.ConnectionString =  
           GetIntegratedSecurityConnectionString();  
        prog.SetUpPerformanceCounters();  
        Console.WriteLine("Available Performance Counters:");  
  
        // Create the connections and display the results.  
        prog.CreateConnections();  
        Console.WriteLine("Press Enter to finish.");  
        Console.ReadLine();  
    }  
  
    private void CreateConnections()  
    {  
        // List the Performance counters.  
        WritePerformanceCounters();  
  
        // Create 4 connections and display counter information.  
        SqlConnection connection1 = new SqlConnection(  
              GetIntegratedSecurityConnectionString());  
        connection1.Open();  
        Console.WriteLine("Opened the 1st Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection2 = new SqlConnection(  
              GetSqlConnectionStringDifferent());  
        connection2.Open();  
        Console.WriteLine("Opened the 2nd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection3 = new SqlConnection(  
              GetSqlConnectionString());  
        connection3.Open();  
        Console.WriteLine("Opened the 3rd Connection:");  
        WritePerformanceCounters();  
  
        SqlConnection connection4 = new SqlConnection(  
              GetSqlConnectionString());  
        connection4.Open();  
        Console.WriteLine("Opened the 4th Connection:");  
        WritePerformanceCounters();  
  
        connection1.Close();  
        Console.WriteLine("Closed the 1st Connection:");  
        WritePerformanceCounters();  
  
        connection2.Close();  
        Console.WriteLine("Closed the 2nd Connection:");  
        WritePerformanceCounters();  
  
        connection3.Close();  
        Console.WriteLine("Closed the 3rd Connection:");  
        WritePerformanceCounters();  
  
        connection4.Close();  
        Console.WriteLine("Closed the 4th Connection:");  
        WritePerformanceCounters();  
    }  
  
    private enum ADO_Net_Performance_Counters  
    {  
        NumberOfActiveConnectionPools,  
        NumberOfReclaimedConnections,  
        HardConnectsPerSecond,  
        HardDisconnectsPerSecond,  
        NumberOfActiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPoolGroups,  
        NumberOfInactiveConnectionPools,  
        NumberOfNonPooledConnections,  
        NumberOfPooledConnections,  
        NumberOfStasisConnections  
        // The following performance counters are more expensive to track.  
        // Enable ConnectionPoolPerformanceCounterDetail in your config file.  
        //     SoftConnectsPerSecond  
        //     SoftDisconnectsPerSecond  
        //     NumberOfActiveConnections  
        //     NumberOfFreeConnections  
    }  
  
    private void SetUpPerformanceCounters()  
    {  
        connection.Close();  
        this.PerfCounters = new PerformanceCounter[10];  
        string instanceName = GetInstanceName();  
        Type apc = typeof(ADO_Net_Performance_Counters);  
        int i = 0;  
        foreach (string s in Enum.GetNames(apc))  
        {  
            this.PerfCounters[i] = new PerformanceCounter();  
            this.PerfCounters[i].CategoryName = ".NET Data Provider for SqlServer";  
            this.PerfCounters[i].CounterName = s;  
            this.PerfCounters[i].InstanceName = instanceName;  
            i++;  
        }  
    }  
  
    [DllImport("kernel32.dll", SetLastError = true)]  
    static extern int GetCurrentProcessId();  
  
    private string GetInstanceName()  
    {  
        //This works for Winforms apps.  
        string instanceName =  
            System.Reflection.Assembly.GetEntryAssembly().GetName().Name;  
  
        // Must replace special characters like (, ), #, /, \\  
        string instanceName2 =  
            AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(', '[')  
            .Replace(')', ']').Replace('#', '_').Replace('/', '_').Replace('\\', '_');  
  
        // For ASP.NET applications your instanceName will be your CurrentDomain's   
        // FriendlyName. Replace the line above that sets the instanceName with this:  
        // instanceName = AppDomain.CurrentDomain.FriendlyName.ToString().Replace('(','[')  
        // .Replace(')',']').Replace('#','_').Replace('/','_').Replace('\\','_');  
  
        string pid = GetCurrentProcessId().ToString();  
        instanceName = instanceName + "[" + pid + "]";  
        Console.WriteLine("Instance Name: {0}", instanceName);  
        Console.WriteLine("---------------------------");  
        return instanceName;  
    }  
  
    private void WritePerformanceCounters()  
    {  
        Console.WriteLine("---------------------------");  
        foreach (PerformanceCounter p in this.PerfCounters)  
        {  
            Console.WriteLine("{0} = {1}", p.CounterName, p.NextValue());  
        }  
        Console.WriteLine("---------------------------");  
    }  
  
    private static string GetIntegratedSecurityConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;Integrated Security=True;" +  
          "Initial Catalog=AdventureWorks";  
    }  
    private static string GetSqlConnectionString()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Data Source=.\SqlExpress;User Id=LowPriv;Password=Data!05;" +  
          "Initial Catalog=AdventureWorks";  
    }  
  
    private static string GetSqlConnectionStringDifferent()  
    {  
        // To avoid storing the connection string in your code,  
        // you can retrieve it from a configuration file.  
        return @"Initial Catalog=AdventureWorks;Data Source=.\SqlExpress;" +  
          "User Id=LowPriv;Password=Data!05;";  
    }  
}  
```  

## <a name="see-also"></a>Vedere anche

- [Connessione a un'origine dati](connecting-to-a-data-source.md)
- [Pool di connessioni OLE DB, ODBC e Oracle](ole-db-odbc-and-oracle-connection-pooling.md)
- [Contatori delle prestazioni per ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/fxk122b4(v=vs.100))
- [Runtime Profiling](../../debug-trace-profile/runtime-profiling.md) (Profilatura di runtime)
- [Introduzione al monitoraggio delle soglie di prestazioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))
- [Panoramica di ADO.NET](ado-net-overview.md)
