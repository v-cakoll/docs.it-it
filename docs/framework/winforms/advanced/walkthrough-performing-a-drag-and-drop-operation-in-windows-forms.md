---
title: "Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 6c78a06e37de491e95d56d29c9d2f3e60b88e8ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529458"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="c90a3-102">Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c90a3-102">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="c90a3-103">Per eseguire operazioni di trascinamento e rilascio all'interno delle applicazioni basate su Windows è necessario gestire una serie di eventi, in particolare il <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, e <xref:System.Windows.Forms.Control.DragDrop> eventi.</span><span class="sxs-lookup"><span data-stu-id="c90a3-103">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="c90a3-104">Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="c90a3-104">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="c90a3-105">Trascinamento di dati</span><span class="sxs-lookup"><span data-stu-id="c90a3-105">Dragging Data</span></span>  
 <span data-ttu-id="c90a3-106">Tutte le operazioni di trascinamento della selezione iniziano con il trascinamento.</span><span class="sxs-lookup"><span data-stu-id="c90a3-106">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="c90a3-107">La funzionalità che consente di raccogliere quando inizia a trascinare i dati viene implementata nel <xref:System.Windows.Forms.Control.DoDragDrop%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c90a3-107">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="c90a3-108">Nell'esempio seguente, il <xref:System.Windows.Forms.Control.MouseDown> evento utilizzato per avviare l'operazione di trascinamento perché è più intuitivo (la maggior parte delle operazioni di trascinamento e rilascio iniziano con il pulsante del mouse viene premuto un).</span><span class="sxs-lookup"><span data-stu-id="c90a3-108">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="c90a3-109">Tenere tuttavia presente che, per avviare una procedura di trascinamento della selezione, può essere usato qualsiasi evento.</span><span class="sxs-lookup"><span data-stu-id="c90a3-109">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c90a3-110">Alcuni controlli hanno eventi specifici per il trascinamento.</span><span class="sxs-lookup"><span data-stu-id="c90a3-110">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="c90a3-111">Il <xref:System.Windows.Forms.ListView> e <xref:System.Windows.Forms.TreeView> controlli, ad esempio, avere un <xref:System.Windows.Forms.TreeView.ItemDrag> evento.</span><span class="sxs-lookup"><span data-stu-id="c90a3-111">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="c90a3-112">Per avviare un'operazione di trascinamento</span><span class="sxs-lookup"><span data-stu-id="c90a3-112">To start a drag operation</span></span>  
  
1.  <span data-ttu-id="c90a3-113">Nel <xref:System.Windows.Forms.Control.MouseDown> evento per il controllo in cui inizia il trascinamento, utilizzare il `DoDragDrop` l'effetto consentito e il metodo per impostare i dati da trascinare.</span><span class="sxs-lookup"><span data-stu-id="c90a3-113">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="c90a3-114">Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="c90a3-114">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="c90a3-115">L'esempio seguente illustra come avviare un'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="c90a3-115">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="c90a3-116">Il controllo in cui inizia il trascinamento è un <xref:System.Windows.Forms.Button> (controllo), i dati trascinati è la stringa che rappresenta il <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.Button> controllo e gli effetti consentiti sono la copia o spostamento.</span><span class="sxs-lookup"><span data-stu-id="c90a3-116">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    >  <span data-ttu-id="c90a3-117">Qualsiasi tipo di dati può essere utilizzati come parametro nel `DoDragDrop` metodo; nell'esempio precedente, il <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.Button> controllo veniva utilizzato (anziché un valore a livello di codice o il recupero dei dati da un set di dati) perché la proprietà è correlata al percorso trascinato da (il <xref:System.Windows.Forms.Button> controllo).</span><span class="sxs-lookup"><span data-stu-id="c90a3-117">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="c90a3-118">Tenerlo presente quando si incorporano operazioni di trascinamento della selezione nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="c90a3-118">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="c90a3-119">Durante un'operazione di trascinamento è attiva, è possibile gestire il <xref:System.Windows.Forms.Control.QueryContinueDrag> evento, quale "richiede l'autorizzazione" del sistema per continuare l'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="c90a3-119">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="c90a3-120">Quando si gestisce questo metodo, è anche appropriato chiamare i metodi che avranno effetto sull'operazione di trascinamento, ad esempio di espandere un <xref:System.Windows.Forms.TreeNode> in un <xref:System.Windows.Forms.TreeView> controllare quando il cursore viene spostato su di esso.</span><span class="sxs-lookup"><span data-stu-id="c90a3-120">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="c90a3-121">Rilascio dei dati</span><span class="sxs-lookup"><span data-stu-id="c90a3-121">Dropping Data</span></span>  
 <span data-ttu-id="c90a3-122">Dopo avere iniziato a trascinare i dati da una posizione in un Windows Form o in un controllo, sarà ovviamente necessario rilasciarli.</span><span class="sxs-lookup"><span data-stu-id="c90a3-122">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="c90a3-123">Il cursore cambia quando attraversa un'area di un form o di un controllo configurata correttamente per il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="c90a3-123">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="c90a3-124">Qualsiasi area all'interno di un Windows Form o controllo, è possibile eseguire per accettare dati trascinati impostando il <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà e la gestione di <xref:System.Windows.Forms.Control.DragEnter> e <xref:System.Windows.Forms.Control.DragDrop> eventi.</span><span class="sxs-lookup"><span data-stu-id="c90a3-124">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="c90a3-125">Per eseguire un rilascio</span><span class="sxs-lookup"><span data-stu-id="c90a3-125">To perform a drop</span></span>  
  
1.  <span data-ttu-id="c90a3-126">Impostare il <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà su true.</span><span class="sxs-lookup"><span data-stu-id="c90a3-126">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2.  <span data-ttu-id="c90a3-127">Nel `DragEnter` evento per il controllo in cui verrà eseguita l'eliminazione, assicurarsi che i dati trascinati siano di un tipo accettabile (in questo caso, <xref:System.Windows.Forms.Control.Text%2A>).</span><span class="sxs-lookup"><span data-stu-id="c90a3-127">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="c90a3-128">Il codice imposta quindi l'effetto che si verificherà quando l'eliminazione si verifica in un valore di <xref:System.Windows.Forms.DragDropEffects> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="c90a3-128">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="c90a3-129">Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="c90a3-129">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    >  <span data-ttu-id="c90a3-130">È possibile definire <xref:System.Windows.Forms.DataFormats> specificando il proprio oggetto come il <xref:System.Object> parametro del <xref:System.Windows.Forms.DataObject.SetData%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c90a3-130">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="c90a3-131">Assicurarsi, in tal caso, che l'oggetto specificato sia serializzabile.</span><span class="sxs-lookup"><span data-stu-id="c90a3-131">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="c90a3-132">Per altre informazioni, vedere <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="c90a3-132">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3.  <span data-ttu-id="c90a3-133">Nel <xref:System.Windows.Forms.Control.DragDrop> evento per il controllo in cui verrà eseguita l'eliminazione, utilizzare il <xref:System.Windows.Forms.DataObject.GetData%2A> metodo per recuperare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="c90a3-133">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="c90a3-134">Per altre informazioni, vedere <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="c90a3-134">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="c90a3-135">Nell'esempio seguente, un <xref:System.Windows.Forms.TextBox> il controllo viene trascinato a (in cui verrà eseguita l'eliminazione).</span><span class="sxs-lookup"><span data-stu-id="c90a3-135">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="c90a3-136">Il codice imposta il <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllare uguale per i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="c90a3-136">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    >  <span data-ttu-id="c90a3-137">Inoltre, è possibile utilizzare il <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> proprietà, in modo che, a seconda di tasti premuti durante l'operazione di trascinamento e rilascio, alcuni effetti si verificano (ad esempio, è standard per copiare i dati trascinati quando viene premuto il tasto CTRL).</span><span class="sxs-lookup"><span data-stu-id="c90a3-137">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c90a3-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c90a3-138">See Also</span></span>  
 [<span data-ttu-id="c90a3-139">Procedura: Aggiungere dati agli Appunti</span><span class="sxs-lookup"><span data-stu-id="c90a3-139">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 [<span data-ttu-id="c90a3-140">Procedura: Recuperare dati dagli Appunti</span><span class="sxs-lookup"><span data-stu-id="c90a3-140">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="c90a3-141">[Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)</span><span class="sxs-lookup"><span data-stu-id="c90a3-141">[Drag-and-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)</span></span>
