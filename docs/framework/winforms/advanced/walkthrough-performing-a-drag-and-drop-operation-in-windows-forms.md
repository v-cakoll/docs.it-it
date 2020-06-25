---
title: "Procedura dettagliata: eseguire un'operazione di trascinamento della selezione"
description: Informazioni su come eseguire un'operazione di trascinamento della selezione in Windows Forms gestendo una serie di eventi, in particolare gli eventi DragEnter, DragLeave e DragDrop.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325813"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="f698b-103">Procedura dettagliata: Esecuzione di un'operazione di trascinamento della selezione in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f698b-103">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="f698b-104">Per eseguire operazioni di trascinamento della selezione nelle applicazioni basate su Windows, è necessario gestire una serie di eventi, in particolare gli <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragLeave> eventi, e <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="f698b-104">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="f698b-105">Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="f698b-105">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="f698b-106">Trascinamento di dati</span><span class="sxs-lookup"><span data-stu-id="f698b-106">Dragging Data</span></span>  
 <span data-ttu-id="f698b-107">Tutte le operazioni di trascinamento della selezione iniziano con il trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f698b-107">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="f698b-108">La funzionalità per consentire la raccolta dei dati quando inizia il trascinamento è implementata nel <xref:System.Windows.Forms.Control.DoDragDrop%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f698b-108">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="f698b-109">Nell'esempio seguente, l' <xref:System.Windows.Forms.Control.MouseDown> evento viene usato per avviare l'operazione di trascinamento perché è il più intuitivo (la maggior parte delle azioni di trascinamento inizia con il pulsante del mouse premuto).</span><span class="sxs-lookup"><span data-stu-id="f698b-109">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="f698b-110">Tenere tuttavia presente che, per avviare una procedura di trascinamento della selezione, può essere usato qualsiasi evento.</span><span class="sxs-lookup"><span data-stu-id="f698b-110">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f698b-111">Alcuni controlli hanno eventi specifici per il trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f698b-111">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="f698b-112">I <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> controlli e, ad esempio, hanno un <xref:System.Windows.Forms.TreeView.ItemDrag> evento.</span><span class="sxs-lookup"><span data-stu-id="f698b-112">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="f698b-113">Per avviare un'operazione di trascinamento</span><span class="sxs-lookup"><span data-stu-id="f698b-113">To start a drag operation</span></span>  
  
1. <span data-ttu-id="f698b-114">Nell' <xref:System.Windows.Forms.Control.MouseDown> evento per il controllo in cui inizierà il trascinamento, utilizzare il `DoDragDrop` metodo per impostare i dati da trascinare e il trascinamento dell'effetto consentito avrà.</span><span class="sxs-lookup"><span data-stu-id="f698b-114">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="f698b-115">Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span><span class="sxs-lookup"><span data-stu-id="f698b-115">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="f698b-116">L'esempio seguente illustra come avviare un'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f698b-116">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="f698b-117">Il controllo in cui inizia il trascinamento è un <xref:System.Windows.Forms.Button> controllo, i dati trascinati sono la stringa che rappresenta la <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.Button> controllo e gli effetti consentiti vengono copiati o spostati.</span><span class="sxs-lookup"><span data-stu-id="f698b-117">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
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
    > <span data-ttu-id="f698b-118">I dati possono essere usati come parametro nel `DoDragDrop` metodo. nell'esempio precedente, <xref:System.Windows.Forms.Control.Text%2A> è stata usata la proprietà del controllo, anziché impostare come <xref:System.Windows.Forms.Button> hardcoded un valore o recuperare i dati da un set di dati, perché la proprietà era correlata al percorso da trascinare (il <xref:System.Windows.Forms.Button> controllo).</span><span class="sxs-lookup"><span data-stu-id="f698b-118">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="f698b-119">Tenerlo presente quando si incorporano operazioni di trascinamento della selezione nelle applicazioni basate su Windows.</span><span class="sxs-lookup"><span data-stu-id="f698b-119">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="f698b-120">Mentre è attiva un'operazione di trascinamento, è possibile gestire l' <xref:System.Windows.Forms.Control.QueryContinueDrag> evento, che "chiede l'autorizzazione" del sistema per continuare l'operazione di trascinamento.</span><span class="sxs-lookup"><span data-stu-id="f698b-120">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="f698b-121">Quando si gestisce questo metodo, è anche il punto appropriato per chiamare i metodi che avranno effetto sull'operazione di trascinamento, ad esempio l'espansione di un oggetto <xref:System.Windows.Forms.TreeNode> in un <xref:System.Windows.Forms.TreeView> controllo quando il cursore viene spostato su di esso.</span><span class="sxs-lookup"><span data-stu-id="f698b-121">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="f698b-122">Rilascio dei dati</span><span class="sxs-lookup"><span data-stu-id="f698b-122">Dropping Data</span></span>  
 <span data-ttu-id="f698b-123">Dopo avere iniziato a trascinare i dati da una posizione in un Windows Form o in un controllo, sarà ovviamente necessario rilasciarli.</span><span class="sxs-lookup"><span data-stu-id="f698b-123">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="f698b-124">Il cursore cambia quando attraversa un'area di un form o di un controllo configurata correttamente per il rilascio dei dati.</span><span class="sxs-lookup"><span data-stu-id="f698b-124">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="f698b-125">È possibile fare in modo che qualsiasi area all'interno di un Windows Form o di un controllo accetti i dati rimossi impostando la <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà e gestendo gli <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> eventi e.</span><span class="sxs-lookup"><span data-stu-id="f698b-125">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="f698b-126">Per eseguire un rilascio</span><span class="sxs-lookup"><span data-stu-id="f698b-126">To perform a drop</span></span>  
  
1. <span data-ttu-id="f698b-127">Impostare la <xref:System.Windows.Forms.Control.AllowDrop%2A> proprietà su true.</span><span class="sxs-lookup"><span data-stu-id="f698b-127">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="f698b-128">Nell' `DragEnter` evento per il controllo in cui si verificherà il rilascio, assicurarsi che i dati trascinati siano di un tipo accettabile (in questo caso <xref:System.Windows.Forms.Control.Text%2A> ).</span><span class="sxs-lookup"><span data-stu-id="f698b-128">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="f698b-129">Il codice imposta quindi l'effetto che si verificherà quando il rilascio viene eseguito in un valore nell' <xref:System.Windows.Forms.DragDropEffects> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="f698b-129">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="f698b-130">Per altre informazioni, vedere <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span><span class="sxs-lookup"><span data-stu-id="f698b-130">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
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
    > <span data-ttu-id="f698b-131">È possibile definirne <xref:System.Windows.Forms.DataFormats> di propri specificando il proprio oggetto come <xref:System.Object> parametro del <xref:System.Windows.Forms.DataObject.SetData%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="f698b-131">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="f698b-132">Assicurarsi, in tal caso, che l'oggetto specificato sia serializzabile.</span><span class="sxs-lookup"><span data-stu-id="f698b-132">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="f698b-133">Per altre informazioni, vedere <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="f698b-133">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="f698b-134">Nell' <xref:System.Windows.Forms.Control.DragDrop> evento per il controllo in cui si verificherà il rilascio, utilizzare il <xref:System.Windows.Forms.DataObject.GetData%2A> metodo per recuperare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="f698b-134">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="f698b-135">Per altre informazioni, vedere <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span><span class="sxs-lookup"><span data-stu-id="f698b-135">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="f698b-136">Nell'esempio seguente un <xref:System.Windows.Forms.TextBox> controllo è il controllo da trascinare (in cui si verificherà il rilascio).</span><span class="sxs-lookup"><span data-stu-id="f698b-136">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="f698b-137">Il codice imposta la <xref:System.Windows.Forms.Control.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllo uguale ai dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="f698b-137">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
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
    > <span data-ttu-id="f698b-138">Inoltre, è possibile utilizzare la <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> proprietà, in modo che, a seconda delle chiavi deselezionate durante l'operazione di trascinamento della selezione, si verifichino determinati effetti, ad esempio è standard copiare i dati trascinati quando viene premuto il tasto CTRL.</span><span class="sxs-lookup"><span data-stu-id="f698b-138">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f698b-139">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f698b-139">See also</span></span>

- <span data-ttu-id="f698b-140">[How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md) (Procedura: Aggiungere dati agli Appunti)</span><span class="sxs-lookup"><span data-stu-id="f698b-140">[How to: Add Data to the Clipboard](how-to-add-data-to-the-clipboard.md)</span></span>
- <span data-ttu-id="f698b-141">[How to: Retrieve Data from the Clipboard](how-to-retrieve-data-from-the-clipboard.md) (Procedura: Recuperare dati dagli Appunti)</span><span class="sxs-lookup"><span data-stu-id="f698b-141">[How to: Retrieve Data from the Clipboard](how-to-retrieve-data-from-the-clipboard.md)</span></span>
- <span data-ttu-id="f698b-142">[Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md) (Supporto delle operazioni di trascinamento della selezione e degli Appunti)</span><span class="sxs-lookup"><span data-stu-id="f698b-142">[Drag-and-Drop Operations and Clipboard Support](drag-and-drop-operations-and-clipboard-support.md)</span></span>
