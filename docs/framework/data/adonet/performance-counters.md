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
# <a name="performance-counters-in-adonet"></a><span data-ttu-id="b5393-102">Contatori di prestazioni in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b5393-102">Performance Counters in ADO.NET</span></span>
<span data-ttu-id="b5393-103">In ADO.NET 2.0 è stato introdotto il supporto espanso per i contatori delle prestazioni, che include il supporto per <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient>.</span><span class="sxs-lookup"><span data-stu-id="b5393-103">ADO.NET 2.0 introduced expanded support for performance counters that includes support for both <xref:System.Data.SqlClient> and <xref:System.Data.OracleClient>.</span></span> <span data-ttu-id="b5393-104">I contatori delle prestazioni <xref:System.Data.SqlClient> disponibili nelle versioni precedenti di ADO.NET sono stati deprecati e sostituiti con i nuovi contatori delle prestazioni descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="b5393-104">The <xref:System.Data.SqlClient> performance counters available in previous versions of ADO.NET have been deprecated and replaced with the new performance counters discussed in this topic.</span></span> <span data-ttu-id="b5393-105">È possibile usare i contatori delle prestazioni di ADO.NET per monitorare lo stato dell'applicazione e le risorse di connessione che usa.</span><span class="sxs-lookup"><span data-stu-id="b5393-105">You can use ADO.NET performance counters to monitor the status of your application and the connection resources that it uses.</span></span> <span data-ttu-id="b5393-106">I contatori delle prestazioni possono essere monitorati tramite Performance Monitor di Windows. In alternativa, è possibile accedervi a livello di codice usando la classe <xref:System.Diagnostics.PerformanceCounter> nello spazio dei nomi <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="b5393-106">Performance counters can be monitored by using Windows Performance Monitor or can be accessed programmatically using the <xref:System.Diagnostics.PerformanceCounter> class in the <xref:System.Diagnostics> namespace.</span></span>  
  
## <a name="available-performance-counters"></a><span data-ttu-id="b5393-107">Contatori delle prestazioni disponibili</span><span class="sxs-lookup"><span data-stu-id="b5393-107">Available Performance Counters</span></span>  
 <span data-ttu-id="b5393-108">Attualmente per <xref:System.Data.SqlClient> e <xref:System.Data.OracleClient> sono disponibili 14 contatori delle prestazioni diversi, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b5393-108">Currently there are 14 different performance counters available for <xref:System.Data.SqlClient> and <xref:System.Data.OracleClient> as described in the following table.</span></span> <span data-ttu-id="b5393-109">Si noti che i nomi dei singoli contatori non sono localizzati nelle versioni internazionali di Microsoft .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5393-109">Note that the names for the individual counters are not localized across regional versions of the Microsoft .NET Framework.</span></span>  
  
|<span data-ttu-id="b5393-110">Contatore delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="b5393-110">Performance counter</span></span>|<span data-ttu-id="b5393-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b5393-111">Description</span></span>|  
|-------------------------|-----------------|  
|`HardConnectsPerSecond`|<span data-ttu-id="b5393-112">Numero di connessioni al secondo eseguite a un server database.</span><span class="sxs-lookup"><span data-stu-id="b5393-112">The number of connections per second that are being made to a database server.</span></span>|  
|`HardDisconnectsPerSecond`|<span data-ttu-id="b5393-113">Numero di disconnessioni al secondo eseguite a un server database.</span><span class="sxs-lookup"><span data-stu-id="b5393-113">The number of disconnects per second that are being made to a database server.</span></span>|  
|`NumberOfActiveConnectionPoolGroups`|<span data-ttu-id="b5393-114">Numero di gruppi univoci di pool di connessioni attivi.</span><span class="sxs-lookup"><span data-stu-id="b5393-114">The number of unique connection pool groups that are active.</span></span> <span data-ttu-id="b5393-115">Questo contatore è controllato dal numero di stringhe di connessione univoche disponibili in AppDomain.</span><span class="sxs-lookup"><span data-stu-id="b5393-115">This counter is controlled by the number of unique connection strings that are found in the AppDomain.</span></span>|  
|`NumberOfActiveConnectionPools`|<span data-ttu-id="b5393-116">Numero complessivo di pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="b5393-116">The total number of connection pools.</span></span>|  
|`NumberOfActiveConnections`|<span data-ttu-id="b5393-117">Numero di connessioni attive al momento in uso.</span><span class="sxs-lookup"><span data-stu-id="b5393-117">The number of active connections that are currently in use.</span></span> <span data-ttu-id="b5393-118">**Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5393-118">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="b5393-119">Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).</span><span class="sxs-lookup"><span data-stu-id="b5393-119">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`NumberOfFreeConnections`|<span data-ttu-id="b5393-120">Numero di connessioni disponibili per l'uso nei pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="b5393-120">The number of connections available for use in the connection pools.</span></span> <span data-ttu-id="b5393-121">**Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5393-121">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="b5393-122">Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).</span><span class="sxs-lookup"><span data-stu-id="b5393-122">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`NumberOfInactiveConnectionPoolGroups`|<span data-ttu-id="b5393-123">Numero di gruppi univoci di pool di connessioni attivi contrassegnati per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="b5393-123">The number of unique connection pool groups that are marked for pruning.</span></span> <span data-ttu-id="b5393-124">Questo contatore è controllato dal numero di stringhe di connessione univoche disponibili in AppDomain.</span><span class="sxs-lookup"><span data-stu-id="b5393-124">This counter is controlled by the number of unique connection strings that are found in the AppDomain.</span></span>|  
|`NumberOfInactiveConnectionPools`|<span data-ttu-id="b5393-125">Numero di pool di connessioni inattivi in cui non si è verificata alcuna attività recente e che sono in attesa di essere eliminati.</span><span class="sxs-lookup"><span data-stu-id="b5393-125">The number of inactive connection pools that have not had any recent activity and are waiting to be disposed.</span></span>|  
|`NumberOfNonPooledConnections`|<span data-ttu-id="b5393-126">Numero di connessioni attive che non sono in pool.</span><span class="sxs-lookup"><span data-stu-id="b5393-126">The number of active connections that are not pooled.</span></span>|  
|`NumberOfPooledConnections`|<span data-ttu-id="b5393-127">Numero di connessioni attive gestite dall'infrastruttura del pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="b5393-127">The number of active connections that are being managed by the connection pooling infrastructure.</span></span>|  
|`NumberOfReclaimedConnections`|<span data-ttu-id="b5393-128">Numero di connessioni che sono state recuperate tramite Garbage Collection laddove per l'applicazione non è stato chiamato `Close` o `Dispose`.</span><span class="sxs-lookup"><span data-stu-id="b5393-128">The number of connections that have been reclaimed through garbage collection where `Close` or `Dispose` was not called by the application.</span></span> <span data-ttu-id="b5393-129">La mancata chiusura o eliminazione esplicita delle connessioni influisce negativamente sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b5393-129">Not explicitly closing or disposing connections hurts performance.</span></span>|  
|`NumberOfStasisConnections`|<span data-ttu-id="b5393-130">Numero di connessioni attualmente in attesa del completamento di un'azione e che non sono pertanto disponibili per l'uso da parte dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5393-130">The number of connections currently awaiting completion of an action and which are therefore unavailable for use by your application.</span></span>|  
|`SoftConnectsPerSecond`|<span data-ttu-id="b5393-131">Numero di connessioni attive rimosse dal pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="b5393-131">The number of active connections being pulled from the connection pool.</span></span> <span data-ttu-id="b5393-132">**Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5393-132">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="b5393-133">Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).</span><span class="sxs-lookup"><span data-stu-id="b5393-133">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
|`SoftDisconnectsPerSecond`|<span data-ttu-id="b5393-134">Numero di connessioni attive restituite al pool di connessioni.</span><span class="sxs-lookup"><span data-stu-id="b5393-134">The number of active connections that are being returned to the connection pool.</span></span> <span data-ttu-id="b5393-135">**Nota:**  Questo contatore delle prestazioni non è abilitato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5393-135">**Note:**  This performance counter is not enabled by default.</span></span> <span data-ttu-id="b5393-136">Per abilitare questo contatore delle prestazioni, vedere [attivazione di contatori disattivati per impostazione predefinita](#ActivatingOffByDefault).</span><span class="sxs-lookup"><span data-stu-id="b5393-136">To enable this performance counter, see [Activating Off-By-Default Counters](#ActivatingOffByDefault).</span></span>|  
  
### <a name="connection-pool-groups-and-connection-pools"></a><span data-ttu-id="b5393-137">Gruppi e pool di connessioni e pool di connessioni</span><span class="sxs-lookup"><span data-stu-id="b5393-137">Connection Pool Groups and Connection Pools</span></span>  
 <span data-ttu-id="b5393-138">Quando si usa l'autenticazione di Windows (sicurezza integrata), è necessario monitorare i contatori delle prestazioni `NumberOfActiveConnectionPoolGroups` e `NumberOfActiveConnectionPools`.</span><span class="sxs-lookup"><span data-stu-id="b5393-138">When using Windows Authentication (integrated security), you must monitor both the `NumberOfActiveConnectionPoolGroups` and `NumberOfActiveConnectionPools` performance counters.</span></span> <span data-ttu-id="b5393-139">Il motivo è che questi gruppi di pool di connessioni sono mappati a stringhe di connessione univoche.</span><span class="sxs-lookup"><span data-stu-id="b5393-139">The reason is that connection pool groups map to unique connection strings.</span></span> <span data-ttu-id="b5393-140">Quando si usa la sicurezza integrata, i pool di connessioni vengono mappati a stringhe di connessione e inoltre creano pool distinti per le singole identità di Windows.</span><span class="sxs-lookup"><span data-stu-id="b5393-140">When integrated security is used, connection pools map to connection strings and additionally create separate pools for individual Windows identities.</span></span> <span data-ttu-id="b5393-141">Ad esempio, se Fred e Julie, ognuno all'interno dello stesso AppDomain, usano la stessa stringa di connessione `"Data Source=MySqlServer;Integrated Security=true"`, viene creato un gruppo di pool di connessioni per la stringa di connessione e due pool aggiuntivi, uno per Fred e l'altro per Julie.</span><span class="sxs-lookup"><span data-stu-id="b5393-141">For example, if Fred and Julie, each within the same AppDomain, both use the connection string `"Data Source=MySqlServer;Integrated Security=true"`, a connection pool group is created for the connection string, and two additional pools are created, one for Fred and one for Julie.</span></span> <span data-ttu-id="b5393-142">Se Giorgio e Martha usano una stringa di connessione con un account di accesso SQL Server identico `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`, viene creato un solo pool per l'identità **lowPrivUser** .</span><span class="sxs-lookup"><span data-stu-id="b5393-142">If John and Martha use a connection string with an identical SQL Server login, `"Data Source=MySqlServer;User Id=lowPrivUser;Password=Strong?Password"`, then only a single pool is created for the **lowPrivUser** identity.</span></span>  
  
<a name="ActivatingOffByDefault"></a>   
### <a name="activating-off-by-default-counters"></a><span data-ttu-id="b5393-143">Attivazione di contatori disattivati per impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="b5393-143">Activating Off-By-Default Counters</span></span>  
 <span data-ttu-id="b5393-144">I contatori delle prestazioni `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond` e `SoftConnectsPerSecond` sono disattivati per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b5393-144">The performance counters `NumberOfFreeConnections`, `NumberOfActiveConnections`, `SoftDisconnectsPerSecond`, and `SoftConnectsPerSecond` are off by default.</span></span> <span data-ttu-id="b5393-145">Aggiungere le informazioni seguenti al file di configurazione dell'applicazione per abilitarli:</span><span class="sxs-lookup"><span data-stu-id="b5393-145">Add the following information to the application's configuration file to enable them:</span></span>  
  
```xml  
<system.diagnostics>  
  <switches>  
    <add name="ConnectionPoolPerformanceCounterDetail"  
         value="4"/>  
  </switches>  
</system.diagnostics>  
```  
  
## <a name="retrieving-performance-counter-values"></a><span data-ttu-id="b5393-146">Recupero di valori dei contatori delle prestazioni</span><span class="sxs-lookup"><span data-stu-id="b5393-146">Retrieving Performance Counter Values</span></span>  
 <span data-ttu-id="b5393-147">Nell'applicazione console seguente viene illustrato come recuperare i valori dei contatori delle prestazioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b5393-147">The following console application shows how to retrieve performance counter values in your application.</span></span> <span data-ttu-id="b5393-148">Affinché vengano restituite informazioni per tutti i contatori delle prestazioni di ADO.NET, è necessario che le connessioni siano aperte a attive.</span><span class="sxs-lookup"><span data-stu-id="b5393-148">Connections must be open and active for information to be returned for all of the ADO.NET performance counters.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b5393-149">In questo esempio viene utilizzato il database **AdventureWorks** di esempio incluso in SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5393-149">This example uses the sample **AdventureWorks** database included with SQL Server.</span></span> <span data-ttu-id="b5393-150">Per le stringhe di connessione indicate nel codice di esempio si presuppone che il database sia installato e disponibile nel computer locale con il nome di istanza SqlExpress e che siano stati creati account di accesso di SQL Server corrispondenti a quelli specificati nelle stringhe di connessione.</span><span class="sxs-lookup"><span data-stu-id="b5393-150">The connection strings provided in the sample code assume that the database is installed and available on the local computer with an instance name of SqlExpress, and that you have created SQL Server logins that match those supplied in the connection strings.</span></span> <span data-ttu-id="b5393-151">Può essere necessario abilitare gli account di accesso di SQL Server se il server è stato configurato con le impostazioni di sicurezza predefinite, che consentono solo l'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="b5393-151">You may need to enable SQL Server logins if your server is configured using the default security settings which allow only Windows Authentication.</span></span> <span data-ttu-id="b5393-152">Apportare le modifiche necessarie alle stringhe di connessione in base all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="b5393-152">Modify the connection strings as necessary to suit your environment.</span></span>  
  
### <a name="example"></a><span data-ttu-id="b5393-153">Esempio</span><span class="sxs-lookup"><span data-stu-id="b5393-153">Example</span></span>  
  
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

## <a name="see-also"></a><span data-ttu-id="b5393-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5393-154">See also</span></span>

- [<span data-ttu-id="b5393-155">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="b5393-155">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="b5393-156">Pool di connessioni OLE DB, ODBC e Oracle</span><span class="sxs-lookup"><span data-stu-id="b5393-156">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)
- <span data-ttu-id="b5393-157">[Contatori delle prestazioni per ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/fxk122b4(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b5393-157">[Performance Counters for ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/fxk122b4(v=vs.100))</span></span>
- <span data-ttu-id="b5393-158">[Runtime Profiling](../../debug-trace-profile/runtime-profiling.md) (Profilatura di runtime)</span><span class="sxs-lookup"><span data-stu-id="b5393-158">[Runtime Profiling](../../debug-trace-profile/runtime-profiling.md)</span></span>
- <span data-ttu-id="b5393-159">[Introduzione al monitoraggio delle soglie di prestazioni](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b5393-159">[Introduction to Monitoring Performance Thresholds](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bd20x32d(v=vs.90))</span></span>
- [<span data-ttu-id="b5393-160">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b5393-160">ADO.NET Overview</span></span>](ado-net-overview.md)
