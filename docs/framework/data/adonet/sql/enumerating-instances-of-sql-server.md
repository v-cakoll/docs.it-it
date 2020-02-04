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
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="b228c-102">Enumerazione di istanze di SQL Server (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="b228c-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
<span data-ttu-id="b228c-103">SQL Server consente alle applicazioni di trovare SQL Server istanze all'interno della rete corrente.</span><span class="sxs-lookup"><span data-stu-id="b228c-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="b228c-104">Mediante la classe <xref:System.Data.Sql.SqlDataSourceEnumerator> queste informazioni vengono esposte allo sviluppatore dell'applicazione che in tal modo dispone di una <xref:System.Data.DataTable> contenente dati relativi a tutti i server visibili.</span><span class="sxs-lookup"><span data-stu-id="b228c-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="b228c-105">Questa tabella restituita contiene un elenco di istanze del server disponibili nella rete che corrisponde all'elenco fornito quando un utente tenta di creare una nuova connessione ed espande l'elenco a discesa contenente tutti i server disponibili nella finestra di dialogo **Proprietà connessione** .</span><span class="sxs-lookup"><span data-stu-id="b228c-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="b228c-106">I risultati visualizzati non sono sempre completi.</span><span class="sxs-lookup"><span data-stu-id="b228c-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b228c-107">Come nel caso della maggior parte dei servizi Windows, è consigliabile eseguire il servizio Visualizzatore SQL con meno privilegi possibile.</span><span class="sxs-lookup"><span data-stu-id="b228c-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="b228c-108">Per ulteriori informazioni sul servizio Visualizzatore SQL e su come gestirne il comportamento, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b228c-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="b228c-109">Recupero di un'istanza di enumeratore</span><span class="sxs-lookup"><span data-stu-id="b228c-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="b228c-110">Per recuperare la tabella che contiene le informazioni sulle istanze di SQL Server disponibili, è innanzitutto necessario recuperare un enumeratore utilizzando la proprietà condivisa/statica <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>:</span><span class="sxs-lookup"><span data-stu-id="b228c-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="b228c-111">Dopo aver recuperato l'istanza statica, è possibile chiamare il metodo <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>, che restituisce un tipo <xref:System.Data.DataTable> contenente informazioni sui server disponibili:</span><span class="sxs-lookup"><span data-stu-id="b228c-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="b228c-112">La tabella restituita dalla chiamata al metodo contiene le seguenti colonne, tutte contenenti valori `string`:</span><span class="sxs-lookup"><span data-stu-id="b228c-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="b228c-113">Colonna</span><span class="sxs-lookup"><span data-stu-id="b228c-113">Column</span></span>|<span data-ttu-id="b228c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b228c-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b228c-115">**ServerName**</span><span class="sxs-lookup"><span data-stu-id="b228c-115">**ServerName**</span></span>|<span data-ttu-id="b228c-116">Nome del server.</span><span class="sxs-lookup"><span data-stu-id="b228c-116">Name of the server.</span></span>|  
|<span data-ttu-id="b228c-117">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="b228c-117">**InstanceName**</span></span>|<span data-ttu-id="b228c-118">Nome dell'istanza del server.</span><span class="sxs-lookup"><span data-stu-id="b228c-118">Name of the server instance.</span></span> <span data-ttu-id="b228c-119">Resta vuoto se il server è in esecuzione come istanza predefinita.</span><span class="sxs-lookup"><span data-stu-id="b228c-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="b228c-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="b228c-120">**IsClustered**</span></span>|<span data-ttu-id="b228c-121">Indica se il server è parte di un cluster.</span><span class="sxs-lookup"><span data-stu-id="b228c-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="b228c-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="b228c-122">**Version**</span></span>|<span data-ttu-id="b228c-123">Versione del server.</span><span class="sxs-lookup"><span data-stu-id="b228c-123">Version of the server.</span></span> <span data-ttu-id="b228c-124">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b228c-124">For example:</span></span><br /><br /> <span data-ttu-id="b228c-125">-9.00. x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="b228c-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="b228c-126">-10.0. XX (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="b228c-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="b228c-127">-10.50. x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="b228c-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="b228c-128">-11.0. XX (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="b228c-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="b228c-129">Limitazioni delle enumerazioni</span><span class="sxs-lookup"><span data-stu-id="b228c-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="b228c-130">È possibile elencare o non elencare tutti i server disponibili.</span><span class="sxs-lookup"><span data-stu-id="b228c-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="b228c-131">L'elenco può variare in base a fattori come i timeout e il traffico di rete.</span><span class="sxs-lookup"><span data-stu-id="b228c-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="b228c-132">Pertanto l'elenco può risultare diverso durante due chiamate consecutive.</span><span class="sxs-lookup"><span data-stu-id="b228c-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="b228c-133">Verranno elencati solo i server nella stessa rete.</span><span class="sxs-lookup"><span data-stu-id="b228c-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="b228c-134">Normalmente i pacchetti di broadcast non passeranno dai router. Per questo motivo è possibile che l'utente non visualizzi un server elencato, ma tale server resterà stabile durante le chiamate.</span><span class="sxs-lookup"><span data-stu-id="b228c-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="b228c-135">Per i server elencati potrebbero essere disponibili anche informazioni aggiuntive quali `IsClustered` e la versione,</span><span class="sxs-lookup"><span data-stu-id="b228c-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="b228c-136">a seconda del metodo con cui si è ottenuto l'elenco.</span><span class="sxs-lookup"><span data-stu-id="b228c-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="b228c-137">I server elencati tramite il servizio Visualizzatore di SQL Server presenteranno maggiori dettagli rispetto a quelli rilevati tramite l'infrastruttura Windows, che consente di elencare solo i nomi.</span><span class="sxs-lookup"><span data-stu-id="b228c-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b228c-138">L'enumerazione di server è disponibile solo in caso di attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="b228c-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="b228c-139">Gli assembly eseguiti in un ambiente di attendibilità parziale non saranno in grado di usare la funzionalità, anche se dispongono dell'autorizzazione CAS (Code Access Security, Sicurezza dall'accesso di codice) <xref:System.Data.SqlClient.SqlClientPermission>.</span><span class="sxs-lookup"><span data-stu-id="b228c-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="b228c-140">SQL Server fornisce informazioni per la <xref:System.Data.Sql.SqlDataSourceEnumerator> mediante l'utilizzo di un servizio Windows esterno denominato SQL Browser.</span><span class="sxs-lookup"><span data-stu-id="b228c-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="b228c-141">Questo servizio è abilitato per impostazione predefinita, ma gli amministratori possono disattivarlo o disabilitarlo per rendere l'istanza del server invisibile a questa classe.</span><span class="sxs-lookup"><span data-stu-id="b228c-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b228c-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="b228c-142">Example</span></span>  
 <span data-ttu-id="b228c-143">L'applicazione console riportata di seguito consente di recuperare informazioni su tutte le istanze di SQL Server visibili e di visualizzarle nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="b228c-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b228c-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b228c-144">See also</span></span>

- [<span data-ttu-id="b228c-145">SQL Server e ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b228c-145">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="b228c-146">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b228c-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
