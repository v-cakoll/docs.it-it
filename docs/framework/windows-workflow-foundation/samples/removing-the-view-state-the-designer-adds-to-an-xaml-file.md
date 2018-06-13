---
title: Rimozione dello stato di visualizzazione della finestra di progettazione per l'aggiunta a un file XAML
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: f63723c29c76854602308ba3e8d7e6dd65d9fb94
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517836"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="8c537-102">Rimozione dello stato di visualizzazione della finestra di progettazione per l'aggiunta a un file XAML</span><span class="sxs-lookup"><span data-stu-id="8c537-102">Removing the View State the Designer Adds to an XAML File</span></span>
<span data-ttu-id="8c537-103">In questo esempio viene illustrato come creare una classe che deriva da <xref:System.Windows.Markup.XamlWriter> e rimuove lo stato di visualizzazione da un file XAML.</span><span class="sxs-lookup"><span data-stu-id="8c537-103">This sample demonstrates how to create a class that derives from <xref:System.Windows.Markup.XamlWriter> and removes view state from a XAML file.</span></span> [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)]<span data-ttu-id="8c537-104"> scrive informazioni nel documento XAML, che è noto come stato di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c537-104"> writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="8c537-105">Lo stato di visualizzazione si riferisce alle informazioni richieste in fase di progettazione, ad esempio il posizionamento del layout, che non sono richieste in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8c537-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]<span data-ttu-id="8c537-106"> inserisce queste informazioni nel documento XAML man mano che viene modificato.</span><span class="sxs-lookup"><span data-stu-id="8c537-106"> inserts this information into the XAML document as it is edited.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)]<span data-ttu-id="8c537-107"> scrive lo stato di visualizzazione nel file XAML con un attributo `mc:Ignorable`, in modo che queste informazioni non vengano caricate quando il runtime carica il file XAML.</span><span class="sxs-lookup"><span data-stu-id="8c537-107"> writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="8c537-108">In questo esempio viene illustrato come creare una classe che rimuove tali informazioni sullo stato di visualizzazione durante l'elaborazione di nodi XAML.</span><span class="sxs-lookup"><span data-stu-id="8c537-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="8c537-109">Discussione</span><span class="sxs-lookup"><span data-stu-id="8c537-109">Discussion</span></span>  
 <span data-ttu-id="8c537-110">In questo esempio viene illustrato come creare un writer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="8c537-110">This sample demonstrates how to create a custom writer.</span></span>  
  
 <span data-ttu-id="8c537-111">Per compilare un writer XAML personalizzato, creare una classe che eredita da <xref:System.Windows.Markup.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="8c537-111">To build a custom XAML writer, create a class that inherits from <xref:System.Windows.Markup.XamlWriter>.</span></span> <span data-ttu-id="8c537-112">I writer XAML sono spesso annidati, è tipico tenere traccia di un writer XAML "interno".</span><span class="sxs-lookup"><span data-stu-id="8c537-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="8c537-113">Questi "interna ' writer possono essere considerati come riferimento allo stack restante di writer XAML, consentendo di disporre di più punti di ingresso per eseguire le operazioni e delegare quindi l'elaborazione al resto dello stack.</span><span class="sxs-lookup"><span data-stu-id="8c537-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>  
  
 <span data-ttu-id="8c537-114">In questo esempio sono presenti alcuni elementi di interesse.</span><span class="sxs-lookup"><span data-stu-id="8c537-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="8c537-115">Uno consiste nel verificare se l'elemento scritto proviene da uno spazio dei nomi della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="8c537-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="8c537-116">Si noti che consente di rimuovere anche l'uso di altri tipi dallo spazio dei nomi della finestra di progettazione in un flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c537-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>  
  
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
  
 <span data-ttu-id="8c537-117">Inoltre, crea uno stack di membri XAML usati mentre si attraversa il flusso del nodo.</span><span class="sxs-lookup"><span data-stu-id="8c537-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="8c537-118">Il lavoro rimanente di questo esempio è ampiamente contenuto nel <!--zz  <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>--> `System.Windows.Markup.XamlWriter.WriteStartMember` metodo.</span><span class="sxs-lookup"><span data-stu-id="8c537-118">The remaining work of this sample is largely contained in the <!--zz  <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>--> `System.Windows.Markup.XamlWriter.WriteStartMember` method.</span></span>  
  
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
  
 <span data-ttu-id="8c537-119">Metodi successivi consentono quindi di verificare se sono ancora contenuti in un contenitore dello stato di visualizzazione e, in tal caso, restituire, e non passare, il nodo dello stack del writer.</span><span class="sxs-lookup"><span data-stu-id="8c537-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>  
  
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
  
 <span data-ttu-id="8c537-120">Per usare un writer XAML personalizzato, è necessario concatenarlo insieme in uno stack di writer XAML.</span><span class="sxs-lookup"><span data-stu-id="8c537-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="8c537-121">Nel seguente esempio di codice viene mostrato come questo possa essere usato.</span><span class="sxs-lookup"><span data-stu-id="8c537-121">The following code shows how this can be used.</span></span>  
  
```csharp 
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };  
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);  
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());  
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="8c537-122">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="8c537-122">To use this sample</span></span>  
  
1. <span data-ttu-id="8c537-123">In [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] aprire il file della soluzione ViewStateCleaningWriter.sln.</span><span class="sxs-lookup"><span data-stu-id="8c537-123">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ViewStateCleaningWriter.sln solution file.</span></span>  
  
2. <span data-ttu-id="8c537-124">Aprire un prompt dei comandi e passare alla directory in cui viene compilato ViewStageCleaningWriter.exe.</span><span class="sxs-lookup"><span data-stu-id="8c537-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>  
  
3. <span data-ttu-id="8c537-125">Eseguire ViewStateCleaningWriter.exe nel file Workflow1.xaml.</span><span class="sxs-lookup"><span data-stu-id="8c537-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>  

   <span data-ttu-id="8c537-126">La sintassi per il file eseguibile viene mostrata nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="8c537-126">The syntax for the executable is shown in the following example.</span></span>  
  
   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```
   
   <span data-ttu-id="8c537-127">Restituisce un file XAML in \[outfile], che contiene tutte le informazioni sullo stato di visualizzazione rimosse.</span><span class="sxs-lookup"><span data-stu-id="8c537-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c537-128">Per un flusso di lavoro <xref:System.Activities.Statements.Sequence>, vengono rimossi diversi suggerimenti di virtualizzazione</span><span class="sxs-lookup"><span data-stu-id="8c537-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="8c537-129">determinando così il ricalcolo del layout da parte della finestra di progettazione al successivo caricamento.</span><span class="sxs-lookup"><span data-stu-id="8c537-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="8c537-130">Quando si usa questo esempio per un oggetto <xref:System.Activities.Statements.Flowchart>, tutte le informazioni relative al posizionamento e al routing linea vengono rimosse e, al successivo caricamento nella finestra di progettazione, tutte le attività sono in pila sul lato sinistro dello schermo.</span><span class="sxs-lookup"><span data-stu-id="8c537-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>  
  
#### <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="8c537-131">Per creare un file XAML di esempio da usare con questo esempio</span><span class="sxs-lookup"><span data-stu-id="8c537-131">To create a sample XAML file for use with this sample</span></span>  
  
1. <span data-ttu-id="8c537-132">Aprire [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8c537-132">Open [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2. <span data-ttu-id="8c537-133">Creare una nuova applicazione console flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c537-133">Create a new Workflow Console Application.</span></span>  
  
3. <span data-ttu-id="8c537-134">Trascinare alcune attività sull'area di disegno</span><span class="sxs-lookup"><span data-stu-id="8c537-134">Drag and drop a few activities onto the canvas</span></span>  
  
4. <span data-ttu-id="8c537-135">Salvare il file XAML del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="8c537-135">Save the workflow XAML file.</span></span>  
  
5. <span data-ttu-id="8c537-136">Esaminare il file XAML per visualizzare le proprietà collegate dello stato di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c537-136">Inspect the XAML file to see the view state attached properties.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8c537-137">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="8c537-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8c537-138">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="8c537-138">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="8c537-139">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="8c537-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8c537-140">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="8c537-140">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`
