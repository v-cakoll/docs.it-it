---
title: Controllo della registrazione di .NET Framework
description: Utilizzare Event Tracing for Windows (ETW) per controllare la registrazione .NET e gli eventi di registrazione Common Language Runtime (CLR). Usare strumenti come logman, Tracerpt e Xperf.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
ms.openlocfilehash: 45d9244eb11b914fd203f24057e1b65c6bef18c2
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309586"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="41fd4-104">Controllo della registrazione di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="41fd4-104">Controlling .NET Framework Logging</span></span>

<span data-ttu-id="41fd4-105">È possibile utilizzare Traccia eventi per Windows (ETW) per registrare eventi CLR (Common Language Runtime).</span><span class="sxs-lookup"><span data-stu-id="41fd4-105">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="41fd4-106">Tramite i seguenti strumenti si possono creare e visualizzare tracce:</span><span class="sxs-lookup"><span data-stu-id="41fd4-106">You can create and view traces by using the following tools:</span></span>

- <span data-ttu-id="41fd4-107">Gli strumenti da riga di comando [Logman](/windows-server/administration/windows-commands/logman) e [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1), inclusi nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="41fd4-107">The [Logman](/windows-server/administration/windows-commands/logman) and [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) command-line tools, which are included with the Windows operating system.</span></span>

- <span data-ttu-id="41fd4-108">Gli strumenti [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) in [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span><span class="sxs-lookup"><span data-stu-id="41fd4-108">The [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools in the [Windows Performance Toolkit](/windows-hardware/test/wpt/).</span></span> <span data-ttu-id="41fd4-109">Per altre informazioni su Xperf, vedere il [blog sulle prestazioni di Windows](https://docs.microsoft.com/archive/blogs/pigscanfly/).</span><span class="sxs-lookup"><span data-stu-id="41fd4-109">For more information about Xperf, see the [Windows Performance blog](https://docs.microsoft.com/archive/blogs/pigscanfly/).</span></span>

<span data-ttu-id="41fd4-110">Per acquisire informazioni sugli eventi CLR, è necessario installare il provider CLR nel computer in uso.</span><span class="sxs-lookup"><span data-stu-id="41fd4-110">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="41fd4-111">Per confermare la corretta installazione del provider, digitare `logman query providers` al prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="41fd4-111">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="41fd4-112">Verrà visualizzato un elenco di provider.</span><span class="sxs-lookup"><span data-stu-id="41fd4-112">A list of providers is displayed.</span></span> <span data-ttu-id="41fd4-113">L'elenco deve contenere una voce relativa al provider CLR, come riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="41fd4-113">This list should contain an entry for the CLR provider, as follows.</span></span>

```output
Provider                                 GUID
-------------------------------------------------------------------------------
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.
```

<span data-ttu-id="41fd4-114">Se il provider CLR non compare nell'elenco, è possibile installarlo in Windows Vista e nei sistemi operativi successivi tramite lo strumento da riga di comando [Wevtutil](/windows-server/administration/windows-commands/wevtutil) di Windows.</span><span class="sxs-lookup"><span data-stu-id="41fd4-114">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](/windows-server/administration/windows-commands/wevtutil) command-line tool.</span></span> <span data-ttu-id="41fd4-115">Aprire la finestra del prompt dei comandi come amministratore.</span><span class="sxs-lookup"><span data-stu-id="41fd4-115">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="41fd4-116">Modificare la directory dei messaggi di richiesta nella cartella .NET Framework 4 (%WINDIR%\Microsoft.NET\Framework [64] \v4. \<.NET version> \ ).</span><span class="sxs-lookup"><span data-stu-id="41fd4-116">Change the prompt directory to the .NET Framework 4 folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="41fd4-117">Questa cartella contiene il file CLR-ETW.man.</span><span class="sxs-lookup"><span data-stu-id="41fd4-117">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="41fd4-118">Al prompt dei comandi digitare il comando seguente per installare il provider CLR:</span><span class="sxs-lookup"><span data-stu-id="41fd4-118">At the command prompt, type the following command to install the CLR provider:</span></span>

`wevtutil im CLR-ETW.man`

## <a name="capturing-clr-etw-events"></a><span data-ttu-id="41fd4-119">Acquisizione di eventi ETW CLR</span><span class="sxs-lookup"><span data-stu-id="41fd4-119">Capturing CLR ETW Events</span></span>

<span data-ttu-id="41fd4-120">È possibile usare gli strumenti da riga di comando [Logman](/windows-server/administration/windows-commands/logman) e [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) per acquisire gli eventi ETW e gli strumenti [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) e [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) per decodificare gli eventi di traccia.</span><span class="sxs-lookup"><span data-stu-id="41fd4-120">You can use the [Logman](/windows-server/administration/windows-commands/logman) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) command-line tools to capture ETW events, and the [Tracerpt](/windows-server/administration/windows-commands/tracerpt_1) and [Xperf](/windows-hardware/test/wpt/xperf-command-line-reference) tools to decode the trace events.</span></span>

<span data-ttu-id="41fd4-121">Per attivare la registrazione, un utente deve specificare tre impostazioni:</span><span class="sxs-lookup"><span data-stu-id="41fd4-121">To turn on logging, a user must specify three things:</span></span>

- <span data-ttu-id="41fd4-122">Il provider a cui comunicare.</span><span class="sxs-lookup"><span data-stu-id="41fd4-122">The provider to communicate to.</span></span>

- <span data-ttu-id="41fd4-123">Un numero a 64 bit che rappresenta un set di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="41fd4-123">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="41fd4-124">Ogni parola chiave rappresenta un set di eventi che il provider può attivare.</span><span class="sxs-lookup"><span data-stu-id="41fd4-124">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="41fd4-125">Il numero rappresenta un set combinato di parole chiave da attivare.</span><span class="sxs-lookup"><span data-stu-id="41fd4-125">The number represents a combined set of keywords to turn on.</span></span>

- <span data-ttu-id="41fd4-126">Un numero piccolo che rappresenta il livello (livello di dettaglio) a cui registrare.</span><span class="sxs-lookup"><span data-stu-id="41fd4-126">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="41fd4-127">Il livello 1 è il livello di dettaglio minore e il livello 5 è il livello dettaglio maggiore.</span><span class="sxs-lookup"><span data-stu-id="41fd4-127">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="41fd4-128">Il livello 0 è un'impostazione predefinita il cui significato è specifico del provider.</span><span class="sxs-lookup"><span data-stu-id="41fd4-128">Level 0 is a default whose meaning is provider-specific.</span></span>

### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="41fd4-129">Per acquisire eventi ETW CLR tramite Logman</span><span class="sxs-lookup"><span data-stu-id="41fd4-129">To capture CLR ETW events using Logman</span></span>

1. <span data-ttu-id="41fd4-130">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="41fd4-130">At the command prompt, type:</span></span>

     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`

     <span data-ttu-id="41fd4-131">dove:</span><span class="sxs-lookup"><span data-stu-id="41fd4-131">where:</span></span>

    - <span data-ttu-id="41fd4-132">Il parametro `-p` identifica il GUID del provider.</span><span class="sxs-lookup"><span data-stu-id="41fd4-132">The `-p` parameter identifies the provider GUID.</span></span>

    - <span data-ttu-id="41fd4-133">`0x1CCBD` specifica le categorie degli eventi che saranno generati.</span><span class="sxs-lookup"><span data-stu-id="41fd4-133">`0x1CCBD` specifies the categories of events that will be raised.</span></span>

    - <span data-ttu-id="41fd4-134">`0x5` imposta il livello di registrazione, in questo caso Verbose (5).</span><span class="sxs-lookup"><span data-stu-id="41fd4-134">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>

    - <span data-ttu-id="41fd4-135">Il parametro `-ets` indica a Logman di inviare comandi alle sessioni di traccia degli eventi.</span><span class="sxs-lookup"><span data-stu-id="41fd4-135">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>

    - <span data-ttu-id="41fd4-136">Il parametro `-ct perf` specifica che la funzione `QueryPerformanceCounter` verrà utilizzata per registrare il timestamp per ogni evento.</span><span class="sxs-lookup"><span data-stu-id="41fd4-136">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>

2. <span data-ttu-id="41fd4-137">Per interrompere la registrazione degli eventi, digitare:</span><span class="sxs-lookup"><span data-stu-id="41fd4-137">To stop logging the events, type:</span></span>

     `logman stop clrevents -ets`

     <span data-ttu-id="41fd4-138">Questo comando crea un file di traccia binario denominato clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="41fd4-138">This command creates a binary trace file named clrevents.etl.</span></span>

### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="41fd4-139">Per acquisire eventi ETW CLR tramite Xperf</span><span class="sxs-lookup"><span data-stu-id="41fd4-139">To capture CLR ETW events using Xperf</span></span>

1. <span data-ttu-id="41fd4-140">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="41fd4-140">At the command prompt, type:</span></span>

     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`

     <span data-ttu-id="41fd4-141">dove il GUID è il GUID del provider ETW CLR e `0x1CCBD:5` traccia qualsiasi evento appartenente al livello 5 (verbose) e ai livelli inferiori.</span><span class="sxs-lookup"><span data-stu-id="41fd4-141">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>

2. <span data-ttu-id="41fd4-142">Per interrompere la traccia, digitare:</span><span class="sxs-lookup"><span data-stu-id="41fd4-142">To stop tracing, type:</span></span>

     `Xperf -stop clr`

     <span data-ttu-id="41fd4-143">Questo comando crea un file di traccia denominato clrevents.etl.</span><span class="sxs-lookup"><span data-stu-id="41fd4-143">This command creates a trace file named clrevents.etl.</span></span>

## <a name="viewing-clr-etw-events"></a><span data-ttu-id="41fd4-144">Visualizzazione di eventi ETW CLR</span><span class="sxs-lookup"><span data-stu-id="41fd4-144">Viewing CLR ETW Events</span></span>

<span data-ttu-id="41fd4-145">Utilizzare i comandi elencati di seguito per visualizzare gli eventi ETW CLR.</span><span class="sxs-lookup"><span data-stu-id="41fd4-145">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="41fd4-146">Per una descrizione degli eventi, vedere [Eventi ETW di CLR](clr-etw-events.md).</span><span class="sxs-lookup"><span data-stu-id="41fd4-146">For a description of the events, see [CLR ETW Events](clr-etw-events.md).</span></span>

### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="41fd4-147">Per visualizzare gli eventi ETW CLR tramite Tracerpt</span><span class="sxs-lookup"><span data-stu-id="41fd4-147">To view CLR ETW events using Tracerpt</span></span>

- <span data-ttu-id="41fd4-148">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="41fd4-148">At the command prompt, type:</span></span>

     `tracerpt clrevents.etl`

     <span data-ttu-id="41fd4-149">Questo comando crea due file: dumpfile.xml e summary.txt.</span><span class="sxs-lookup"><span data-stu-id="41fd4-149">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="41fd4-150">Nel file dumpfile.xml sono elencati tutti gli eventi, mentre summary.txt fornisce un riepilogo degli eventi.</span><span class="sxs-lookup"><span data-stu-id="41fd4-150">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>

### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="41fd4-151">Per visualizzare gli eventi ETW CLR tramite Xperf</span><span class="sxs-lookup"><span data-stu-id="41fd4-151">To view CLR ETW events using Xperf</span></span>

- <span data-ttu-id="41fd4-152">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="41fd4-152">At the command prompt, type:</span></span>

     `xperf clrevents.etl`

     <span data-ttu-id="41fd4-153">Questo comando apre il visualizzatore di file ETL Xperf.</span><span class="sxs-lookup"><span data-stu-id="41fd4-153">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="41fd4-154">In questo visualizzatore, gli eventi CLR compaiono nella vista **Eventi generici**.</span><span class="sxs-lookup"><span data-stu-id="41fd4-154">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="41fd4-155">Per visualizzare una griglia dei dati di eventi suddivisi in categorie in base al tipo, selezionare un'area temporale in questa visualizzazione e quindi fare clic con il pulsante destro del mouse e selezionare **Riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="41fd4-155">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>

### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="41fd4-156">Per convertire il file con estensione etl in un file con valori delimitati da virgole</span><span class="sxs-lookup"><span data-stu-id="41fd4-156">To convert the .etl file to a comma-separated value file</span></span>

- <span data-ttu-id="41fd4-157">Al prompt dei comandi digitare:</span><span class="sxs-lookup"><span data-stu-id="41fd4-157">At the command prompt, type:</span></span>

     `xperf -i clrevents.etl -f clrevents.csv`

     <span data-ttu-id="41fd4-158">Questo comando fa in modo che XPerf esegua il dump degli eventi come un file (CSV) con valori delimitati da virgole visualizzabile.</span><span class="sxs-lookup"><span data-stu-id="41fd4-158">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="41fd4-159">Poiché eventi diversi dispongono di campi diversi, questo file con estensione CSV contiene più di una riga di intestazione prima dei dati.</span><span class="sxs-lookup"><span data-stu-id="41fd4-159">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="41fd4-160">Il primo campo di ogni riga è il tipo di evento che indica quale intestazione deve essere utilizzata per determinare gli altri campi.</span><span class="sxs-lookup"><span data-stu-id="41fd4-160">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="41fd4-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41fd4-161">See also</span></span>

- [<span data-ttu-id="41fd4-162">Windows Performance Toolkit</span><span class="sxs-lookup"><span data-stu-id="41fd4-162">Windows Performance Toolkit</span></span>](/windows-hardware/test/wpt/)
- [<span data-ttu-id="41fd4-163">Eventi ETW in Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="41fd4-163">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
