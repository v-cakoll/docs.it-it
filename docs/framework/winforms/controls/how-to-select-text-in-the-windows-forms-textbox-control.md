---
title: Selezionare il testo nel controllo TextBox
description: Informazioni su come selezionare il testo a livello di codice nel controllo TextBox Windows Forms. Viene inoltre illustrato come avvisare visivamente il lettore della posizione della stringa trovata.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], selecting text programmatically
- text boxes [Windows Forms], selecting text programmatically
- text [Windows Forms], selecting in text boxes programmatically
ms.assetid: 8c591546-6a01-45c7-8e03-f78431f903b1
ms.openlocfilehash: b8fdaff76461c4d6766dfc6afaef5e814d982834
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621561"
---
# <a name="how-to-select-text-in-the-windows-forms-textbox-control"></a><span data-ttu-id="40531-104">Procedura: selezionare testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="40531-104">How to: Select Text in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="40531-105">È possibile selezionare il testo a livello di codice nel <xref:System.Windows.Forms.TextBox> controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="40531-105">You can select text programmatically in the Windows Forms <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="40531-106">Se, ad esempio, si crea una funzione che cerca un testo per una determinata stringa, è possibile selezionare il testo per avvisare visivamente il lettore della posizione della stringa trovata.</span><span class="sxs-lookup"><span data-stu-id="40531-106">For example, if you create a function that searches text for a particular string, you can select the text to visually alert the reader of the found string's position.</span></span>  
  
### <a name="to-select-text-programmatically"></a><span data-ttu-id="40531-107">Per selezionare il testo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="40531-107">To select text programmatically</span></span>  
  
1. <span data-ttu-id="40531-108">Impostare la <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà sull'inizio del testo che si desidera selezionare.</span><span class="sxs-lookup"><span data-stu-id="40531-108">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property to the beginning of the text you want to select.</span></span>  
  
     <span data-ttu-id="40531-109">La <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è un numero che indica il punto di inserimento all'interno della stringa di testo, con 0 è la posizione più a sinistra.</span><span class="sxs-lookup"><span data-stu-id="40531-109">The <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is a number that indicates the insertion point within the string of text, with 0 being the left-most position.</span></span> <span data-ttu-id="40531-110">Se la <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> proprietà è impostata su un valore maggiore o uguale al numero di caratteri nella casella di testo, il punto di inserimento viene inserito dopo l'ultimo carattere.</span><span class="sxs-lookup"><span data-stu-id="40531-110">If the <xref:System.Windows.Forms.TextBoxBase.SelectionStart%2A> property is set to a value equal to or greater than the number of characters in the text box, the insertion point is placed after the last character.</span></span>  
  
2. <span data-ttu-id="40531-111">Impostare la <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà sulla lunghezza del testo che si desidera selezionare.</span><span class="sxs-lookup"><span data-stu-id="40531-111">Set the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property to the length of the text you want to select.</span></span>  
  
     <span data-ttu-id="40531-112">La <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> proprietà è un valore numerico che imposta la larghezza del punto di inserimento.</span><span class="sxs-lookup"><span data-stu-id="40531-112">The <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> property is a numeric value that sets the width of the insertion point.</span></span> <span data-ttu-id="40531-113"><xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A>Se si imposta su un numero maggiore di 0, viene selezionato il numero di caratteri, a partire dal punto di inserimento corrente.</span><span class="sxs-lookup"><span data-stu-id="40531-113">Setting the <xref:System.Windows.Forms.TextBoxBase.SelectionLength%2A> to a number greater than 0 causes that number of characters to be selected, starting from the current insertion point.</span></span>  
  
3. <span data-ttu-id="40531-114">Opzionale Accedere al testo selezionato tramite la <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="40531-114">(Optional) Access the selected text through the <xref:System.Windows.Forms.TextBoxBase.SelectedText%2A> property.</span></span>  
  
     <span data-ttu-id="40531-115">Il codice seguente consente di selezionare il contenuto di una casella di testo quando <xref:System.Windows.Forms.Control.Enter> si verifica l'evento del controllo.</span><span class="sxs-lookup"><span data-stu-id="40531-115">The code below selects the contents of a text box when the control's <xref:System.Windows.Forms.Control.Enter> event occurs.</span></span> <span data-ttu-id="40531-116">Questo esempio controlla se la casella di testo contiene un valore per la <xref:System.Windows.Forms.TextBox.Text%2A> proprietà che non è `null` o una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="40531-116">This example checks if the text box has a value for the <xref:System.Windows.Forms.TextBox.Text%2A> property that is not `null` or an empty string.</span></span> <span data-ttu-id="40531-117">Quando la casella di testo riceve lo stato attivo, viene selezionato il testo corrente nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="40531-117">When the text box receives the focus, the current text in the text box is selected.</span></span> <span data-ttu-id="40531-118">Il `TextBox1_Enter` gestore eventi deve essere associato al controllo. per ulteriori informazioni, vedere [procedura: creare gestori eventi in fase di esecuzione per Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="40531-118">The `TextBox1_Enter` event handler must be bound to the control; for more information, see [How to: Create Event Handlers at Run Time for Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).</span></span>  
  
     <span data-ttu-id="40531-119">Per testare questo esempio, premere il tasto TAB fino a quando la casella di testo non ha lo stato attivo.</span><span class="sxs-lookup"><span data-stu-id="40531-119">To test this example, press the Tab key until the text box has the focus.</span></span> <span data-ttu-id="40531-120">Se si fa clic nella casella di testo, il testo viene deselezionato.</span><span class="sxs-lookup"><span data-stu-id="40531-120">If you click in the text box, the text is unselected.</span></span>  
  
    ```vb  
    Private Sub TextBox1_Enter(ByVal sender As Object, ByVal e As System.EventArgs) Handles TextBox1.Enter  
       If (Not String.IsNullOrEmpty(TextBox1.Text)) Then  
          TextBox1.SelectionStart = 0  
          TextBox1.SelectionLength = TextBox1.Text.Length  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_Enter(object sender, System.EventArgs e){  
       if (!String.IsNullOrEmpty(textBox1.Text))  
       {  
          textBox1.SelectionStart = 0;  
          textBox1.SelectionLength = textBox1.Text.Length;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void textBox1_Enter(System::Object ^ sender,  
          System::EventArgs ^ e) {  
       if (!System::String::IsNullOrEmpty(textBox1->Text))  
       {  
          textBox1->SelectionStart = 0;  
          textBox1->SelectionLength = textBox1->Text->Length;  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="40531-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40531-121">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="40531-122">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="40531-122">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="40531-123">Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="40531-123">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="40531-124">Procedura: creare una casella di testo Password con il controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="40531-124">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="40531-125">Procedura: creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="40531-125">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="40531-126">Procedura: inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="40531-126">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="40531-127">Procedura: visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="40531-127">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="40531-128">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="40531-128">TextBox Control</span></span>](textbox-control-windows-forms.md)
