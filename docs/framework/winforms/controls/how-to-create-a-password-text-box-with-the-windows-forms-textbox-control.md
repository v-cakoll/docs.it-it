---
title: Crea una casella di testo password con il controllo TextBox
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
ms.openlocfilehash: ff4706a736d15f14cf437c808219e9088773dc6d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731290"
---
# <a name="how-to-create-a-password-text-box-with-the-windows-forms-textbox-control"></a><span data-ttu-id="000ff-102">Procedura: creare una casella di testo Password con il controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="000ff-102">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>

<span data-ttu-id="000ff-103">Una casella password è una casella di testo Windows Forms che Visualizza i caratteri segnaposto mentre un utente digita una stringa.</span><span class="sxs-lookup"><span data-stu-id="000ff-103">A password box is a Windows Forms text box that displays placeholder characters while a user types a string.</span></span>

### <a name="to-create-a-password-text-box"></a><span data-ttu-id="000ff-104">Per creare una casella di testo password</span><span class="sxs-lookup"><span data-stu-id="000ff-104">To create a password text box</span></span>

1. <span data-ttu-id="000ff-105">Impostare la proprietà <xref:System.Windows.Forms.TextBox.PasswordChar%2A> del controllo <xref:System.Windows.Forms.TextBox> su un carattere specifico.</span><span class="sxs-lookup"><span data-stu-id="000ff-105">Set the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property of the <xref:System.Windows.Forms.TextBox> control to a specific character.</span></span>

    <span data-ttu-id="000ff-106">La proprietà <xref:System.Windows.Forms.TextBox.PasswordChar%2A> specifica il carattere visualizzato nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="000ff-106">The <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property specifies the character displayed in the text box.</span></span> <span data-ttu-id="000ff-107">Se ad esempio si desidera visualizzare gli asterischi nella casella password, specificare \* per la proprietà <xref:System.Windows.Forms.TextBox.PasswordChar%2A> nel Finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="000ff-107">For example, if you want asterisks displayed in the password box, specify \* for the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property in the Properties window.</span></span> <span data-ttu-id="000ff-108">Quindi, indipendentemente dal carattere che un utente digita nella casella di testo, viene visualizzato un asterisco.</span><span class="sxs-lookup"><span data-stu-id="000ff-108">Then, regardless of what character a user types in the text box, an asterisk is displayed.</span></span>

2. <span data-ttu-id="000ff-109">Opzionale Impostare la proprietà <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A>.</span><span class="sxs-lookup"><span data-stu-id="000ff-109">(Optional) Set the <xref:System.Windows.Forms.TextBoxBase.MaxLength%2A> property.</span></span> <span data-ttu-id="000ff-110">La proprietà determina il numero di caratteri che possono essere digitati nella casella di testo.</span><span class="sxs-lookup"><span data-stu-id="000ff-110">The property determines how many characters can be typed in the text box.</span></span> <span data-ttu-id="000ff-111">Se viene superata la lunghezza massima, il sistema emette un segnale acustico e la casella di testo non accetta più caratteri.</span><span class="sxs-lookup"><span data-stu-id="000ff-111">If the maximum length is exceeded, the system emits a beep and the text box does not accept any more characters.</span></span> <span data-ttu-id="000ff-112">Si noti che è possibile che non si desideri eseguire questa operazione perché la lunghezza massima di una password può essere usata per gli hacker che tentano di indovinare la password.</span><span class="sxs-lookup"><span data-stu-id="000ff-112">Note that you may not wish to do this as the maximum length of a password may be of use to hackers who are trying to guess the password.</span></span>

    <span data-ttu-id="000ff-113">Nell'esempio di codice seguente viene illustrato come inizializzare una casella di testo che accetterà una stringa con un massimo di 14 caratteri e visualizzerà gli asterischi al posto della stringa.</span><span class="sxs-lookup"><span data-stu-id="000ff-113">The following code example shows how to initialize a text box that will accept a string up to 14 characters long and display asterisks in place of the string.</span></span> <span data-ttu-id="000ff-114">La procedura di `InitializeMyControl` non verrà eseguita automaticamente. deve essere chiamato.</span><span class="sxs-lookup"><span data-stu-id="000ff-114">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="000ff-115">Utilizzando la proprietà <xref:System.Windows.Forms.TextBox.PasswordChar%2A> in una casella di testo è possibile garantire che altri utenti non possano determinare la password di un utente se osservano l'utente che lo immette.</span><span class="sxs-lookup"><span data-stu-id="000ff-115">Using the <xref:System.Windows.Forms.TextBox.PasswordChar%2A> property on a text box can help ensure that other people will not be able to determine a user's password if they observe the user entering it.</span></span> <span data-ttu-id="000ff-116">Questa misura di sicurezza non copre alcun tipo di archiviazione o trasmissione della password che può verificarsi a causa della logica dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="000ff-116">This security measure does not cover any sort of storage or transmission of the password that can occur due to your application logic.</span></span> <span data-ttu-id="000ff-117">Poiché il testo immesso non è crittografato in alcun modo, è consigliabile considerarlo come tutti gli altri dati riservati.</span><span class="sxs-lookup"><span data-stu-id="000ff-117">Because the text entered is not encrypted in any way, you should treat it as you would any other confidential data.</span></span> <span data-ttu-id="000ff-118">Anche se non viene visualizzato come tale, la password viene comunque considerata come una stringa di testo normale (a meno che non siano state implementate misure di sicurezza aggiuntive).</span><span class="sxs-lookup"><span data-stu-id="000ff-118">Even though it does not appear as such, the password is still being treated as a plain-text string (unless you have implemented some additional security measure).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="000ff-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="000ff-119">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="000ff-120">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="000ff-120">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="000ff-121">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="000ff-121">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="000ff-122">Procedura: Creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="000ff-122">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="000ff-123">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="000ff-123">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="000ff-124">Procedura: Selezionare testo nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="000ff-124">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="000ff-125">Procedura: Visualizzare più righe nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="000ff-125">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="000ff-126">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="000ff-126">TextBox Control</span></span>](textbox-control-windows-forms.md)
