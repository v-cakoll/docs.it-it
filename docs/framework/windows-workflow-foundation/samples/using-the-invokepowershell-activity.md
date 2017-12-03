---
title: "Utilizzo dell'attività InvokePowerShell"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 956251a0-31ca-4183-bf76-d277c08585df
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3ef8b539e490911e5454fe87db483508cc8a5d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-invokepowershell-activity"></a><span data-ttu-id="cae3e-102">Utilizzo dell'attività InvokePowerShell</span><span class="sxs-lookup"><span data-stu-id="cae3e-102">Using the InvokePowerShell Activity</span></span>
<span data-ttu-id="cae3e-103">Nell'esempio InvokePowerShell viene illustrato come richiamare i comandi di Windows PowerShell usando l'attività `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-103">The InvokePowerShell sample demonstrates how to invoke Windows PowerShell commands using the `InvokePowerShell` activity.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="cae3e-104">Dimostrazione</span><span class="sxs-lookup"><span data-stu-id="cae3e-104">Demonstrates</span></span>  
  
-   <span data-ttu-id="cae3e-105">Semplice innovazione dei comandi di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae3e-105">Simple innovation of Windows PowerShell commands.</span></span>  
  
-   <span data-ttu-id="cae3e-106">Recupero di valori dalla pipeline di output di Windows PowerShell e relativa archiviazione nelle variabili del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="cae3e-106">Retrieve values from the Windows PowerShell output pipeline and store them in workflow variables.</span></span>  
  
-   <span data-ttu-id="cae3e-107">Passaggio di dati in Windows PowerShell come pipeline di input per un comando di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-107">Pass data into windows PowerShell as input pipeline for an executing command.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cae3e-108">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="cae3e-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cae3e-109">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="cae3e-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cae3e-110">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cae3e-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cae3e-111">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="cae3e-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`  
  
## <a name="discussion"></a><span data-ttu-id="cae3e-112">Discussione</span><span class="sxs-lookup"><span data-stu-id="cae3e-112">Discussion</span></span>  
 <span data-ttu-id="cae3e-113">In questo esempio sono contenuti i tre progetti seguenti.</span><span class="sxs-lookup"><span data-stu-id="cae3e-113">This sample contains the following three projects.</span></span>  
  
|<span data-ttu-id="cae3e-114">Nome progetto</span><span class="sxs-lookup"><span data-stu-id="cae3e-114">Project Name</span></span>|<span data-ttu-id="cae3e-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cae3e-115">Description</span></span>|<span data-ttu-id="cae3e-116">File principali</span><span class="sxs-lookup"><span data-stu-id="cae3e-116">Main Files</span></span>|  
|------------------|-----------------|----------------|  
|<span data-ttu-id="cae3e-117">CodedClient</span><span class="sxs-lookup"><span data-stu-id="cae3e-117">CodedClient</span></span>|<span data-ttu-id="cae3e-118">Applicazione client di esempio che usa l'attività PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae3e-118">A sample client application that uses the PowerShell activity.</span></span>|<span data-ttu-id="cae3e-119">-   **Program.cs**: a livello di codice crea un flusso di lavoro basato su sequenze che chiama l'attività InvokePowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae3e-119">-   **Program.cs**: Programmatically creates a sequence-based workflow that calls the InvokePowerShell activity.</span></span>|  
|<span data-ttu-id="cae3e-120">DesignerClient</span><span class="sxs-lookup"><span data-stu-id="cae3e-120">DesignerClient</span></span>|<span data-ttu-id="cae3e-121">Set di attività personalizzate che contengono l'attività personalizzata `InvokePowerShell` e altre varie attività personalizzate, nonché un flusso di lavoro che le usa.</span><span class="sxs-lookup"><span data-stu-id="cae3e-121">A set of custom activities that contain the `InvokePowerShell` custom activity and other miscellaneous custom activities, and a workflow that uses them.</span></span>|<ul><li><span data-ttu-id="cae3e-122">Attività:</span><span class="sxs-lookup"><span data-stu-id="cae3e-122">Activities:</span></span><br /><br /> <ul><li><span data-ttu-id="cae3e-123">**Printcollection**: attività di supporto che stampa tutti gli elementi in una raccolta nella console.</span><span class="sxs-lookup"><span data-stu-id="cae3e-123">**PrintCollection.cs**: A helper activity that prints all the items in a collection to the console.</span></span></li><li><span data-ttu-id="cae3e-124">**ReadLine**: attività di supporto per la lettura dell'input dalla console.</span><span class="sxs-lookup"><span data-stu-id="cae3e-124">**ReadLine.cs**: A helper activity for reading input from the console.</span></span></li></ul></li><li><span data-ttu-id="cae3e-125">File system:</span><span class="sxs-lookup"><span data-stu-id="cae3e-125">File System:</span></span><br /><br /> <ul><li><span data-ttu-id="cae3e-126">**Copy. XAML**: un'attività che copia un file.</span><span class="sxs-lookup"><span data-stu-id="cae3e-126">**Copy.xaml**: An activity that copies a file.</span></span></li><li><span data-ttu-id="cae3e-127">**CreateFile. XAML**: un'attività che crea un file.</span><span class="sxs-lookup"><span data-stu-id="cae3e-127">**CreateFile.xaml**: An activity that creates a file.</span></span></li><li><span data-ttu-id="cae3e-128">**DeleteFile. XAML**: un'attività che elimina un file.</span><span class="sxs-lookup"><span data-stu-id="cae3e-128">**DeleteFile.xaml**: An activity that deletes a file.</span></span></li><li><span data-ttu-id="cae3e-129">**MakeDir. XAML**: un'attività che crea una directory.</span><span class="sxs-lookup"><span data-stu-id="cae3e-129">**MakeDir.xaml**: An activity that creates a directory.</span></span></li><li><span data-ttu-id="cae3e-130">**Move. XAML**: un'attività che consente di spostare un file.</span><span class="sxs-lookup"><span data-stu-id="cae3e-130">**Move.xaml**: An activity that moves a file.</span></span></li><li><span data-ttu-id="cae3e-131">**ReadFile. XAML**: un'attività che legge un file e restituisce il relativo contenuto.</span><span class="sxs-lookup"><span data-stu-id="cae3e-131">**ReadFile.xaml**: An activity that reads a file and returns its contents.</span></span></li><li><span data-ttu-id="cae3e-132">**TestPath. XAML**: attività che verifica l'esistenza di un percorso.</span><span class="sxs-lookup"><span data-stu-id="cae3e-132">**TestPath.xaml**: An activity that tests for the existence of a path.</span></span></li></ul></li><li><span data-ttu-id="cae3e-133">Processo:</span><span class="sxs-lookup"><span data-stu-id="cae3e-133">Process:</span></span><br /><br /> <ul><li><span data-ttu-id="cae3e-134">**GetProcess. XAML**: un'attività che ottiene un elenco dei processi in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-134">**GetProcess.xaml**: An activity that gets a list of running processes.</span></span></li><li><span data-ttu-id="cae3e-135">**Stopprocess. XAML**: un'attività che interrompe un processo specifico.</span><span class="sxs-lookup"><span data-stu-id="cae3e-135">**StopProcess.xaml**: An activity that stops a specific process.</span></span></li></ul></li><li><span data-ttu-id="cae3e-136">**Program.cs**: chiama il flusso di lavoro Sequence1.</span><span class="sxs-lookup"><span data-stu-id="cae3e-136">**Program.cs**: Calls the Sequence1 workflow.</span></span></li><li><span data-ttu-id="cae3e-137">**Sequence1**: un flusso di lavoro basato su sequenze.</span><span class="sxs-lookup"><span data-stu-id="cae3e-137">**Sequence1.xaml**: A sequence-based workflow.</span></span></li></ul>|  
|<span data-ttu-id="cae3e-138">PowerShell</span><span class="sxs-lookup"><span data-stu-id="cae3e-138">PowerShell</span></span>|<span data-ttu-id="cae3e-139">Attività `InvokePowerShell` e finestre di progettazione associate.</span><span class="sxs-lookup"><span data-stu-id="cae3e-139">The `InvokePowerShell` activity and its associated designers.</span></span>|<span data-ttu-id="cae3e-140">File di attività</span><span class="sxs-lookup"><span data-stu-id="cae3e-140">Activity Files</span></span><br /><br /> <span data-ttu-id="cae3e-141">-   **Executepowershell**: logica di esecuzione principale dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cae3e-141">-   **ExecutePowerShell.cs**: The main execution logic of the activity.</span></span><br /><span data-ttu-id="cae3e-142">-   **Invokepowershell. cs**: wrapper della logica di esecuzione principale che contiene una versione generica (valore restituito) e una versione non generica (valore non restituito).</span><span class="sxs-lookup"><span data-stu-id="cae3e-142">-   **InvokePowerShell.cs**: The wrapper around the main execution logic, which contains a generic (return value) version and a non-generic (non-return value) version.</span></span> <span data-ttu-id="cae3e-143">Si tratta dell'interfaccia pubblica per l'attività.</span><span class="sxs-lookup"><span data-stu-id="cae3e-143">This is the public interface for the activity.</span></span><br /><span data-ttu-id="cae3e-144">-   **Nopersistzone**: questa attività impedisce la persistenza delle attività figlio.</span><span class="sxs-lookup"><span data-stu-id="cae3e-144">-   **NoPersistZone.cs**: This activity prevents any child activities from persisting.</span></span> <span data-ttu-id="cae3e-145">Questa classe viene usata all'interno dell'implementazione dell'attività `InvokePowerShell` per evitare che l'attività venga resa persistente a metà esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-145">This class is used within the `InvokePowerShell` activity implementation to prevent the activity from being persisted mid-execution.</span></span><br /><br /> <span data-ttu-id="cae3e-146">File delle finestre di progettazione:</span><span class="sxs-lookup"><span data-stu-id="cae3e-146">Designer files:</span></span><br /><br /> <span data-ttu-id="cae3e-147">1.  **ArgumentDictionaryEditor.cs**: finestra di dialogo di Windows che consente all'utente di modificare gli argomenti del `InvokePowerShell` attività.</span><span class="sxs-lookup"><span data-stu-id="cae3e-147">1.  **ArgumentDictionaryEditor.cs**: A Windows dialog that allows the user to edit the arguments of the `InvokePowerShell` activity.</span></span><br /><span data-ttu-id="cae3e-148">2.  **Genericinvokepowershelldesigner. XAML** e **GenericInvokePowerShellDesigner.xaml.cs**: definisce l'aspetto del tipo generico `InvokePowerShell` attività [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae3e-148">2.  **GenericInvokePowerShellDesigner.xaml** and **GenericInvokePowerShellDesigner.xaml.cs**: Defines the appearance of the generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span><br /><span data-ttu-id="cae3e-149">3.  **Invokepowershelldesigner. XAML** e **invokepowershelldesigner. cs**: definisce l'aspetto del tipo non generico- `InvokePowerShell` attività [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae3e-149">3.  **InvokePowerShellDesigner.xaml** and **InvokePowerShellDesigner.cs**: Defines the appearance of the non-generic `InvokePowerShell` activity in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>|  
  
 <span data-ttu-id="cae3e-150">I progetti client vengono discussi per primi, poiché è più semplice capire la funzionalità interna dell'attività PowerShell una volta capito il relativo uso.</span><span class="sxs-lookup"><span data-stu-id="cae3e-150">The client projects are discussed first, as it is easier to understand the internal functionality of the PowerShell activity once its use is understood.</span></span>  
  
## <a name="using-this-sample"></a><span data-ttu-id="cae3e-151">Utilizzo dell'esempio</span><span class="sxs-lookup"><span data-stu-id="cae3e-151">Using This Sample</span></span>  
 <span data-ttu-id="cae3e-152">Nelle sezioni seguenti viene descritto come usare i tre progetti dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="cae3e-152">The following sections describe how to use the three projects in the sample.</span></span>  
  
### <a name="using-the-coded-client-project"></a><span data-ttu-id="cae3e-153">Utilizzo del progetto CodedClient</span><span class="sxs-lookup"><span data-stu-id="cae3e-153">Using the Coded Client Project</span></span>  
 <span data-ttu-id="cae3e-154">Il client di esempio crea a livello di codice un'attività Sequence che contiene esempi di diversi metodi di utilizzo dell'attività `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-154">The sample client programmatically creates a sequence activity, which contains examples of several different methods of using the `InvokePowerShell` activity.</span></span> <span data-ttu-id="cae3e-155">La prima chiamata avvia il Blocco note.</span><span class="sxs-lookup"><span data-stu-id="cae3e-155">The first invocation launches Notepad.</span></span>  
  
```  
new InvokePowerShell()  
{  
    CommandText = "notepad"  
},  
```  
  
 <span data-ttu-id="cae3e-156">La seconda chiamata ottiene un elenco dei processi in esecuzione nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="cae3e-156">The second invocation gets a list of the processes running on the local machine.</span></span>  
  
```  
new InvokePowerShell<Process>()  
{  
    CommandText = "Get-Process",  
    Output = processes1,  
},  
```  
  
 <span data-ttu-id="cae3e-157">`Output` è la variabile usata per archiviare l'output del comando.</span><span class="sxs-lookup"><span data-stu-id="cae3e-157">`Output` is the variable used to store the output of the command.</span></span>  
  
 <span data-ttu-id="cae3e-158">La chiamata successiva mostra come eseguire un passaggio della post-elaborazione in ogni singolo output della chiamata di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae3e-158">The next call demonstrates how to run a post-processing step on each individual output of the PowerShell invocation.</span></span> <span data-ttu-id="cae3e-159">`InitializationAction` viene impostato sulla funzione che restituisce una rappresentazione in forma di stringa per ogni processo.</span><span class="sxs-lookup"><span data-stu-id="cae3e-159">`InitializationAction` is set to the function that outputs a string representation for each process.</span></span> <span data-ttu-id="cae3e-160">La raccolta di queste stringhe viene restituita nella variabile `Output` dall'attività `InvokePowerShell<string>`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-160">The collection of these strings is returned in the `Output` variable by the `InvokePowerShell<string>` activity.</span></span>  
  
 <span data-ttu-id="cae3e-161">Le chiamate `InvokePowerShell` successive dimostrano il passaggio di dati nell'attività e la restituzione di output ed errori.</span><span class="sxs-lookup"><span data-stu-id="cae3e-161">The succeeding `InvokePowerShell` calls demonstrate passing data into the activity and getting outputs and errors out.</span></span>  
  
### <a name="using-the-designer-client-project"></a><span data-ttu-id="cae3e-162">Utilizzo del progetto DesignerClient</span><span class="sxs-lookup"><span data-stu-id="cae3e-162">Using the Designer Client Project</span></span>  
 <span data-ttu-id="cae3e-163">Il progetto DesignerClient è costituito da un set di attività personalizzate, di cui gran parte è stata compilata con l'attività `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-163">The DesignerClient project consists of a set of custom activities, almost all of which are built containing the `InvokePowerShell` activity.</span></span> <span data-ttu-id="cae3e-164">La maggior parte delle attività chiama la versione non generica dell'attività `InvokePowerShell` e non prevede un valore restituito.</span><span class="sxs-lookup"><span data-stu-id="cae3e-164">Most of the activities call the non-generic version of the `InvokePowerShell` activity, and do not expect a return value.</span></span> <span data-ttu-id="cae3e-165">Le altre attività usano la versione generica dell'attività `InvokePowerShell` e l'argomento `InitializationAction` per elaborare i risultati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="cae3e-165">Other activities use the generic version of the `InvokePowerShell` activity, and use the `InitializationAction` argument to post-process the results.</span></span>  
  
## <a name="using-the-powershell-project"></a><span data-ttu-id="cae3e-166">Utilizzo del progetto PowerShell</span><span class="sxs-lookup"><span data-stu-id="cae3e-166">Using the PowerShell Project</span></span>  
 <span data-ttu-id="cae3e-167">L'azione principale dell'attività si verifica nella classe `ExecutePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-167">The main action of the activity takes place in the `ExecutePowerShell` class.</span></span> <span data-ttu-id="cae3e-168">Poiché l'esecuzione dei comandi di PowerShell non deve bloccare il thread del flusso di lavoro principale, l'attività viene creata in modo da essere un'attività asincrona ereditando dalla classe <xref:System.Activities.AsyncCodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="cae3e-168">Because the execution of PowerShell commands should not block the main workflow thread, the activity is created to be an asynchronous activity by inheriting from the <xref:System.Activities.AsyncCodeActivity> class.</span></span>  
  
 <span data-ttu-id="cae3e-169">Il metodo <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> viene chiamato dall'esecuzione del flusso di lavoro per iniziare l'esecuzione dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cae3e-169">The <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> method is called by the workflow runtime to begin running the activity.</span></span> <span data-ttu-id="cae3e-170">Inizia chiamando le API di PowerShell per creare una pipeline di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae3e-170">It starts by calling PowerShell APIs to create a PowerShell pipeline.</span></span>  
  
```  
runspace = RunspaceFactory.CreateRunspace();  
runspace.Open();  
pipeline = runspace.CreatePipeline();  
```  
  
 <span data-ttu-id="cae3e-171">Successivamente crea un comando di PowerShell e lo popola con parametri e variabili.</span><span class="sxs-lookup"><span data-stu-id="cae3e-171">It then creates a PowerShell command and populates it with parameters and variables.</span></span>  
  
```  
Command cmd = new Command(this.CommandText, this.IsScript);   
// loop over parameters and run: cmd.Parameters.Add(...)  
// loop over variables and run: runspace.SessionStateProxy.SetVariable(...)  
pipeline.Commands.Add(cmd);  
```  
  
 <span data-ttu-id="cae3e-172">A questo punto, gli input inoltrati tramite pipe vengono inviati anche alla pipeline.</span><span class="sxs-lookup"><span data-stu-id="cae3e-172">The inputs piped in are also sent to the pipeline at this point.</span></span> <span data-ttu-id="cae3e-173">Infine, la pipeline viene sottoposta a wrapping in un oggetto `PipelineInvokerAsyncResult` e restituita.</span><span class="sxs-lookup"><span data-stu-id="cae3e-173">Finally, the pipeline is wrapped in a `PipelineInvokerAsyncResult` object and returned.</span></span> <span data-ttu-id="cae3e-174">L'oggetto `PipelineInvokerAsyncResult` registra un listener e richiama la pipeline.</span><span class="sxs-lookup"><span data-stu-id="cae3e-174">The `PipelineInvokerAsyncResult` object registers a listener and invokes the pipeline.</span></span>  
  
```  
pipeline.InvokeAsync();  
```  
  
 <span data-ttu-id="cae3e-175">Al termine dell'esecuzione, gli output e gli errori vengono archiviati all'interno dello stesso oggetto `PipelineInvokerAsyncResult` e il controllo viene restituito all'esecuzione del flusso di lavoro chiamando il metodo di callback passato originariamente al metodo <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="cae3e-175">When execution finishes, output and errors are stored within the same `PipelineInvokerAsyncResult` object, and control is handed back to the workflow runtime by calling the callback method originally passed to <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span></span>  
  
 <span data-ttu-id="cae3e-176">Alla fine dell'esecuzione del metodo, l'esecuzione del flusso di lavoro chiama il metodo <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> dell'attività.</span><span class="sxs-lookup"><span data-stu-id="cae3e-176">At the end of the method's execution, the workflow runtime calls the activity’s <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> method.</span></span>  
  
 <span data-ttu-id="cae3e-177">La classe `InvokePowerShell` esegue il wrapping della classe `ExecutePowerShellCommand` e crea due versioni dell'attività: una generica e una non generica.</span><span class="sxs-lookup"><span data-stu-id="cae3e-177">The `InvokePowerShell` class wraps the `ExecutePowerShellCommand` class and creates two versions of the activity; a generic version and a non-generic version.</span></span> <span data-ttu-id="cae3e-178">La versione non generica restituisce direttamente l'output dell'esecuzione di PowerShell, mentre la versione generica trasforma i singoli risultati nel tipo generico.</span><span class="sxs-lookup"><span data-stu-id="cae3e-178">The non-generic version returns the output of the PowerShell execution directly, whereas the generic version transforms the individual results to the generic type.</span></span>  
  
 <span data-ttu-id="cae3e-179">La versione generica dell'attività viene implementata come un flusso di lavoro sequenziale che chiama l'oggetto `ExecutePowerShellCommand` ed elabora i risultati in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="cae3e-179">The generic version of the activity is implemented as a sequential workflow that calls `ExecutePowerShellCommand` and post-processes its results.</span></span> <span data-ttu-id="cae3e-180">Per ogni elemento nella raccolta di risultati, la fase di post-elaborazione chiama l'oggetto `InitializationAction` se impostato.</span><span class="sxs-lookup"><span data-stu-id="cae3e-180">For each element in the result collection, the post-processing step calls `InitializationAction` if it is set.</span></span> <span data-ttu-id="cae3e-181">In caso contrario, esegue un semplice cast.</span><span class="sxs-lookup"><span data-stu-id="cae3e-181">Otherwise, it does a simple cast.</span></span>  
  
```  
new ForEach<PSObject>  
{  
    Values = psObjects,  
    Body = new ActivityAction<PSObject>  
    {  
        Argument = psObject,  
        Handler = new Sequence  
        {  
            Activities =  
            {  
                new If  
                {  
                    Condition = // Is InitializationAction set?  
                    Then = new InvokeFunc<PSObject, TResult>  
                    {  
                        Argument = psObject,  
                        Result = outputObject,  
                        Func = this.InitializationAction  
                    },  
                    Else = new Assign<TResult>  
                    {  
                        To = outputObject,  
                        Value = new InArgument<TResult>(ctx => (TResult) psObject.Get(ctx).BaseObject),  
                    }  
                },  
                new AddToCollection<TResult>  
                {  
                    Collection = outputObjects,  
                    Item = outputObject  
                },  
            }  
        }  
    }  
},  
```  
  
 <span data-ttu-id="cae3e-182">Per ognuna delle due attività `InvokePowerShell` (generica e non generica), è stata creata una finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-182">For each of the two `InvokePowerShell` activities (generic, and non-generic), a designer was created.</span></span> <span data-ttu-id="cae3e-183">InvokePowerShellDesigner.xaml e il file con estensione cs associato definiscono l'aspetto in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] per la versione non generica dell'attività `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-183">InvokePowerShellDesigner.xaml and its associated .cs file define the appearance in [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] for the non-generic version of the `InvokePowerShell` activity.</span></span> <span data-ttu-id="cae3e-184">In InvokePowerShellDesigner.xaml, viene usato un oggetto <xref:System.Windows.Controls.DockPanel> per rappresentare l'interfaccia grafica.</span><span class="sxs-lookup"><span data-stu-id="cae3e-184">Inside InvokePowerShellDesigner.xaml, a <xref:System.Windows.Controls.DockPanel> is used to represent the graphical interface.</span></span>  
  
```  
<DockPanel x:Uid="DockPanel_1" LastChildFill="True">  
        <TextBlock x:Uid="TextBlock_1" Text="CommandText" />  
        <TextBox x:Uid="TextBox_1" Text="{Binding Path=ModelItem.CommandText, Mode=TwoWay}"  
                 TextWrapping="WrapWithOverflow"  AcceptsReturn="True" MinLines="4" MaxLines="4"  
                 Background="{x:Null}" Margin="3" />  
    </DockPanel>  
```  
  
 <span data-ttu-id="cae3e-185">Si noti che la proprietà `Text` della casella di testo è un'associazione bidirezionale che assicura che il valore della proprietà `CommandText` dell'attività sia equivalente al valore inserito nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-185">Note that the `Text` property of the text box is a two-way binding that ensures that the value of the activity’s `CommandText` property is equivalent to the value input into the designer.</span></span>  
  
 <span data-ttu-id="cae3e-186">GenericInvokePowerShellDesigner.xaml e il file con estensione cs associato definiscono l'interfaccia grafica per l'attività `InvokePowerShell` generica.</span><span class="sxs-lookup"><span data-stu-id="cae3e-186">GenericInvokePowerShellDesigner.xaml and its associated .cs file define the graphical interface for the generic `InvokePowerShell` activity.</span></span> <span data-ttu-id="cae3e-187">La finestra di progettazione è leggermente più complessa perché consente agli utenti di impostare un oggetto `InitializationAction`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-187">The designer is slightly more complicated because it allows users to set an `InitializationAction`.</span></span> <span data-ttu-id="cae3e-188">L'elemento principale è l'uso dell'oggetto <xref:System.Activities.Presentation.WorkflowItemPresenter> per consentire il trascinamento delle attività figlio nell'area di progettazione di `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-188">The key element is the usage of <xref:System.Activities.Presentation.WorkflowItemPresenter> to allow drag and drop of child activities onto the `InvokePowerShell` designer surface.</span></span>  
  
```  
<sap:WorkflowItemPresenter x:Uid="sap:WorkflowItemPresenter_1" Margin="0,10,0,10"  
    HintText="Drop Activities Here"  
    AllowedItemType="{x:Type sa:Activity}"  
    Item="{Binding Path=ModelItem.InitializationAction.Handler, Mode=TwoWay}"  
    Grid.Row="1" Grid.Column="1" />  
```  
  
 <span data-ttu-id="cae3e-189">La personalizzazione della finestra di progettazione non termina con i file con estensione xaml che definiscono l'aspetto dell'attività nell'area di disegno della progettazione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-189">The designer customization does not stop with the .xaml files that define the appearance of the activity on the design canvas.</span></span> <span data-ttu-id="cae3e-190">Anche le finestre di dialogo usate per visualizzare i parametri dell'attività possono essere personalizzate.</span><span class="sxs-lookup"><span data-stu-id="cae3e-190">The dialog boxes used to display the parameters of the activity can also be customized.</span></span> <span data-ttu-id="cae3e-191">Questi parametri e le variabili PowerShell influiscono sul comportamento dei comandi di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cae3e-191">These parameters and PowerShell variables affect the behavior of PowerShell commands.</span></span> <span data-ttu-id="cae3e-192">L'attività li espone come <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` tipi.</span><span class="sxs-lookup"><span data-stu-id="cae3e-192">The activity exposes them as <!--zz <xref:System.Collections.Generic.Dictionary%601>--> `System.Collections.Generic.Dictionary` types.</span></span> <span data-ttu-id="cae3e-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml e PropertyEditorResources.cs definiscono la finestra di dialogo che consente di modificare questi tipi.</span><span class="sxs-lookup"><span data-stu-id="cae3e-193">ArgumentDictionaryEditor.cs, PropertyEditorResources.xaml and PropertyEditorResources.cs define the dialog box that allows you to edit these types.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cae3e-194">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="cae3e-194">To set up, build, and run the sample</span></span>  
 <span data-ttu-id="cae3e-195">È necessario installare Windows PowerShell per eseguire questo esempio.</span><span class="sxs-lookup"><span data-stu-id="cae3e-195">You must install Windows PowerShell to run this sample.</span></span> <span data-ttu-id="cae3e-196">Windows PowerShell può essere installato da questo percorso: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span><span class="sxs-lookup"><span data-stu-id="cae3e-196">Windows PowerShell can be installed from this location: [Windows PowerShell](http://go.microsoft.com/fwlink/?LinkId=150383).</span></span>  
  
#### <a name="to-run-the-coded-client"></a><span data-ttu-id="cae3e-197">Per eseguire il progetto CodedClient</span><span class="sxs-lookup"><span data-stu-id="cae3e-197">To run the coded client</span></span>  
  
1.  <span data-ttu-id="cae3e-198">Aprire PowerShell.sln tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae3e-198">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cae3e-199">Fare clic con il pulsante destro del mouse sulla soluzione e compilarla.</span><span class="sxs-lookup"><span data-stu-id="cae3e-199">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="cae3e-200">Fare doppio clic su di **CodedClient** del progetto e selezionare **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="cae3e-200">Right-click the **CodedClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="cae3e-201">Premere CTRL+F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-201">Press CTRL+F5 to run the application.</span></span>  
  
#### <a name="to-run-the-designer-client"></a><span data-ttu-id="cae3e-202">Per eseguire il progetto DesignerClient</span><span class="sxs-lookup"><span data-stu-id="cae3e-202">To run the designer client</span></span>  
  
1.  <span data-ttu-id="cae3e-203">Aprire PowerShell.sln tramite [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cae3e-203">Open PowerShell.sln using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="cae3e-204">Fare clic con il pulsante destro del mouse sulla soluzione e compilarla.</span><span class="sxs-lookup"><span data-stu-id="cae3e-204">Right-click the solution and build it.</span></span>  
  
3.  <span data-ttu-id="cae3e-205">Fare doppio clic su di **DesignerClient** del progetto e selezionare **imposta come progetto di avvio**.</span><span class="sxs-lookup"><span data-stu-id="cae3e-205">Right-click the **DesignerClient** project and select **Set as Startup Project**.</span></span>  
  
4.  <span data-ttu-id="cae3e-206">Premere CTRL+F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cae3e-206">Press CTRL+F5 to run the application.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="cae3e-207">Problemi noti</span><span class="sxs-lookup"><span data-stu-id="cae3e-207">Known Issues</span></span>  
  
1.  <span data-ttu-id="cae3e-208">Se si fa riferimento all'assembly o al progetto di attività `InvokePowerShell` da un altro progetto si verifica un errore di compilazione, pertanto potrebbe essere necessario aggiungere manualmente l'elemento `<SpecificVersion>True</SpecificVersion>` al file con estensione csproj del nuovo progetto sotto la riga che fa riferimento a `InvokePowerShell`.</span><span class="sxs-lookup"><span data-stu-id="cae3e-208">If referencing the `InvokePowerShell` activity assembly or project from another project results in a build error, you may need to manually add the `<SpecificVersion>True</SpecificVersion>` element to the .csproj file of the new project under the line that references `InvokePowerShell`.</span></span>  
  
2.  <span data-ttu-id="cae3e-209">Se non è installato Windows PowerShell, il seguente messaggio di errore viene visualizzato in Visual Studio non appena si aggiunge un `InvokePowerShell` attività su un flusso di lavoro:`Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span><span class="sxs-lookup"><span data-stu-id="cae3e-209">If Windows PowerShell is not installed, the following error message is displayed in Visual Studio as soon as you add an `InvokePowerShell` activity onto a workflow: `Workflow Designer encountered problems with your document. Could not load file or assembly ‘System.Management.Automation’ ... or one of its dependencies. The system cannot find the file specified.`</span></span>  
  
3.  <span data-ttu-id="cae3e-210">In Windows PowerShell 2.0, la chiamata a livello di codice di `$input.MoveNext()` non viene eseguita correttamente e gli script che usano `$input.MoveNext()` generano errori e risultati imprevisti.</span><span class="sxs-lookup"><span data-stu-id="cae3e-210">In Windows PowerShell 2.0, programmatically calling `$input.MoveNext()` fails and scripts using `$input.MoveNext()` produce unintended errors and results.</span></span> <span data-ttu-id="cae3e-211">Per risolvere questo problema, usare il verbo PowerShell `foreach` anziché chiamare `MoveNext()` quando si scorre una matrice.</span><span class="sxs-lookup"><span data-stu-id="cae3e-211">To work around this issue, consider using the PowerShell verb `foreach` instead of calling `MoveNext()` when iterating an array.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cae3e-212">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="cae3e-212">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cae3e-213">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="cae3e-213">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cae3e-214">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="cae3e-214">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cae3e-215">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="cae3e-215">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\PowerShell`