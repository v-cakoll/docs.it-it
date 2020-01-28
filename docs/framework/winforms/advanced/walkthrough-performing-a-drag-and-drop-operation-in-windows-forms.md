---
title: "Procedura dettagliata: eseguire un'operazione di trascinamento della selezione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 265e6d4f9e3370d28a18b86dea983bb0b556be41
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746800"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="431a5-102">Procedura dettagliata: Esecuzione di un'operazione di trascinamento in Windows Form</span><span class="sxs-lookup"><span data-stu-id="431a5-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="431a5-103">Per eseguire operazioni di trascinamento della selezione nelle applicazioni basate su Windows, è necessario gestire una serie di eventi, in particolare gli eventi <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>e <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="431a5-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="431a5-104">Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="431a5-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="431a5-105">Trascinamento di dati</span><span class="sxs-lookup"><span data-stu-id="431a5-105">Dragging Data</span></span>  
 <span data-ttu-id="431a5-106">Tutte le operazioni di trascinamento della selezione iniziano con il trascinamento.</span><span class="sxs-lookup"><span data-stu-id="431a5-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="431a5-107">La funzionalità per consentire la raccolta dei dati quando inizia il trascinamento è implementata nel metodo <xref:System.Windows.Forms.Control.DoDragDrop%2A>.</span><span class="sxs-lookup"><span data-stu-id="431a5-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="431a5-108">Nell'esempio seguente viene usato l'evento <xref:System.Windows.Forms.Control.MouseDown> per avviare l'operazione di trascinamento perché è il più intuitivo (la maggior parte delle operazioni di trascinamento della selezione inizia con il pulsante del mouse premuto).</span><span class="sxs-lookup"><span data-stu-id="431a5-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="431a5-109">Tenere tuttavia presente che, per avviare una procedura di trascinamento della selezione, può essere usato qualsiasi evento.</span><span class="sxs-lookup"><span data-stu-id="431a5-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="431a5-110">Alcuni controlli hanno eventi specifici per il trascinamento.</span><span class="sxs-lookup"><span data-stu-id="431a5-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="431a5-111">I controlli <xref:System.Windows.Forms.ListView> e <xref:System.Windows.Forms.TreeView>, ad esempio, hanno un evento <xref:System.Windows.Forms.TreeView.ItemDrag>.</span><span class="sxs-lookup"><span data-stu-id="431a5-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="431a5-112">Per avviare un'operazione di trascinamento</span><span class="sxs-lookup"><span data-stu-id="431a5-112">To start a drag operation</span></span>  
  
1. <span data-ttu-id="431a5-113">Nell'evento <xref:System.Windows.Forms.Control.MouseDown> per il controllo in cui inizierà il trascinamento, utilizzare il metodo `DoDragDrop` per impostare i dati da trascinare e il trascinamento dell'effetto consentito avrà.</span><span class="sxs-lookup"><span data-stu-id="431a5-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="431a5-114">Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="431a5-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="431a5-115">L'esempio seguente illustra come avviare un'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="431a5-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="431a5-116">Il controllo in cui inizia il trascinamento è un controllo <xref:System.Windows.Forms.Button>, i dati trascinati sono la stringa che rappresenta la proprietà <xref:System.Windows.Forms.Control.Text%2A> del controllo <xref:System.Windows.Forms.Button> e gli effetti consentiti vengono copiati o spostati.</span><span class="sxs-lookup"><span data-stu-id="431a5-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,   
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |   
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="431a5-117">I dati possono essere usati come parametro nel metodo `DoDragDrop`; Nell'esempio precedente è stata usata la proprietà <xref:System.Windows.Forms.Control.Text%2A> del controllo <xref:System.Windows.Forms.Button> (anziché impostare come hardcoded un valore o recuperare i dati da un set di dati) perché la proprietà era correlata al percorso da cui viene trascinato (il controllo <xref:System.Windows.Forms.Button>).</span><span class="sxs-lookup"><span data-stu-id="431a5-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="431a5-118">Tenerlo presente quando si incorporano operazioni di trascinamento della selezione nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="431a5-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="431a5-119">Mentre è attiva un'operazione di trascinamento, è possibile gestire l'evento <xref:System.Windows.Forms.Control.QueryContinueDrag>, che "chiede l'autorizzazione" del sistema per continuare l'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="431a5-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="431a5-120">Quando si gestisce questo metodo, è anche il punto appropriato per chiamare i metodi che avranno effetto sull'operazione di trascinamento, ad esempio l'espansione di un <xref:System.Windows.Forms.TreeNode> in un controllo <xref:System.Windows.Forms.TreeView> quando il cursore viene spostato su di esso.</span><span class="sxs-lookup"><span data-stu-id="431a5-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="431a5-121">Rilascio dei dati</span><span class="sxs-lookup"><span data-stu-id="431a5-121">Dropping Data</span></span>  
 <span data-ttu-id="431a5-122">Dopo avere iniziato a trascinare i dati da una posizione in un Windows Form o in un controllo, sarà ovviamente necessario rilasciarli.</span><span class="sxs-lookup"><span data-stu-id="431a5-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="431a5-123">Il cursore cambia quando attraversa un'area di un form o di un controllo configurata correttamente per il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="431a5-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="431a5-124">È possibile fare in modo che qualsiasi area all'interno di un Windows Form o di un controllo accetti i dati rimossi impostando la proprietà <xref:System.Windows.Forms.Control.AllowDrop%2A> e gestendo gli eventi <xref:System.Windows.Forms.Control.DragEnter> e <xref:System.Windows.Forms.Control.DragDrop>.</span><span class="sxs-lookup"><span data-stu-id="431a5-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="431a5-125">Per eseguire un rilascio</span><span class="sxs-lookup"><span data-stu-id="431a5-125">To perform a drop</span></span>  
  
1. <span data-ttu-id="431a5-126">Impostare la proprietà <xref:System.Windows.Forms.Control.AllowDrop%2A> su true.</span><span class="sxs-lookup"><span data-stu-id="431a5-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="431a5-127">Nell'evento `DragEnter` per il controllo in cui si verificherà il rilascio, assicurarsi che i dati trascinati siano di tipo accettabile (in questo caso, <xref:System.Windows.Forms.Control.Text%2A>).</span><span class="sxs-lookup"><span data-stu-id="431a5-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="431a5-128">Il codice imposta quindi l'effetto che si verificherà quando il rilascio viene eseguito in un valore nell'enumerazione <xref:System.Windows.Forms.DragDropEffects>.</span><span class="sxs-lookup"><span data-stu-id="431a5-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="431a5-129">Per ulteriori informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="431a5-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))   
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="431a5-130">È possibile definire <xref:System.Windows.Forms.DataFormats> personalizzati specificando un oggetto personalizzato come parametro di <xref:System.Object> del metodo <xref:System.Windows.Forms.DataObject.SetData%2A>.</span><span class="sxs-lookup"><span data-stu-id="431a5-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="431a5-131">Assicurarsi, in tal caso, che l'oggetto specificato sia serializzabile.</span><span class="sxs-lookup"><span data-stu-id="431a5-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="431a5-132">Per ulteriori informazioni, vedere <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="431a5-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="431a5-133">Nell'evento <xref:System.Windows.Forms.Control.DragDrop> per il controllo in cui si verificherà il rilascio, utilizzare il metodo <xref:System.Windows.Forms.DataObject.GetData%2A> per recuperare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="431a5-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="431a5-134">Per ulteriori informazioni, vedere <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="431a5-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="431a5-135">Nell'esempio seguente un controllo <xref:System.Windows.Forms.TextBox> è il controllo da trascinare (in cui si verificherà il rilascio).</span><span class="sxs-lookup"><span data-stu-id="431a5-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="431a5-136">Il codice imposta la proprietà <xref:System.Windows.Forms.Control.Text%2A> del controllo <xref:System.Windows.Forms.TextBox> uguale ai dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="431a5-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,   
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="431a5-137">Inoltre, è possibile utilizzare la proprietà <xref:System.Windows.Forms.DragEventArgs.KeyState%2A>, in modo che, a seconda delle chiavi deselezionate durante l'operazione di trascinamento della selezione, si verifichino determinati effetti, ad esempio è standard copiare i dati trascinati quando viene premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="431a5-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431a5-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="431a5-138">See also</span></span>

- [<span data-ttu-id="431a5-139">Procedura: Aggiungere dati agli Appunti</span><span class="sxs-lookup"><span data-stu-id="431a5-139">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="431a5-140">Procedura: Recuperare dati dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="431a5-140">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- <span data-ttu-id="431a5-141">[Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)</span><span class="sxs-lookup"><span data-stu-id="431a5-141">[Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md)</span></span>
