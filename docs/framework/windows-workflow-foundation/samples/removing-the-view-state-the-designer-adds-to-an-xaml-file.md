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
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a>Rimozione dello stato di visualizzazione della finestra di progettazione viene aggiunto a un file XAML

In questo esempio viene illustrato come creare una classe che deriva da <xref:System.Xaml.XamlWriter> e rimuove lo stato di visualizzazione da un file XAML. [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] scrive informazioni nel documento XAML, che è noto come stato di visualizzazione. Lo stato di visualizzazione si riferisce alle informazioni richieste in fase di progettazione, ad esempio il posizionamento del layout, che non sono richieste in fase di esecuzione. [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] inserisce queste informazioni nel documento XAML man mano che viene modificato. [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] scrive lo stato di visualizzazione nel file XAML con un attributo `mc:Ignorable`, in modo che queste informazioni non vengano caricate quando il runtime carica il file XAML. In questo esempio viene illustrato come creare una classe che rimuove tali informazioni sullo stato di visualizzazione durante l'elaborazione di nodi XAML.

## <a name="discussion"></a>Discussione

In questo esempio viene illustrato come creare un writer personalizzato.

Per compilare un writer XAML personalizzato, creare una classe che eredita da <xref:System.Xaml.XamlWriter>. Come i writer XAML sono spesso annidati, è tipico tenere traccia di un writer XAML "interno". Questi "interna" writer possono essere considerati il riferimento allo stack restante di writer XAML, consentendo di impostare più punti di ingresso per eseguire le operazioni e delegare quindi l'elaborazione per il resto dello stack.

In questo esempio sono presenti alcuni elementi di interesse. Uno consiste nel verificare se l'elemento scritto proviene da uno spazio dei nomi della finestra di progettazione. Si noti che consente di rimuovere anche l'uso di altri tipi dallo spazio dei nomi della finestra di progettazione in un flusso di lavoro.

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

Inoltre, crea uno stack di membri XAML usati mentre si attraversa il flusso del nodo. Il lavoro rimanente di questo esempio è ampiamente contenuto nel metodo `WriteStartMember`.

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

Metodi successivi consentono quindi di verificare se sono ancora contenuti in un contenitore dello stato di visualizzazione e, in tal caso, restituire, e non passare, il nodo dello stack del writer.

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

Per usare un writer XAML personalizzato, è necessario concatenarlo insieme in uno stack di writer XAML. Nel seguente esempio di codice viene mostrato come questo possa essere usato.

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a>Per usare questo esempio

1. Con Visual Studio 2010, aprire il file della soluzione Viewstatecleaningwriter.

2. Aprire un prompt dei comandi e passare alla directory in cui viene compilato ViewStageCleaningWriter.exe.

3. Eseguire ViewStateCleaningWriter.exe nel file Workflow1.xaml.

   La sintassi per il file eseguibile viene mostrata nell'esempio seguente.

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   Ciò produce un file XAML per \[FileOut], che dispone di tutte le informazioni sullo stato di visualizzazione rimosse.

> [!NOTE]
> Per un flusso di lavoro <xref:System.Activities.Statements.Sequence>, vengono rimossi diversi suggerimenti di virtualizzazione determinando così il ricalcolo del layout da parte della finestra di progettazione al successivo caricamento. Quando si usa questo esempio per un oggetto <xref:System.Activities.Statements.Flowchart>, tutte le informazioni relative al posizionamento e al routing linea vengono rimosse e, al successivo caricamento nella finestra di progettazione, tutte le attività sono in pila sul lato sinistro dello schermo.

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a>Per creare un file XAML di esempio da usare con questo esempio

1. Open Visual Studio 2010.

2. Creare una nuova applicazione console flusso di lavoro.

3. Trascinare e rilasciare alcune attività nell'area di disegno

4. Salvare il file XAML del flusso di lavoro.

5. Esaminare il file XAML per visualizzare le proprietà collegate dello stato di visualizzazione.

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`