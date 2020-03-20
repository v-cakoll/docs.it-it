---
title: Segnalibri - WF
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: c5bd8130ee623599e80014777baf92986c3b6969
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183016"
---
# <a name="bookmarks"></a><span data-ttu-id="36bef-102">Segnalibri</span><span class="sxs-lookup"><span data-stu-id="36bef-102">Bookmarks</span></span>
<span data-ttu-id="36bef-103">I segnalibri rappresentano il meccanismo che consente a un'attività di attendere passivamente l'input senza mantenere un thread del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36bef-103">Bookmarks are the mechanism that enables an activity to passively wait for input without holding onto a workflow thread.</span></span> <span data-ttu-id="36bef-104">Quando un'attività segnala che sta attendendo stimoli, può creare un segnalibro.</span><span class="sxs-lookup"><span data-stu-id="36bef-104">When an activity signals that it is waiting for stimulus, it can create a bookmark.</span></span> <span data-ttu-id="36bef-105">Ciò indica al runtime che l'esecuzione dell'attività non deve essere considerata completa anche quando viene restituito il metodo attualmente in esecuzione (che ha creato l'oggetto <xref:System.Activities.Bookmark>).</span><span class="sxs-lookup"><span data-stu-id="36bef-105">This indicates to the runtime that the activity’s execution should not be considered complete even when the currently executing method (which created the <xref:System.Activities.Bookmark>) returns.</span></span>  
  
## <a name="bookmark-basics"></a><span data-ttu-id="36bef-106">Informazioni introduttive sul segnalibro</span><span class="sxs-lookup"><span data-stu-id="36bef-106">Bookmark Basics</span></span>  
 <span data-ttu-id="36bef-107">Un oggetto <xref:System.Activities.Bookmark> rappresenta un punto in cui l'esecuzione può essere ripresa (e attraverso cui è possibile recapitare l'input) all'interno di un'istanza del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="36bef-107">A <xref:System.Activities.Bookmark> represents a point at which execution can be resumed (and through which input can be delivered) within a workflow instance.</span></span> <span data-ttu-id="36bef-108">In genere, viene assegnato un nome a un oggetto <xref:System.Activities.Bookmark> e il codice esterno (host o estensione) è responsabile della ripresa del segnalibro con i dati attinenti.</span><span class="sxs-lookup"><span data-stu-id="36bef-108">Typically, a <xref:System.Activities.Bookmark> is given a name and external (host or extension) code is responsible for resuming the bookmark with relevant data.</span></span> <span data-ttu-id="36bef-109">Quando un oggetto <xref:System.Activities.Bookmark> viene ripreso, l'esecuzione del flusso di lavoro pianifica il delegato <xref:System.Activities.BookmarkCallback> associato a tale oggetto <xref:System.Activities.Bookmark> al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="36bef-109">When a <xref:System.Activities.Bookmark> is resumed, the workflow runtime schedules the <xref:System.Activities.BookmarkCallback> delegate that was associated with that <xref:System.Activities.Bookmark> at the time of its creation.</span></span>  
  
## <a name="bookmark-options"></a><span data-ttu-id="36bef-110">Opzioni del segnalibro</span><span class="sxs-lookup"><span data-stu-id="36bef-110">Bookmark Options</span></span>  
 <span data-ttu-id="36bef-111">La classe <xref:System.Activities.BookmarkOptions> specifica il tipo di oggetto <xref:System.Activities.Bookmark> in corso di creazione.</span><span class="sxs-lookup"><span data-stu-id="36bef-111">The <xref:System.Activities.BookmarkOptions> class specifies the type of <xref:System.Activities.Bookmark> being created.</span></span> <span data-ttu-id="36bef-112">I valori possibili che non si escludono a vicenda sono <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume> e <xref:System.Activities.BookmarkOptions.NonBlocking>.</span><span class="sxs-lookup"><span data-stu-id="36bef-112">The possible non mutually-exclusive values are <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume>, and <xref:System.Activities.BookmarkOptions.NonBlocking>.</span></span> <span data-ttu-id="36bef-113">Usare il valore <xref:System.Activities.BookmarkOptions.None>, ovvero l'impostazione predefinita, quando si crea un oggetto <xref:System.Activities.Bookmark> che si presume debba essere ripreso una sola volta.</span><span class="sxs-lookup"><span data-stu-id="36bef-113">Use <xref:System.Activities.BookmarkOptions.None>, the default, when creating a <xref:System.Activities.Bookmark> that is expected to be resumed exactly once.</span></span> <span data-ttu-id="36bef-114">Usare il valore <xref:System.Activities.BookmarkOptions.MultipleResume> quando si crea un oggetto <xref:System.Activities.Bookmark> che può essere ripreso più volte.</span><span class="sxs-lookup"><span data-stu-id="36bef-114">Use <xref:System.Activities.BookmarkOptions.MultipleResume> when creating a <xref:System.Activities.Bookmark> that can be resumed multiple times.</span></span> <span data-ttu-id="36bef-115">Usare un valore <xref:System.Activities.BookmarkOptions.NonBlocking> quando si crea un oggetto <xref:System.Activities.Bookmark> che potrebbe non essere mai ripreso.</span><span class="sxs-lookup"><span data-stu-id="36bef-115">Use <xref:System.Activities.BookmarkOptions.NonBlocking> when creating a <xref:System.Activities.Bookmark> that might never be resumed.</span></span> <span data-ttu-id="36bef-116">A differenza dei segnalibri creati usando l'oggetto <xref:System.Activities.BookmarkOptions> predefinito, i segnalibri <xref:System.Activities.BookmarkOptions.NonBlocking> non impediscono il completamento di un'attività.</span><span class="sxs-lookup"><span data-stu-id="36bef-116">Unlike bookmarks created using the default <xref:System.Activities.BookmarkOptions>, <xref:System.Activities.BookmarkOptions.NonBlocking> bookmarks do not prevent an activity from completing.</span></span>  
  
## <a name="bookmark-resumption"></a><span data-ttu-id="36bef-117">Ripresa del segnalibro</span><span class="sxs-lookup"><span data-stu-id="36bef-117">Bookmark Resumption</span></span>  
 <span data-ttu-id="36bef-118">I segnalibri possono essere ripresi dal codice all'esterno di un flusso di lavoro usando uno degli overload <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>.</span><span class="sxs-lookup"><span data-stu-id="36bef-118">Bookmarks can be resumed by code outside of a workflow using one of the <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> overloads.</span></span> <span data-ttu-id="36bef-119">In questo esempio viene creata un'attività `ReadLine`.</span><span class="sxs-lookup"><span data-stu-id="36bef-119">In this example, a `ReadLine` activity is created.</span></span> <span data-ttu-id="36bef-120">In caso di esecuzione, l'attività `ReadLine` crea un oggetto <xref:System.Activities.Bookmark>, registra un callback, quindi attende la ripresa dell'oggetto <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="36bef-120">When executed, the `ReadLine` activity creates a <xref:System.Activities.Bookmark>, registers a callback, and then waits for the <xref:System.Activities.Bookmark> to be resumed.</span></span> <span data-ttu-id="36bef-121">Una volta ripresa, l'attività `ReadLine` assegna i dati passati con l'oggetto <xref:System.Activities.Bookmark> al relativo argomento <xref:System.Activities.Activity%601.Result%2A>.</span><span class="sxs-lookup"><span data-stu-id="36bef-121">When it is resumed, the `ReadLine` activity assigns the data that was passed with the <xref:System.Activities.Bookmark> to its <xref:System.Activities.Activity%601.Result%2A> argument.</span></span>  
  
```csharp  
public sealed class ReadLine : NativeActivity<string>  
{  
    [RequiredArgument]  
    public  InArgument<string> BookmarkName { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        // Create a Bookmark and wait for it to be resumed.  
        context.CreateBookmark(BookmarkName.Get(context),
            new BookmarkCallback(OnResumeBookmark));  
    }  
  
    // NativeActivity derived activities that do asynchronous operations by calling
    // one of the CreateBookmark overloads defined on System.Activities.NativeActivityContext
    // must override the CanInduceIdle property and return true.  
    protected override bool CanInduceIdle  
    {  
        get { return true; }  
    }  
  
    public void OnResumeBookmark(NativeActivityContext context, Bookmark bookmark, object obj)  
    {  
        // When the Bookmark is resumed, assign its value to  
        // the Result argument.  
        Result.Set(context, (string)obj);  
    }  
}  
```  
  
 <span data-ttu-id="36bef-122">In questo esempio viene creato un flusso di lavoro che usa l'attività `ReadLine` per rilevare il nome dell'utente e visualizzarlo nella finestra della console.</span><span class="sxs-lookup"><span data-stu-id="36bef-122">In this example, a workflow is created that uses the `ReadLine` activity to gather the user’s name and display it to the console window.</span></span> <span data-ttu-id="36bef-123">L'applicazione host esegue il lavoro effettivo di rilevamento dell'input e lo passa al flusso di lavoro riprendendo l'oggetto <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="36bef-123">The host application performs the actual work of gathering the input and passes it to the workflow by resuming the <xref:System.Activities.Bookmark>.</span></span>  
  
```csharp  
Variable<string> name = new Variable<string>  
{  
    Name = "name"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        name  
    },  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "What is your name?"  
        },  
        new ReadLine()  
        {  
            BookmarkName = "UserName",  
            Result = name  
        },  
        new WriteLine()  
        {  
            Text = new InArgument<string>((env) => "Hello, " + name.Get(env))  
        }  
    }  
};  
  
AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
// Create the WorkflowApplication using the desired  
// workflow definition.  
WorkflowApplication wfApp = new WorkflowApplication(wf);  
  
// Handle the desired lifecycle events.  
wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
{  
    // Signal the host that the workflow is complete.  
    syncEvent.Set();  
};  
  
// Start the workflow.  
wfApp.Run();  
  
// Collect the user's name and resume the bookmark.  
// Bookmark resumption only occurs when the workflow  
// is idle. If a call to ResumeBookmark is made and the workflow  
// is not idle, ResumeBookmark blocks until the workflow becomes  
// idle before resuming the bookmark.  
wfApp.ResumeBookmark("UserName", Console.ReadLine());  
  
// Wait for Completed to arrive and signal that  
// the workflow is complete.  
syncEvent.WaitOne();  
```  
  
 <span data-ttu-id="36bef-124">Quando l'attività `ReadLine` viene eseguita, crea un oggetto <xref:System.Activities.Bookmark> denominato `UserName` e attende la ripresa del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="36bef-124">When the `ReadLine` activity is executed, it creates a <xref:System.Activities.Bookmark> named `UserName` and then waits for the bookmark to be resumed.</span></span> <span data-ttu-id="36bef-125">L'host raccoglie i dati desiderati, quindi riprende l'oggetto <xref:System.Activities.Bookmark>.</span><span class="sxs-lookup"><span data-stu-id="36bef-125">The host collects the desired data and then resumes the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="36bef-126">Il flusso di lavoro viene ripreso, ne viene visualizzato il nome, quindi viene completato.</span><span class="sxs-lookup"><span data-stu-id="36bef-126">The workflow resumes, displays the name, and then completes.</span></span> <span data-ttu-id="36bef-127">Si noti che non è necessario alcun codice di sincronizzazione per la ripresa del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="36bef-127">Note that no synchronization code is required with regard to resuming the bookmark.</span></span> <span data-ttu-id="36bef-128">Un oggetto <xref:System.Activities.Bookmark> può essere ripreso solo quando il flusso di lavoro è inattivo e, in caso contrario, la chiamata al metodo <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> viene bloccata finché il flusso di lavoro non diventa inattivo.</span><span class="sxs-lookup"><span data-stu-id="36bef-128">A <xref:System.Activities.Bookmark> can only be resumed when the workflow is idle, and if the workflow is not idle, the call to <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> blocks until the workflow becomes idle.</span></span>  
  
## <a name="bookmark-resumption-result"></a><span data-ttu-id="36bef-129">Risultato della ripresa del segnalibro</span><span class="sxs-lookup"><span data-stu-id="36bef-129">Bookmark Resumption Result</span></span>  
 <span data-ttu-id="36bef-130">Il metodo <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> restituisce un valore dell'enumerazione <xref:System.Activities.BookmarkResumptionResult> per indicare i risultati della richiesta di ripresa del segnalibro.</span><span class="sxs-lookup"><span data-stu-id="36bef-130"><xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> returns a <xref:System.Activities.BookmarkResumptionResult> enumeration value to indicate the results of the bookmark resumption request.</span></span> <span data-ttu-id="36bef-131">I possibili valori restituiti sono <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady> e <xref:System.Activities.BookmarkResumptionResult.NotFound>.</span><span class="sxs-lookup"><span data-stu-id="36bef-131">The possible return values are <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady>, and <xref:System.Activities.BookmarkResumptionResult.NotFound>.</span></span> <span data-ttu-id="36bef-132">Gli host e le estensioni possono usare questo valore per stabilire come procedere.</span><span class="sxs-lookup"><span data-stu-id="36bef-132">Hosts and extensions can use this value to determine how to proceed.</span></span>
