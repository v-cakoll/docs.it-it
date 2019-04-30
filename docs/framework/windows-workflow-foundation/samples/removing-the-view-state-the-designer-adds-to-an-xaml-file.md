---
title: Rimozione dello stato di visualizzazione della finestra di progettazione viene aggiunto a un file XAML - WF
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: 71a2aadeefd53b391f4589ed9dc32d9cd6e3183a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004939"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="21d49-102">Rimozione dello stato di visualizzazione della finestra di progettazione viene aggiunto a un file XAML</span><span class="sxs-lookup"><span data-stu-id="21d49-102">Removing the view state the designer adds to an XAML file</span></span>

<span data-ttu-id="21d49-103">In questo esempio viene illustrato come creare una classe che deriva da <xref:System.Xaml.XamlWriter> e rimuove lo stato di visualizzazione da un file XAML.</span><span class="sxs-lookup"><span data-stu-id="21d49-103">This sample demonstrates how to create a class that derives from <xref:System.Xaml.XamlWriter> and removes view state from a XAML file.</span></span> [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] <span data-ttu-id="21d49-104">scrive informazioni nel documento XAML, che è noto come stato di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="21d49-104">writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="21d49-105">Lo stato di visualizzazione si riferisce alle informazioni richieste in fase di progettazione, ad esempio il posizionamento del layout, che non sono richieste in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="21d49-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="21d49-106">inserisce queste informazioni nel documento XAML man mano che viene modificato.</span><span class="sxs-lookup"><span data-stu-id="21d49-106">inserts this information into the XAML document as it is edited.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="21d49-107">scrive lo stato di visualizzazione nel file XAML con un attributo `mc:Ignorable`, in modo che queste informazioni non vengano caricate quando il runtime carica il file XAML.</span><span class="sxs-lookup"><span data-stu-id="21d49-107">writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="21d49-108">In questo esempio viene illustrato come creare una classe che rimuove tali informazioni sullo stato di visualizzazione durante l'elaborazione di nodi XAML.</span><span class="sxs-lookup"><span data-stu-id="21d49-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>

## <a name="discussion"></a><span data-ttu-id="21d49-109">Discussione</span><span class="sxs-lookup"><span data-stu-id="21d49-109">Discussion</span></span>

<span data-ttu-id="21d49-110">In questo esempio viene illustrato come creare un writer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="21d49-110">This sample demonstrates how to create a custom writer.</span></span>

<span data-ttu-id="21d49-111">Per compilare un writer XAML personalizzato, creare una classe che eredita da <xref:System.Xaml.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="21d49-111">To build a custom XAML writer, create a class that inherits from <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="21d49-112">Come i writer XAML sono spesso annidati, è tipico tenere traccia di un writer XAML "interno".</span><span class="sxs-lookup"><span data-stu-id="21d49-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="21d49-113">Questi "interna" writer possono essere considerati il riferimento allo stack restante di writer XAML, consentendo di impostare più punti di ingresso per eseguire le operazioni e delegare quindi l'elaborazione per il resto dello stack.</span><span class="sxs-lookup"><span data-stu-id="21d49-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>

<span data-ttu-id="21d49-114">In questo esempio sono presenti alcuni elementi di interesse.</span><span class="sxs-lookup"><span data-stu-id="21d49-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="21d49-115">Uno consiste nel verificare se l'elemento scritto proviene da uno spazio dei nomi della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="21d49-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="21d49-116">Si noti che consente di rimuovere anche l'uso di altri tipi dallo spazio dei nomi della finestra di progettazione in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="21d49-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>

```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)
{
    return xamlMember.IsAttachable &&
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);
}

const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.
public ViewStateCleaningWriter(XamlWriter innerWriter)
{
    this.InnerWriter = innerWriter;
    this.MemberStack = new Stack<XamlMember>();
}

XamlWriter InnerWriter {get; set; }
Stack<XamlMember> MemberStack {get; set; }
```

<span data-ttu-id="21d49-117">Inoltre, crea uno stack di membri XAML usati mentre si attraversa il flusso del nodo.</span><span class="sxs-lookup"><span data-stu-id="21d49-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="21d49-118">Il lavoro rimanente di questo esempio è ampiamente contenuto nel metodo `WriteStartMember`.</span><span class="sxs-lookup"><span data-stu-id="21d49-118">The remaining work of this sample is largely contained in the `WriteStartMember` method.</span></span>

```csharp
public override void WriteStartMember(XamlMember xamlMember)
{
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))
    {
        m_attachedPropertyDepth++;
    }

    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteStartMember(xamlMember);
}
```

<span data-ttu-id="21d49-119">Metodi successivi consentono quindi di verificare se sono ancora contenuti in un contenitore dello stato di visualizzazione e, in tal caso, restituire, e non passare, il nodo dello stack del writer.</span><span class="sxs-lookup"><span data-stu-id="21d49-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>

```csharp
public override void WriteValue(Object value)
{
    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteValue(value);
}
```

<span data-ttu-id="21d49-120">Per usare un writer XAML personalizzato, è necessario concatenarlo insieme in uno stack di writer XAML.</span><span class="sxs-lookup"><span data-stu-id="21d49-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="21d49-121">Nel seguente esempio di codice viene mostrato come questo possa essere usato.</span><span class="sxs-lookup"><span data-stu-id="21d49-121">The following code shows how this can be used.</span></span>

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a><span data-ttu-id="21d49-122">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="21d49-122">To use this sample</span></span>

1. <span data-ttu-id="21d49-123">Con Visual Studio 2010, aprire il file della soluzione Viewstatecleaningwriter.</span><span class="sxs-lookup"><span data-stu-id="21d49-123">Using Visual Studio 2010, open the ViewStateCleaningWriter.sln solution file.</span></span>

2. <span data-ttu-id="21d49-124">Aprire un prompt dei comandi e passare alla directory in cui viene compilato ViewStageCleaningWriter.exe.</span><span class="sxs-lookup"><span data-stu-id="21d49-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>

3. <span data-ttu-id="21d49-125">Eseguire ViewStateCleaningWriter.exe nel file Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="21d49-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>

   <span data-ttu-id="21d49-126">La sintassi per il file eseguibile viene mostrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="21d49-126">The syntax for the executable is shown in the following example.</span></span>

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   <span data-ttu-id="21d49-127">Ciò produce un file XAML per \[FileOut], che dispone di tutte le informazioni sullo stato di visualizzazione rimosse.</span><span class="sxs-lookup"><span data-stu-id="21d49-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>

> [!NOTE]
> <span data-ttu-id="21d49-128">Per un flusso di lavoro <xref:System.Activities.Statements.Sequence>, vengono rimossi diversi suggerimenti di virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="21d49-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="21d49-129">determinando così il ricalcolo del layout da parte della finestra di progettazione al successivo caricamento.</span><span class="sxs-lookup"><span data-stu-id="21d49-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="21d49-130">Quando si usa questo esempio per un oggetto <xref:System.Activities.Statements.Flowchart>, tutte le informazioni relative al posizionamento e al routing linea vengono rimosse e, al successivo caricamento nella finestra di progettazione, tutte le attività sono in pila sul lato sinistro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="21d49-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="21d49-131">Per creare un file XAML di esempio da usare con questo esempio</span><span class="sxs-lookup"><span data-stu-id="21d49-131">To create a sample XAML file for use with this sample</span></span>

1. <span data-ttu-id="21d49-132">Open Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="21d49-132">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="21d49-133">Creare una nuova applicazione console flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="21d49-133">Create a new Workflow Console Application.</span></span>

3. <span data-ttu-id="21d49-134">Trascinare e rilasciare alcune attività nell'area di disegno</span><span class="sxs-lookup"><span data-stu-id="21d49-134">Drag and drop a few activities onto the canvas</span></span>

4. <span data-ttu-id="21d49-135">Salvare il file XAML del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="21d49-135">Save the workflow XAML file.</span></span>

5. <span data-ttu-id="21d49-136">Esaminare il file XAML per visualizzare le proprietà collegate dello stato di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="21d49-136">Inspect the XAML file to see the view state attached properties.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21d49-137">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="21d49-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="21d49-138">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="21d49-138">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="21d49-139">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="21d49-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="21d49-140">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="21d49-140">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`