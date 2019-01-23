---
title: 'Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TextBox control [Windows Forms], entering passwords
- password boxes [Windows Forms], creating
- PasswordChar property in text boxes
- passwords [Windows Forms], input mask
- passwords [Windows Forms], password text box
ms.assetid: d105d6b9-3d50-44cd-80d8-2c0e2f486727
ms.openlocfilehash: b6fe0e615cc5bbd0f549505ed9e6add8d7a51433
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523987"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="4b48a-102">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4b48a-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>
<span data-ttu-id="4b48a-103">Una casella della password è una casella di testo di Windows Form che consente di visualizzare caratteri segnaposto mentre un utente digita una stringa.</span><span class="sxs-lookup"><span data-stu-id="4b48a-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>  
  
### <a name="to-create-a-password-text-box"></a><span data-ttu-id="4b48a-104">Per creare una casella di testo password</span><span class="sxs-lookup"><span data-stu-id="4b48a-104">To create a password text box</span></span>  
  
1.  <span data-ttu-id="4b48a-105">Impostare il <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà del <xref:System.Windows.Forms.TextBox> controllo a un carattere specifico.</span><span class="sxs-lookup"><span data-stu-id="4b48a-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>  
  
     <span data-ttu-id="4b48a-106">Il <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà specifica il carattere visualizzato nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="4b48a-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="4b48a-107">Ad esempio, se si desidera che gli asterischi visualizzati nella casella della password, specificare \* per il <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b48a-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="4b48a-108">Quindi, indipendentemente dal fatto che un utente digita nella casella di testo di carattere, viene visualizzato un asterisco.</span><span class="sxs-lookup"><span data-stu-id="4b48a-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>  
  
2.  <span data-ttu-id="4b48a-109">(Facoltativo) Impostare il <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="4b48a-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="4b48a-110">La proprietà determina il numero di caratteri può essere digitato nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="4b48a-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="4b48a-111">Se viene superata la lunghezza massima, il sistema emette un segnale acustico e la casella di testo non accetta ulteriori caratteri.</span><span class="sxs-lookup"><span data-stu-id="4b48a-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="4b48a-112">Si noti che non è possibile eseguire questa operazione come la lunghezza massima di una password possono essere utilizzata da pirati informatici che tentano di indovinare la password.</span><span class="sxs-lookup"><span data-stu-id="4b48a-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>  
  
     <span data-ttu-id="4b48a-113">Esempio di codice seguente viene illustrato come inizializzare una casella di testo che accetta una stringa fino a 14 caratteri e visualizza un asterisco al posto della stringa.</span><span class="sxs-lookup"><span data-stu-id="4b48a-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="4b48a-114">Il `InitializeMyControl` procedure non verrà eseguiti automaticamente; deve essere chiamato.</span><span class="sxs-lookup"><span data-stu-id="4b48a-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="4b48a-115">Uso di <xref:System.Windows.Forms.TextBox.PasswordChar%2A> proprietà in una casella di testo per assicurarsi che ad altri utenti non saranno in grado di determinare una password dell'utente se si attengano all'utente di immettere lo.</span><span class="sxs-lookup"><span data-stu-id="4b48a-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="4b48a-116">Questa misura di sicurezza non copre una sorta di archiviazione o la trasmissione della password che possono verificarsi a causa della logica dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4b48a-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="4b48a-117">Poiché il testo immesso non è crittografato in alcun modo, è opportuno considerarlo come qualsiasi altro tipo di dati riservati.</span><span class="sxs-lookup"><span data-stu-id="4b48a-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="4b48a-118">Anche se non fa di conseguenza, la password verrà comunque considerata come una stringa di testo normale (a meno che non è stato implementato alcune misure di sicurezza aggiuntiva).</span><span class="sxs-lookup"><span data-stu-id="4b48a-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>  
  
    ```vb  
    Private Sub InitializeMyControl()  
       ' Set to no text.  
       TextBox1.Text = ""  
       ' The password character is an asterisk.  
       TextBox1.PasswordChar = "*"  
       ' The control will allow no more than 14 characters.  
       TextBox1.MaxLength = 14  
    End Sub  
    ```  
  
    ```csharp  
    private void InitializeMyControl()  
    {  
       // Set to no text.  
       textBox1.Text = "";  
       // The password character is an asterisk.  
       textBox1.PasswordChar = '*';  
       // The control will allow no more than 14 characters.  
       textBox1.MaxLength = 14;  
    }  
    ```  
  
    ```cpp  
    private:  
       void InitializeMyControl()  
       {  
          // Set to no text.  
          textBox1->Text = "";  
          // The password character is an asterisk.  
          textBox1->PasswordChar = '*';  
          // The control will allow no more than 14 characters.  
          textBox1->MaxLength = 14;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4b48a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b48a-119">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="4b48a-120">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="4b48a-120">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="4b48a-121">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="4b48a-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="4b48a-122">Procedura: Creare una casella di testo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="4b48a-122">How to: Create a Read-Only Text Box</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="4b48a-123">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="4b48a-123">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="4b48a-124">Procedura: Selezionare il testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="4b48a-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4b48a-125">Procedura: Visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="4b48a-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="4b48a-126">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="4b48a-126">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
