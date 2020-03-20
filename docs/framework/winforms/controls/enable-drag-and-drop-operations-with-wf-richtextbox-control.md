---
title: Abilitare le operazioni di trascinamento della selezione con il controllo RichTextBoxEnable Drag-and-Drop Operations with RichTextBox Control
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], text boxes
- drag and drop [Windows Forms], richTextBox control
- text boxes [Windows Forms], drag-and-drop operations
- RichTextBox control [Windows Forms], drag-and-drop operations
ms.assetid: ca167d1c-2014-4cf0-96a0-20598470be3b
ms.openlocfilehash: 27e5c18598552c465ef17f5e58069bc10e401c09
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182356"
---
# <a name="how-to-enable-drag-and-drop-operations-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="78606-102">Procedura: abilitare operazioni di trascinamento con il controllo RichTextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="78606-102">How to: Enable Drag-and-Drop Operations with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="78606-103">Le operazioni di trascinamento della selezione del controllo <xref:System.Windows.Forms.RichTextBox> di Windows Form vengono eseguite gestendo gli eventi <xref:System.Windows.Forms.RichTextBox.DragEnter> e <xref:System.Windows.Forms.RichTextBox.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="78606-103">Drag-and-drop operations with the Windows Forms <xref:System.Windows.Forms.RichTextBox> control are done by handling the <xref:System.Windows.Forms.RichTextBox.DragEnter> and <xref:System.Windows.Forms.RichTextBox.DragDrop> events.</span></span> <span data-ttu-id="78606-104">Quindi, le operazioni di trascinamento della selezione risultano molto semplici con il controllo <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="78606-104">Thus, drag-and-drop operations are extremely simple with the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
### <a name="to-enable-drag-operations-in-a-richtextbox-control"></a><span data-ttu-id="78606-105">Per abilitare le operazioni di trascinamento in un controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="78606-105">To enable drag operations in a RichTextBox control</span></span>  
  
1. <span data-ttu-id="78606-106">Impostare la proprietà <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> del controllo <xref:System.Windows.Forms.RichTextBox> su `true`.</span><span class="sxs-lookup"><span data-stu-id="78606-106">Set the <xref:System.Windows.Forms.RichTextBox.AllowDrop%2A> property of the <xref:System.Windows.Forms.RichTextBox> control to `true`.</span></span>  
  
2. <span data-ttu-id="78606-107">Scrivere il codice nel gestore eventi per l'evento <xref:System.Windows.Forms.RichTextBox.DragEnter> .</span><span class="sxs-lookup"><span data-stu-id="78606-107">Write code in the event handler of the <xref:System.Windows.Forms.RichTextBox.DragEnter> event.</span></span> <span data-ttu-id="78606-108">Usare un'istruzione `if` per assicurarsi che i dati trascinati siano di un tipo accettabile (in questo caso, testo).</span><span class="sxs-lookup"><span data-stu-id="78606-108">Use an `if` statement to ensure that the data being dragged is of an acceptable type (in this case, text).</span></span> <span data-ttu-id="78606-109">La proprietà <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> può essere impostata su uno qualsiasi dei valori dell'enumerazione <xref:System.Windows.Forms.DragDropEffects> .</span><span class="sxs-lookup"><span data-stu-id="78606-109">The <xref:System.Windows.Forms.DragEventArgs.Effect%2A?displayProperty=nameWithType> property can be set to any value of the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragEnter(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
          e.Effect = DragDropEffects.Copy  
       Else  
          e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    ```cpp  
    private:  
       void richTextBox1_DragEnter(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          if (e->Data->GetDataPresent(DataFormats::Text))  
             e->Effect = DragDropEffects::Copy;  
          else  
             e->Effect = DragDropEffects::None;  
       }  
    ```  
  
     <span data-ttu-id="78606-110">(Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="78606-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragEnter += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragEnter);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragEnter += gcnew  
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragEnter);  
    ```  
  
3. <span data-ttu-id="78606-111">Scrivere codice per gestire l'evento <xref:System.Windows.Forms.RichTextBox.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="78606-111">Write code to handle the <xref:System.Windows.Forms.RichTextBox.DragDrop> event.</span></span> <span data-ttu-id="78606-112">Usare il metodo <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> per recuperare i dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="78606-112">Use the <xref:System.Windows.Forms.DataObject.GetData%2A?displayProperty=nameWithType> method to retrieve the data being dragged.</span></span>  
  
     <span data-ttu-id="78606-113">Nell'esempio seguente il codice imposta la proprietà <xref:System.Windows.Forms.RichTextBox.Text%2A> del controllo <xref:System.Windows.Forms.RichTextBox> uguale ai dati trascinati.</span><span class="sxs-lookup"><span data-stu-id="78606-113">In the example below, the code sets the <xref:System.Windows.Forms.RichTextBox.Text%2A> property of the <xref:System.Windows.Forms.RichTextBox> control equal to the data being dragged.</span></span> <span data-ttu-id="78606-114">Se il testo è già presente nel controllo <xref:System.Windows.Forms.RichTextBox> , il testo trascinato viene inserito nel punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="78606-114">If there is already text in the <xref:System.Windows.Forms.RichTextBox> control, the dragged text is inserted at the insertion point.</span></span>  
  
    ```vb  
    Private Sub RichTextBox1_DragDrop(ByVal sender As Object, _
       ByVal e As System.Windows.Forms.DragEventArgs) _
       Handles RichTextBox1.DragDrop  
       Dim i As Int16
       Dim s As String  
  
       ' Get start position to drop the text.  
       i = RichTextBox1.SelectionStart  
       s = RichTextBox1.Text.Substring(i)  
       RichTextBox1.Text = RichTextBox1.Text.Substring(0, i)  
  
       ' Drop the text on to the RichTextBox.  
       RichTextBox1.Text = RichTextBox1.Text + _  
          e.Data.GetData(DataFormats.Text).ToString()  
       RichTextBox1.Text = RichTextBox1.Text + s  
    End Sub  
    ```  
  
    ```csharp  
    private void richTextBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       int i;  
       String s;  
  
       // Get start position to drop the text.  
       i = richTextBox1.SelectionStart;  
       s = richTextBox1.Text.Substring(i);  
       richTextBox1.Text = richTextBox1.Text.Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       richTextBox1.Text = richTextBox1.Text +
          e.Data.GetData(DataFormats.Text).ToString();  
       richTextBox1.Text = richTextBox1.Text + s;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void richTextBox1_DragDrop(System::Object ^  sender,  
          System::Windows::Forms::DragEventArgs ^  e)  
       {  
          int i;  
          String ^s;  
  
       // Get start position to drop the text.  
       i = richTextBox1->SelectionStart;  
       s = richTextBox1->Text->Substring(i);  
       richTextBox1->Text = richTextBox1->Text->Substring(0,i);  
  
       // Drop the text on to the RichTextBox.  
       String ^str = String::Concat(richTextBox1->Text, e->Data  
       ->GetData(DataFormats->Text)->ToString());
       richTextBox1->Text = String::Concat(str, s);  
       }  
    ```  
  
     <span data-ttu-id="78606-115">(Visual Cè e Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="78606-115">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.richTextBox1.DragDrop += new  
        System.Windows.Forms.DragEventHandler  
        (this.richTextBox1_DragDrop);  
    ```  
  
    ```cpp  
    this->richTextBox1->DragDrop += gcnew
       System::Windows::Forms::DragEventHandler  
       (this, &Form1::richTextBox1_DragDrop);  
    ```  
  
### <a name="to-test-the-drag-and-drop-functionality-in-your-application"></a><span data-ttu-id="78606-116">Per testare la funzionalità di trascinamento della selezione nell'applicazione</span><span class="sxs-lookup"><span data-stu-id="78606-116">To test the drag-and-drop functionality in your application</span></span>  
  
1. <span data-ttu-id="78606-117">Salvare e compilare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="78606-117">Save and build your application.</span></span> <span data-ttu-id="78606-118">Durante l'esecuzione, eseguire WordPad.</span><span class="sxs-lookup"><span data-stu-id="78606-118">While it is running, run WordPad.</span></span>  
  
     <span data-ttu-id="78606-119">WordPad è un editor di testo installato da Windows che consente operazioni di trascinamento della selezione.</span><span class="sxs-lookup"><span data-stu-id="78606-119">WordPad is a text editor installed by Windows that allows drag-and-drop operations.</span></span> <span data-ttu-id="78606-120">È accessibile premendo **Start** , selezionando **Esegui**e digitando `WordPad` nella casella di testo della finestra di dialogo **Esegui** , quindi facendo clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="78606-120">It is accessible by clicking the **Start** button, selecting **Run**, typing `WordPad` in the text box of the **Run** dialog box, and then clicking **OK**.</span></span>  
  
2. <span data-ttu-id="78606-121">Una volta aperto WordPad, digitare una stringa di testo al suo interno.</span><span class="sxs-lookup"><span data-stu-id="78606-121">Once WordPad is open, type a string of text in it.</span></span> <span data-ttu-id="78606-122">Usando il mouse, selezionare il testo e quindi trascinarlo sul controllo <xref:System.Windows.Forms.RichTextBox> nell'applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="78606-122">Using the mouse, select the text, and then drag the selected text over to the <xref:System.Windows.Forms.RichTextBox> control in your Windows application.</span></span>  
  
     <span data-ttu-id="78606-123">Quando si passa il mouse sul controllo <xref:System.Windows.Forms.RichTextBox> (e, di conseguenza, si genera l'evento <xref:System.Windows.Forms.RichTextBox.DragEnter> ), il puntatore del mouse cambia ed è possibile rilasciare il testo selezionato nel controllo <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="78606-123">Notice that when you point the mouse at the <xref:System.Windows.Forms.RichTextBox> control (and, consequently, raise the <xref:System.Windows.Forms.RichTextBox.DragEnter> event), the mouse pointer changes and you can drop the selected text into the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
     <span data-ttu-id="78606-124">Quando si rilascia il pulsante del mouse, il testo selezionato viene rilasciato (ossia, viene generato l'evento <xref:System.Windows.Forms.RichTextBox.DragDrop> ) e viene inserito all'interno del controllo <xref:System.Windows.Forms.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="78606-124">When you release the mouse button, the selected text is dropped (that is, the <xref:System.Windows.Forms.RichTextBox.DragDrop> event is raised) and is inserted within the <xref:System.Windows.Forms.RichTextBox> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78606-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78606-125">See also</span></span>

- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="78606-126">Procedura: eseguire operazioni di trascinamento e rilascio tra applicazioni</span><span class="sxs-lookup"><span data-stu-id="78606-126">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../advanced/how-to-perform-drag-and-drop-operations-between-applications.md)
- [<span data-ttu-id="78606-127">Controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="78606-127">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="78606-128">Controlli da utilizzare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="78606-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
