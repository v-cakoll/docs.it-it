---
title: Strumento di analisi composizione (Mefx)
ms.date: 03/30/2017
helpviewer_keywords:
- Composition Analysis Tool [MEF]
- MEF, Composition Analysis Tool
- Mefx [MEF], Composition Analysis Tool
ms.assetid: c48a7f93-83bb-4a06-aea0-d8e7bd1502ad
ms.openlocfilehash: 7d0acf16ace5aad60b32b7139a58a258fb080ee0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181293"
---
# <a name="composition-analysis-tool-mefx"></a><span data-ttu-id="bfd8f-102">Strumento di analisi composizione (Mefx)</span><span class="sxs-lookup"><span data-stu-id="bfd8f-102">Composition Analysis Tool (Mefx)</span></span>
<span data-ttu-id="bfd8f-103">Lo strumento di analisi composizione (Mefx) è un'applicazione della riga di comando che analizza i file di libreria (DLL) e di applicazione (EXE) che contengono le parti MEF (Managed Extensibility Framework).</span><span class="sxs-lookup"><span data-stu-id="bfd8f-103">The Composition Analysis Tool (Mefx) is a command-line application that analyzes library (.dll) and application (.exe) files containing Managed Extensibility Framework (MEF) parts.</span></span> <span data-ttu-id="bfd8f-104">Lo scopo principale di Mefx è fornire agli sviluppatori un modo per diagnosticare gli errori di composizione nelle relative applicazioni MEF senza la necessità di aggiungere codice di analisi complesso all'applicazione stessa.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-104">The primary purpose of Mefx is to provide developers a way to diagnose composition failures in their MEF applications without the requirement to add cumbersome tracing code to the application itself.</span></span> <span data-ttu-id="bfd8f-105">Può essere utile anche per comprendere le parti di una libreria fornita da terze parti.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-105">It can also be useful to help understand parts from a library provided by a third party.</span></span> <span data-ttu-id="bfd8f-106">Questo argomento descrive come usare Mefx e fornisce un riferimento per la relativa sintassi.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-106">This topic describes how to use Mefx and provides a reference for its syntax.</span></span>  
  
<a name="getting_mefx"></a>
## <a name="getting-mefx"></a><span data-ttu-id="bfd8f-107">Come ottenere Mefx</span><span class="sxs-lookup"><span data-stu-id="bfd8f-107">Getting Mefx</span></span>  
 <span data-ttu-id="bfd8f-108">Mefx è disponibile su GitHub in [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0).</span><span class="sxs-lookup"><span data-stu-id="bfd8f-108">Mefx is available on GitHub at [Managed Extensibility Framework](https://github.com/MicrosoftArchive/mef/releases/tag/4.0).</span></span> <span data-ttu-id="bfd8f-109">Scaricare e decomprimere semplicemente lo strumento.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-109">Simply download and unzip the tool.</span></span>  
  
<a name="basic_syntax"></a>
## <a name="basic-syntax"></a><span data-ttu-id="bfd8f-110">Sintassi di base</span><span class="sxs-lookup"><span data-stu-id="bfd8f-110">Basic Syntax</span></span>  
 <span data-ttu-id="bfd8f-111">Mefx viene richiamato dalla riga di comando nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="bfd8f-111">Mefx is invoked from the command line in the following format:</span></span>  
  
```console
mefx [files and directories] [action] [options]  
```  
  
 <span data-ttu-id="bfd8f-112">Il primo set di argomenti specifica i file e le directory da cui caricare le parti per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-112">The first set of arguments specify the files and directories from which to load parts for analysis.</span></span> <span data-ttu-id="bfd8f-113">Specificare un file con l'opzione `/file:` e una directory con l'opzione `/directory:` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-113">Specify a file with the `/file:` switch, and a directory with the `/directory:` switch.</span></span> <span data-ttu-id="bfd8f-114">È possibile specificare più file e directory, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-114">You can specify multiple files or directories, as shown in the following example:</span></span>  
  
```console  
mefx /file:MyAddIn.dll /directory:Program\AddIns [action...]  
```  
  
> [!NOTE]
> <span data-ttu-id="bfd8f-115">Ogni file dll o exe deve essere caricato solo una volta.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-115">Each .dll or .exe should only be loaded one time.</span></span> <span data-ttu-id="bfd8f-116">Se un file viene caricato più volte, lo strumento può restituire informazioni non corrette.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-116">If a file is loaded multiple times, the tool may return incorrect information.</span></span>  
  
 <span data-ttu-id="bfd8f-117">Dopo l'elenco dei file e delle directory è necessario specificare un comando e tutte le opzioni per il comando.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-117">After the list of files and directories, you must specify a command, and any options for that command.</span></span>  
  
<a name="listing_available_parts"></a>
## <a name="listing-available-parts"></a><span data-ttu-id="bfd8f-118">Elenco delle parti disponibili</span><span class="sxs-lookup"><span data-stu-id="bfd8f-118">Listing Available Parts</span></span>  
 <span data-ttu-id="bfd8f-119">Usare l'azione `/parts` per elencare tutte le parti dichiarate nei file caricati.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-119">Use the `/parts` action to list all the parts declared in the files loaded.</span></span> <span data-ttu-id="bfd8f-120">Il risultato è un semplice elenco di nomi di parti.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-120">The result is a simple list of part names.</span></span>  
  
```console
mefx /file:MyAddIn.dll /parts  
MyAddIn.AddIn  
MyAddIn.MemberPart  
```  
  
 <span data-ttu-id="bfd8f-121">Per altre informazioni sulle parti, usare l'opzione `/verbose` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-121">For more information about the parts, use the `/verbose` option.</span></span> <span data-ttu-id="bfd8f-122">Verranno restituite altre informazioni per tutte le parti disponibili.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-122">This will output more information for all available parts.</span></span> <span data-ttu-id="bfd8f-123">Per ottenere altre informazioni su una singola parte, usare l'azione `/type` invece di `/parts`.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-123">To get more information about a single part, use the `/type` action instead of `/parts`.</span></span>  
  
```console  
mefx /file:MyAddIn.dll /type:MyAddIn.AddIn /verbose  
[Part] MyAddIn.MemberPart from: AssemblyCatalog (Assembly=" MyAddIn, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] MyAddIn.MemberPart (ContractName=" MyAddIn.MemberPart")  
```  
  
<a name="listing_imports_and_exports"></a>
## <a name="listing-imports-and-exports"></a><span data-ttu-id="bfd8f-124">Elenco delle importazioni e delle esportazioni</span><span class="sxs-lookup"><span data-stu-id="bfd8f-124">Listing Imports and Exports</span></span>  
 <span data-ttu-id="bfd8f-125">Le azioni `/imports` e `/exports` elencheranno rispettivamente tutte le parti importate e tutte le parti esportate.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-125">The `/imports` and `/exports` actions will list all the imported parts and all the exported parts, respectively.</span></span> <span data-ttu-id="bfd8f-126">È anche possibile elencare le parti che importano o esportano un tipo specifico usando le azioni `/importers` o `/exporters` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-126">You can also list the parts that import or export a particular type by using the `/importers` or `/exporters` actions.</span></span>  
  
```console  
mefx /file:MyAddIn.dll /importers:MyAddin.MemberPart  
MyAddin.AddIn  
```  
  
 <span data-ttu-id="bfd8f-127">A queste azioni è anche possibile applicare l'opzione `/verbose` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-127">You can also apply the `/verbose` option to these actions.</span></span>  
  
<a name="finding_rejected_parts"></a>
## <a name="finding-rejected-parts"></a><span data-ttu-id="bfd8f-128">Individuazione delle parti rifiutate</span><span class="sxs-lookup"><span data-stu-id="bfd8f-128">Finding Rejected Parts</span></span>  
 <span data-ttu-id="bfd8f-129">Una volta caricate le parti disponibili, Mefx usa il motore di composizione MEF per comporle.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-129">Once it has loaded the available parts, Mefx uses the MEF composition engine to compose them.</span></span> <span data-ttu-id="bfd8f-130">Le parti che non possono essere composte correttamente vengono definite *rifiutate*.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-130">Parts that cannot be successfully composed are referred to as *rejected*.</span></span> <span data-ttu-id="bfd8f-131">Per elencare tutte le parti rifiutate, usare l'azione `/rejected` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-131">To list all the rejected parts, use the `/rejected` action.</span></span>  
  
 <span data-ttu-id="bfd8f-132">È possibile usare l'opzione `/verbose` con l'azione `/rejected` per stampare le informazioni dettagliate relative alle parti rifiutate.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-132">You can use the `/verbose` option with the `/rejected` action to print detailed information about rejected parts.</span></span> <span data-ttu-id="bfd8f-133">Nell'esempio seguente la DLL `ClassLibrary1` contiene la parte `AddIn` che importa le parti `MemberPart` e `ChainOne` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-133">In the following example, the `ClassLibrary1` DLL contains the `AddIn` part, which imports the `MemberPart` and `ChainOne` parts.</span></span> <span data-ttu-id="bfd8f-134">`ChainOne` importa `ChainTwo`, ma `ChainTwo` non esiste.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-134">`ChainOne` imports `ChainTwo`, but `ChainTwo` does not exist.</span></span> <span data-ttu-id="bfd8f-135">Ciò significa che `ChainOne` viene rifiutato causando il rifiuto di `AddIn` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-135">This means that `ChainOne` is rejected, which causes `AddIn` to be rejected.</span></span>  
  
```console  
mefx /file:ClassLibrary1.dll /rejected /verbose  
```  
  
 <span data-ttu-id="bfd8f-136">Di seguito viene mostrato l'output completo del comando precedente:</span><span class="sxs-lookup"><span data-stu-id="bfd8f-136">The following shows the complete output of the previous command:</span></span>  
  
```output
[Part] ClassLibrary1.AddIn from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Export] ClassLibrary1.AddIn (ContractName="ClassLibrary1.AddIn")  
  [Import] ClassLibrary1.AddIn.memberPart (ContractName="ClassLibrary1.MemberPart")  
    [SatisfiedBy] ClassLibrary1.MemberPart (ContractName="ClassLibrary1.MemberPart") from: ClassLibrary1.MemberPart from: AssemblyCatalog (Assembly="ClassLibrar  
y1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Import] ClassLibrary1.AddIn.chain (ContractName="ClassLibrary1.ChainOne")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainOne") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainOne".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
    [Unsuitable] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
from: ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
      [Because] PartDefinitionIsRejected, The part providing the export is rejected because of other issues.  
  
[Part] ClassLibrary1.ChainOne from: AssemblyCatalog (Assembly="ClassLibrary1, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null")  
  [Primary Rejection]  
  [Export] ClassLibrary1.ChainOne (ContractName="ClassLibrary1.ChainOne")  
  [Import] ClassLibrary1.ChainOne.chain (ContractName="ClassLibrary1.ChainTwo")  
    [Exception] System.ComponentModel.Composition.ImportCardinalityMismatchException: No valid exports were found that match the constraint '((exportDefinition.ContractName == "ClassLibrary1.ChainTwo") AndAlso (exportDefinition.Metadata.ContainsKey("ExportTypeIdentity") AndAlso "ClassLibrary1.ChainTwo".Equals(exportDefinition.Metadata.get_Item("ExportTypeIdentity"))))', invalid exports may have been rejected.  
   at System.ComponentModel.Composition.Hosting.ExportProvider.GetExports(ImportDefinition definition, AtomicComposition atomicComposition)  
   at Microsoft.ComponentModel.Composition.Diagnostics.CompositionInfo.AnalyzeImportDefinition(ExportProvider host, IEnumerable`1 availableParts, ImportDefinition id)  
```  
  
 <span data-ttu-id="bfd8f-137">Le informazioni interessanti sono contenute nei risultati `[Exception]` e `[Unsuitable]` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-137">The interesting information is contained in the `[Exception]` and `[Unsuitable]` results.</span></span> <span data-ttu-id="bfd8f-138">Il risultato `[Exception]` fornisce informazioni sul motivo per cui una parte è stata rifiutata.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-138">The `[Exception]` result provides information about why a part was rejected.</span></span> <span data-ttu-id="bfd8f-139">Il risultato `[Unsuitable]` indica il motivo per cui non è possibile usare una parte con una diversa corrispondenza per soddisfare un'importazione. In questo caso il motivo è dovuto al fatto che la parte stessa è stata rifiutata a causa di importazioni mancanti.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-139">The `[Unsuitable]` result indicates why an otherwise-matching part could not be used to fill an import; in this case, because that part was itself rejected for missing imports.</span></span>  
  
<a name="analyzing_primary_causes"></a>
## <a name="analyzing-primary-causes"></a><span data-ttu-id="bfd8f-140">Analisi delle cause principali</span><span class="sxs-lookup"><span data-stu-id="bfd8f-140">Analyzing Primary Causes</span></span>  
 <span data-ttu-id="bfd8f-141">Se alcune parti sono collegate in una lunga catena di dipendenza, un problema che riguarda la parte finale può causare il rifiuto dell'intera catena.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-141">If several parts are linked in a long dependency chain, a problem involving a part near the bottom may cause the entire chain to be rejected.</span></span> <span data-ttu-id="bfd8f-142">La diagnosi di questi problemi può essere difficile perché la causa radice dell'errore non è sempre ovvia.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-142">Diagnosing these problems can be difficult because the root cause of the failure is not always obvious.</span></span> <span data-ttu-id="bfd8f-143">Per risolvere il problema, è possibile usare l'azione `/causes` , che tenta di individuare la causa radice di qualsiasi rifiuto a cascata.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-143">To help with the problem, you can use the `/causes` action, which attempts to find the root cause of any cascading rejection.</span></span>  
  
 <span data-ttu-id="bfd8f-144">Se si usa l'azione `/causes` dell'esempio precedente, vengono elencate solo le informazioni relative a `ChainOne`, la cui importazione non soddisfatta rappresenta la causa radice del rifiuto di `AddIn`.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-144">Using the `/causes` action on the previous example would list only information for `ChainOne`, whose unfilled import is the root cause of the rejection of `AddIn`.</span></span> <span data-ttu-id="bfd8f-145">L'azione `/causes` può essere usata sia con l'opzione normale che con l'opzione `/verbose` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-145">The `/causes` action can be used in both normal and `/verbose` options.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bfd8f-146">Nella maggior parte dei casi, Mefx sarà in grado di diagnosticare la causa radice di un errore a cascata.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-146">In most cases, Mefx will be able to diagnose the root cause of a cascading failure.</span></span> <span data-ttu-id="bfd8f-147">Tuttavia, nei casi in cui le parti vengono aggiunte a un contenitore a livello di codice, nei casi che riguardano contenitori gerarchici o nei casi che riguardano implementazioni personalizzate di `ExportProvider` , Mefx non sarà in grado di diagnosticare la causa.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-147">However, in cases where parts are added programmatically to a container, cases involving hierarchical containers, or cases involving custom `ExportProvider` implementations, Mefx will not be able to diagnose the cause.</span></span> <span data-ttu-id="bfd8f-148">In generale, i casi descritti precedentemente devono essere evitati laddove possibile, poiché la diagnosi degli errori è generalmente complessa.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-148">In general, the previously described cases should be avoided where possible, as failures are generally difficult to diagnose.</span></span>  
  
<a name="white_lists"></a>
## <a name="white-lists"></a><span data-ttu-id="bfd8f-149">Elenchi degli elementi consentiti</span><span class="sxs-lookup"><span data-stu-id="bfd8f-149">White Lists</span></span>  
 <span data-ttu-id="bfd8f-150">L'opzione `/whitelist` consente di specificare un file di testo che elenca le parti di cui è previsto il rifiuto.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-150">The `/whitelist` option enables you to specify a text file that lists parts that are expected to be rejected.</span></span> <span data-ttu-id="bfd8f-151">I rifiuti imprevisti verranno quindi contrassegnati.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-151">Unexpected rejections will then be flagged.</span></span> <span data-ttu-id="bfd8f-152">Ciò può essere utile quando si analizza una libreria incompleta o una sottolibreria in cui mancano alcune dipendenze.</span><span class="sxs-lookup"><span data-stu-id="bfd8f-152">This can be useful when you analyze an incomplete library, or a sub-library that is missing some dependencies.</span></span> <span data-ttu-id="bfd8f-153">L'opzione `/whitelist` può essere applicata alle azioni `/rejected` o `/causes` .</span><span class="sxs-lookup"><span data-stu-id="bfd8f-153">The `/whitelist` option can be applied to the `/rejected` or `/causes` actions.</span></span>  
  
 <span data-ttu-id="bfd8f-154">Si consideri un file denominato test.txt che contiene il testo "ClassLibrary1.ChainOne".</span><span class="sxs-lookup"><span data-stu-id="bfd8f-154">Consider a file named test.txt that contains the text "ClassLibrary1.ChainOne".</span></span> <span data-ttu-id="bfd8f-155">Se si esegue l'azione `/rejected` con l'opzione `/whitelist` dell'esempio precedente, verrà generato l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="bfd8f-155">If you run the `/rejected` action with the `/whitelist` option on the previous example, it will produce the following output:</span></span>  
  
```console
mefx /file:ClassLibrary1.dll /rejected /whitelist:test.txt  
[Unexpected] ClassLibrary1.AddIn  
ClassLibrary1.ChainOne  
```
