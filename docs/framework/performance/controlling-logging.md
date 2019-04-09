---
title: Controllo della registrazione di .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3846e9e00158efbd4828053411b604dafc56e27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59091330"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="5baff-102">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="5baff-102">Controlling .NET Framework Logging</span></span>
<span data-ttu-id="5baff-103">È possibile utilizzare Traccia eventi per Windows (ETW) per registrare eventi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="5baff-103">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="5baff-104">Tramite i seguenti strumenti si possono creare e visualizzare tracce:</span><span class="sxs-lookup"><span data-stu-id="5baff-104">You can create and view traces by using the following tools:</span></span>  
  
-   <span data-ttu-id="5baff-105">Gli strumenti da riga di comando [Logman](/windows-server/administration/windows-commands/logman) e [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1), inclusi nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="5baff-105">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>  
  
-   <span data-ttu-id="5baff-106">Gli strumenti [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) in [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span><span class="sxs-lookup"><span data-stu-id="5baff-106">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="5baff-107">Per altre informazioni su Xperf, vedere il [blog sulle prestazioni di Windows](https://go.microsoft.com/fwlink/?LinkId=179509).</span><span class="sxs-lookup"><span data-stu-id="5baff-107">For more information about Xperf, see the [Windows Performance blog](https://go.microsoft.com/fwlink/?LinkId=179509).</span></span>  
  
 <span data-ttu-id="5baff-108">Per acquisire informazioni sugli eventi CLR, è necessario installare il provider CLR nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="5baff-108">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="5baff-109">Per confermare la corretta installazione del provider, digitare `logman query providers` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="5baff-109">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="5baff-110">Verrà visualizzato un elenco di provider.</span><span class="sxs-lookup"><span data-stu-id="5baff-110">A list of providers is displayed.</span></span> <span data-ttu-id="5baff-111">L'elenco deve contenere una voce relativa al provider CLR, come riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="5baff-111">This list should contain an entry for the CLR provider, as follows.</span></span>  
  
```  
Provider                                 GUID  
-------------------------------------------------------------------------------  
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.  
```  
  
 <span data-ttu-id="5baff-112">Se il provider CLR non compare nell'elenco, è possibile installarlo in Windows Vista e nei sistemi operativi successivi tramite lo strumento da riga di comando [Wevtutil](/windows-server/administration/windows-commands/wevtutil) di Windows.</span><span class="sxs-lookup"><span data-stu-id="5baff-112">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="5baff-113">Aprire la finestra del prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="5baff-113">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="5baff-114">Impostare la directory del prompt sulla cartella di [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<versione .NET>\ ).</span><span class="sxs-lookup"><span data-stu-id="5baff-114">Change the prompt directory to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="5baff-115">Questa cartella contiene il file CLR-ETW.man.</span><span class="sxs-lookup"><span data-stu-id="5baff-115">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="5baff-116">Al prompt dei comandi digitare il comando seguente per installare il provider CLR:</span><span class="sxs-lookup"><span data-stu-id="5baff-116">At the command prompt, type the following command to install the CLR provider:</span></span>  
  
 `wevtutil im CLR-ETW.man`  
  
## <a name="capturing-clr-etw-events"></a><span data-ttu-id="5baff-117">Acquisizione di eventi ETW CLR</span><span class="sxs-lookup"><span data-stu-id="5baff-117">Capturing CLR ETW Events</span></span>  
 <span data-ttu-id="5baff-118">È possibile usare gli strumenti da riga di comando [Logman](/windows-server/administration/windows-commands/logman) e [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) per acquisire gli eventi ETW e gli strumenti [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) e [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) per decodificare gli eventi di traccia.</span><span class="sxs-lookup"><span data-stu-id="5baff-118">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>  
  
 <span data-ttu-id="5baff-119">Per attivare la registrazione, un utente deve specificare tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="5baff-119">To turn on logging, a user must specify three things:</span></span>  
  
-   <span data-ttu-id="5baff-120">Il provider a cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="5baff-120">The provider to communicate to.</span></span>  
  
-   <span data-ttu-id="5baff-121">Un numero a 64 bit che rappresenta un set di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="5baff-121">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="5baff-122">Ogni parola chiave rappresenta un set di eventi che il provider può attivare.</span><span class="sxs-lookup"><span data-stu-id="5baff-122">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="5baff-123">Il numero rappresenta un set combinato di parole chiave da attivare.</span><span class="sxs-lookup"><span data-stu-id="5baff-123">The number represents a combined set of keywords to turn on.</span></span>  
  
-   <span data-ttu-id="5baff-124">Un numero piccolo che rappresenta il livello (livello di dettaglio) a cui registrare.</span><span class="sxs-lookup"><span data-stu-id="5baff-124">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="5baff-125">Il livello 1 è il livello di dettaglio minore e il livello 5 è il livello dettaglio maggiore.</span><span class="sxs-lookup"><span data-stu-id="5baff-125">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="5baff-126">Il livello 0 è un'impostazione predefinita il cui significato è specifico del provider.</span><span class="sxs-lookup"><span data-stu-id="5baff-126">Level 0 is a default whose meaning is provider-specific.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="5baff-127">Per acquisire eventi ETW CLR tramite Logman</span><span class="sxs-lookup"><span data-stu-id="5baff-127">To capture CLR ETW events using Logman</span></span>  
  
1.  <span data-ttu-id="5baff-128">Al prompt dei comandi, digitare:</span><span class="sxs-lookup"><span data-stu-id="5baff-128">At the command prompt, type:</span></span>  
  
     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`  
  
     <span data-ttu-id="5baff-129">dove:</span><span class="sxs-lookup"><span data-stu-id="5baff-129">where:</span></span>  
  
    -   <span data-ttu-id="5baff-130">Il parametro `-p` identifica il GUID del provider.</span><span class="sxs-lookup"><span data-stu-id="5baff-130">The `-p` parameter identifies the provider GUID.</span></span>  
  
    -   `0x1CCBD` <span data-ttu-id="5baff-131">Specifica le categorie di eventi che verranno generati.</span><span class="sxs-lookup"><span data-stu-id="5baff-131">specifies the categories of events that will be raised.</span></span>  
  
    -   `0x5` <span data-ttu-id="5baff-132">Imposta il livello di registrazione (in questo caso verbose (5)).</span><span class="sxs-lookup"><span data-stu-id="5baff-132">sets the level of logging (in this case, verbose (5)).</span></span>  
  
    -   <span data-ttu-id="5baff-133">Il parametro `-ets` indica a Logman di inviare comandi alle sessioni di traccia degli eventi.</span><span class="sxs-lookup"><span data-stu-id="5baff-133">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>  
  
    -   <span data-ttu-id="5baff-134">Il parametro `-ct perf` specifica che la funzione `QueryPerformanceCounter` verrà utilizzata per registrare il timestamp per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="5baff-134">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>  
  
2.  <span data-ttu-id="5baff-135">Per interrompere la registrazione degli eventi, digitare:</span><span class="sxs-lookup"><span data-stu-id="5baff-135">To stop logging the events, type:</span></span>  
  
     `logman stop clrevents -ets`  
  
     <span data-ttu-id="5baff-136">Questo comando crea un file di traccia binario denominato clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="5baff-136">This command creates a binary trace file named clrevents.etl.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="5baff-137">Per acquisire eventi ETW CLR tramite Xperf</span><span class="sxs-lookup"><span data-stu-id="5baff-137">To capture CLR ETW events using Xperf</span></span>  
  
1.  <span data-ttu-id="5baff-138">Al prompt dei comandi, digitare:</span><span class="sxs-lookup"><span data-stu-id="5baff-138">At the command prompt, type:</span></span>  
  
     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`  
  
     <span data-ttu-id="5baff-139">dove il GUID è il GUID del provider ETW CLR e `0x1CCBD:5` traccia qualsiasi evento appartenente al livello 5 (verbose) e ai livelli inferiori.</span><span class="sxs-lookup"><span data-stu-id="5baff-139">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>  
  
2.  <span data-ttu-id="5baff-140">Per interrompere la traccia, digitare:</span><span class="sxs-lookup"><span data-stu-id="5baff-140">To stop tracing, type:</span></span>  
  
     `Xperf -stop clr`  
  
     <span data-ttu-id="5baff-141">Questo comando crea un file di traccia denominato clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="5baff-141">This command creates a trace file named clrevents.etl.</span></span>  
  
## <a name="viewing-clr-etw-events"></a><span data-ttu-id="5baff-142">Visualizzazione di eventi ETW CLR</span><span class="sxs-lookup"><span data-stu-id="5baff-142">Viewing CLR ETW Events</span></span>  
 <span data-ttu-id="5baff-143">Utilizzare i comandi elencati di seguito per visualizzare gli eventi ETW CLR.</span><span class="sxs-lookup"><span data-stu-id="5baff-143">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="5baff-144">Per una descrizione degli eventi, vedere [Eventi ETW di CLR](../../../docs/framework/performance/clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="5baff-144">For a description of the events, see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).</span></span>  
  
#### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="5baff-145">Per visualizzare gli eventi ETW CLR tramite Tracerpt</span><span class="sxs-lookup"><span data-stu-id="5baff-145">To view CLR ETW events using Tracerpt</span></span>  
  
-   <span data-ttu-id="5baff-146">Al prompt dei comandi, digitare:</span><span class="sxs-lookup"><span data-stu-id="5baff-146">At the command prompt, type:</span></span>  
  
     `tracerpt clrevents.etl`  
  
     <span data-ttu-id="5baff-147">Questo comando crea due file: dumpfile.xml e summary.txt.</span><span class="sxs-lookup"><span data-stu-id="5baff-147">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="5baff-148">Nel file dumpfile.xml sono elencati tutti gli eventi, mentre summary.txt fornisce un riepilogo degli eventi.</span><span class="sxs-lookup"><span data-stu-id="5baff-148">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>  
  
#### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="5baff-149">Per visualizzare gli eventi ETW CLR tramite Xperf</span><span class="sxs-lookup"><span data-stu-id="5baff-149">To view CLR ETW events using Xperf</span></span>  
  
-   <span data-ttu-id="5baff-150">Al prompt dei comandi, digitare:</span><span class="sxs-lookup"><span data-stu-id="5baff-150">At the command prompt, type:</span></span>  
  
     `xperf clrevents.etl`  
  
     <span data-ttu-id="5baff-151">Questo comando apre il visualizzatore di file ETL Xperf.</span><span class="sxs-lookup"><span data-stu-id="5baff-151">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="5baff-152">In questo visualizzatore, gli eventi CLR compaiono nella vista **Eventi generici**.</span><span class="sxs-lookup"><span data-stu-id="5baff-152">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="5baff-153">Per visualizzare una griglia dei dati di eventi suddivisi in categorie in base al tipo, selezionare un'area temporale in questa visualizzazione e quindi fare clic con il pulsante destro del mouse e selezionare **Riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="5baff-153">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>  
  
#### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="5baff-154">Per convertire il file con estensione etl in un file con valori delimitati da virgole</span><span class="sxs-lookup"><span data-stu-id="5baff-154">To convert the .etl file to a comma-separated value file</span></span>  
  
-   <span data-ttu-id="5baff-155">Al prompt dei comandi, digitare:</span><span class="sxs-lookup"><span data-stu-id="5baff-155">At the command prompt, type:</span></span>  
  
     `xperf -i clrevents.etl -f clrevents.csv`  
  
     <span data-ttu-id="5baff-156">Questo comando fa in modo che XPerf esegua il dump degli eventi come un file (CSV) con valori delimitati da virgole visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="5baff-156">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="5baff-157">Poiché eventi diversi dispongono di campi diversi, questo file con estensione CSV contiene più di una riga di intestazione prima dei dati.</span><span class="sxs-lookup"><span data-stu-id="5baff-157">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="5baff-158">Il primo campo di ogni riga è il tipo di evento che indica quale intestazione deve essere utilizzata per determinare gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="5baff-158">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5baff-159">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5baff-159">See also</span></span>

- [<span data-ttu-id="5baff-160">Windows Performance Toolkit</span><span class="sxs-lookup"><span data-stu-id="5baff-160">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="5baff-161">Eventi ETW in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="5baff-161">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
