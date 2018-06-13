---
title: 'Procedura dettagliata: utilizzo del controllo MaskedTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- input [Windows Forms], controlling to ensure validity
- MaskedTextBox control [Windows Forms], walkthroughs
- MaskedTextBox control [Windows Forms], validation
- user input [Windows Forms], controlling
- text [Windows Forms], controls for input
ms.assetid: df60565e-5447-4110-92a6-be1f6ff5faa3
ms.openlocfilehash: bcca6c5f5481d351a39a4e71532cc0f006075128
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538441"
---
# <a name="walkthrough-working-with-the-maskedtextbox-control"></a><span data-ttu-id="78244-102">Procedura dettagliata: utilizzo del controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="78244-102">Walkthrough: Working with the MaskedTextBox Control</span></span>
<span data-ttu-id="78244-103">Le attività illustrate nella procedura dettagliata sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="78244-103">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="78244-104">L'inizializzazione di <xref:System.Windows.Forms.MaskedTextBox> controllo</span><span class="sxs-lookup"><span data-stu-id="78244-104">Initializing the <xref:System.Windows.Forms.MaskedTextBox> control</span></span>  
  
-   <span data-ttu-id="78244-105">Utilizzo di <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> gestore eventi per avvertire l'utente quando un carattere non è conforme alla maschera</span><span class="sxs-lookup"><span data-stu-id="78244-105">Using the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event handler to alert the user when a character does not conform to the mask</span></span>  
  
-   <span data-ttu-id="78244-106">Assegnazione di un tipo per il <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> proprietà e utilizzando il <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> gestore eventi per avvertire l'utente quando il valore di cui si sta tentando di eseguire il commit non è valido per il tipo di</span><span class="sxs-lookup"><span data-stu-id="78244-106">Assigning a type to the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property and using the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event handler to alert the user when the value they're attempting to commit is not valid for the type</span></span>  
  
## <a name="creating-the-project-and-adding-a-control"></a><span data-ttu-id="78244-107">Creazione del progetto e aggiungendo un controllo</span><span class="sxs-lookup"><span data-stu-id="78244-107">Creating the Project and Adding a Control</span></span>  
  
#### <a name="to-add-a-maskedtextbox-control-to-your-form"></a><span data-ttu-id="78244-108">Per aggiungere un controllo MaskedTextBox al form</span><span class="sxs-lookup"><span data-stu-id="78244-108">To add a MaskedTextBox control to your form</span></span>  
  
1.  <span data-ttu-id="78244-109">Aprire il form in cui si desidera posizionare il <xref:System.Windows.Forms.MaskedTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="78244-109">Open the form on which you want to place the <xref:System.Windows.Forms.MaskedTextBox> control.</span></span>  
  
2.  <span data-ttu-id="78244-110">Trascinare un <xref:System.Windows.Forms.MaskedTextBox> controllo il **della casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="78244-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control from the **Toolbox** to your form.</span></span>  
  
3.  <span data-ttu-id="78244-111">Il pulsante destro del controllo e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="78244-111">Right-click the control and choose **Properties**.</span></span> <span data-ttu-id="78244-112">Nel **proprietà** finestra, seleziona il **Mask** proprietà e fare clic su di **...**  (pulsante) accanto al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="78244-112">In the **Properties** window, select the **Mask** property and click the **...** (ellipsis) button next to the property name.</span></span>  
  
4.  <span data-ttu-id="78244-113">Nel **maschera di Input** la finestra di dialogo, seleziona il **data breve** mascherare e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="78244-113">In the **Input Mask** dialog box, select the **Short Date** mask and click **OK**.</span></span>  
  
5.  <span data-ttu-id="78244-114">Nel **proprietà** finestra set di <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="78244-114">In the **Properties** window set the <xref:System.Windows.Forms.MaskedTextBox.BeepOnError%2A> property to `true`.</span></span> <span data-ttu-id="78244-115">Questa proprietà determina un breve segnale acustico ogni volta che l'utente tenta di un carattere che viola la definizione della maschera di input.</span><span class="sxs-lookup"><span data-stu-id="78244-115">This property causes a short beep to sound every time the user attempts to input a character that violates the mask definition.</span></span>  
  
 <span data-ttu-id="78244-116">Per un riepilogo dei caratteri che supporta la proprietà maschera, vedere la sezione Note della <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="78244-116">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
## <a name="alert-the-user-to-input-errors"></a><span data-ttu-id="78244-117">Avvisare l'utente per gli errori di Input</span><span class="sxs-lookup"><span data-stu-id="78244-117">Alert the User to Input Errors</span></span>  
  
#### <a name="add-a-balloon-tip-for-rejected-mask-input"></a><span data-ttu-id="78244-118">Aggiungere una descrizione comandi per l'input maschera rifiutato</span><span class="sxs-lookup"><span data-stu-id="78244-118">Add a balloon tip for rejected mask input</span></span>  
  
1.  <span data-ttu-id="78244-119">Restituito per il **della casella degli strumenti** e aggiungere un <xref:System.Windows.Forms.ToolTip> al form.</span><span class="sxs-lookup"><span data-stu-id="78244-119">Return to the **Toolbox** and add a <xref:System.Windows.Forms.ToolTip> to your form.</span></span>  
  
2.  <span data-ttu-id="78244-120">Creare un gestore eventi per il <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> evento che genera il <xref:System.Windows.Forms.ToolTip> quando si verifica un errore di input.</span><span class="sxs-lookup"><span data-stu-id="78244-120">Create an event handler for the <xref:System.Windows.Forms.MaskedTextBox.MaskInputRejected> event that raises the <xref:System.Windows.Forms.ToolTip> when an input error occurs.</span></span> <span data-ttu-id="78244-121">Il fumetto suggerimento rimane visibile per cinque secondi o fino a quando l'utente fa clic.</span><span class="sxs-lookup"><span data-stu-id="78244-121">The balloon tip remains visible for five seconds, or until the user clicks it.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        ... // Other initialization code  
        maskedTextBox1.Mask = "00/00/0000";  
        maskedTextBox1.MaskInputRejected += new MaskInputRejectedEventHandler(maskedTextBox1_MaskInputRejected)  
    }  
  
    void maskedTextBox1_MaskInputRejected(object sender, MaskInputRejectedEventArgs e)  
    {  
        toolTip1.ToolTipTitle = "Invalid Input";  
        toolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", maskedTextBox1, maskedTextBox1.Location, 5000);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        Me.ToolTip1.IsBalloon = True  
        Me.MaskedTextBox1.Mask = "00/00/0000"  
    End Sub  
  
    Private Sub MaskedTextBox1_MaskInputRejected(sender as Object, e as MaskInputRejectedEventArgs) Handles MaskedTextBox1.MaskInputRejected  
        ToolTip1.ToolTipTitle = "Invalid Input"  
        ToolTip1.Show("We're sorry, but only digits (0-9) are allowed in dates.", MaskedTextBox1, 5000)  
    End Sub  
    ```  
  
## <a name="alert-the-user-to-a-type-that-is-not-valid"></a><span data-ttu-id="78244-122">Avvisare l'utente a un tipo che non è valido</span><span class="sxs-lookup"><span data-stu-id="78244-122">Alert the User to a Type that Is Not Valid</span></span>  
  
#### <a name="add-a-balloon-tip-for-invalid-data-types"></a><span data-ttu-id="78244-123">Aggiungere una descrizione comandi per i tipi di dati non validi</span><span class="sxs-lookup"><span data-stu-id="78244-123">Add a balloon tip for invalid data types</span></span>  
  
1.  <span data-ttu-id="78244-124">Del modulo <xref:System.Windows.Forms.Form.Load> gestore dell'evento, assegnare un <xref:System.Type> oggetto che rappresenta il <xref:System.DateTime> tipo di <xref:System.Windows.Forms.MaskedTextBox> del controllo <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> proprietà:</span><span class="sxs-lookup"><span data-stu-id="78244-124">In your form's <xref:System.Windows.Forms.Form.Load> event handler, assign a <xref:System.Type> object representing the <xref:System.DateTime> type to the <xref:System.Windows.Forms.MaskedTextBox> control's <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property:</span></span>  
  
    ```csharp  
    private void Form1_Load(Object sender, EventArgs e)  
    {  
        // Other code  
        maskedTextBox1.ValidatingType = typeof(System.DateTime);  
        maskedTextBox1.TypeValidationCompleted += new TypeValidationEventHandler(maskedTextBox1_TypeValidationCompleted);  
    }  
    ```  
  
    ```vb  
    Private Sub Form1_Load(sender as Object, e as EventArgs)  
        // Other code  
        MaskedTextBox1.ValidatingType = GetType(System.DateTime)  
    End Sub  
    ```  
  
2.  <span data-ttu-id="78244-125">Aggiungere un gestore eventi per l'evento <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted>:</span><span class="sxs-lookup"><span data-stu-id="78244-125">Add an event handler for the <xref:System.Windows.Forms.MaskedTextBox.TypeValidationCompleted> event:</span></span>  
  
    ```csharp  
    public void maskedTextBox1_TypeValidationCompleted(object sender, TypeValidationEventArgs e)  
    {  
        if (!e.IsValidInput)  
        {  
           toolTip1.ToolTipTitle = "Invalid Date Value";  
           toolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000);  
           e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Public Sub MaskedTextBox1_TypeValidationCompleted(sender as Object, e as TypeValidationEventArgs)  
        If Not e.IsValidInput Then  
           ToolTip1.ToolTipTitle = "Invalid Date Value"  
           ToolTip1.Show("We're sorry, but the value you entered is not a valid date. Please change the value.", maskedTextBox1, 5000)  
           e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="78244-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78244-126">See Also</span></span>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [<span data-ttu-id="78244-127">Controllo MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="78244-127">MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/maskedtextbox-control-windows-forms.md)
