---
title: 'Procedura: inserire virgolette in una stringa'
description: Informazioni su come inserire le virgolette in una stringa di testo. Viene inoltre illustrato come utilizzare il campo quote come costante.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- quotation marks
- TextBox control [Windows Forms], displaying quotation marks
- quotation marks [Windows Forms], adding to strings in text boxes
ms.assetid: 68bdc3f3-4177-4eab-99cd-cac17a82b515
ms.openlocfilehash: 08a3e2ab5662cbbf7825890ab430fddcd7b4a9ce
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903623"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="3ef50-104">Procedura: inserire virgolette in una stringa (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="3ef50-104">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="3ef50-105">In alcuni casi è possibile racchiudere tra virgolette (" ") una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="3ef50-105">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="3ef50-106">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3ef50-106">For example:</span></span>  
  
 <span data-ttu-id="3ef50-107">Ha detto, "Meritate un treat!"</span><span class="sxs-lookup"><span data-stu-id="3ef50-107">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="3ef50-108">In alternativa, è anche possibile usare il <xref:Microsoft.VisualBasic.ControlChars.Quote> campo come costante.</span><span class="sxs-lookup"><span data-stu-id="3ef50-108">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="3ef50-109">Per inserire le virgolette in una stringa nel codice</span><span class="sxs-lookup"><span data-stu-id="3ef50-109">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="3ef50-110">In Visual Basic inserire due virgolette in una riga come virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="3ef50-110">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="3ef50-111">In Visual C# e Visual C++ Inserire la sequenza di escape \\ "come virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="3ef50-111">In Visual C# and Visual C++, insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="3ef50-112">Ad esempio, per creare la stringa precedente, usare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3ef50-112">For example, to create the preceding string, use the following code.</span></span>  
  
    ```vb  
    Private Sub InsertQuote()  
       TextBox1.Text = "She said, ""You deserve a treat!"" "  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertQuote(){  
       textBox1.Text = "She said, \"You deserve a treat!\" ";  
    }  
    ```  
  
    ```cpp  
    private:  
       void InsertQuote()  
       {  
          textBox1->Text = "She said, \"You deserve a treat!\" ";  
       }  
    ```  
  
     <span data-ttu-id="3ef50-113">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3ef50-113">-or-</span></span>  
  
2. <span data-ttu-id="3ef50-114">Inserire il carattere ASCII o Unicode per una virgoletta.</span><span class="sxs-lookup"><span data-stu-id="3ef50-114">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="3ef50-115">In Visual Basic usare il carattere ASCII (34).</span><span class="sxs-lookup"><span data-stu-id="3ef50-115">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="3ef50-116">In Visual C# usare il carattere Unicode (\u0022).</span><span class="sxs-lookup"><span data-stu-id="3ef50-116">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
    ```vb  
    Private Sub InsertAscii()  
       TextBox1.Text = "She said, " & Chr(34) & "You deserve a treat!" & Chr(34)  
    End Sub  
    ```  
  
    ```csharp  
    private void InsertAscii(){  
       textBox1.Text = "She said, " + '\u0022' + "You deserve a treat!" + '\u0022';  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="3ef50-117">In questo esempio, non è possibile usare \u0022 perché non è possibile usare un nome di carattere universale che indica un carattere nel set di caratteri di base.</span><span class="sxs-lookup"><span data-stu-id="3ef50-117">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="3ef50-118">In caso contrario, si otterrebbe C3851.</span><span class="sxs-lookup"><span data-stu-id="3ef50-118">Otherwise, you produce C3851.</span></span> <span data-ttu-id="3ef50-119">Per altre informazioni, vedere l'[L'errore del compilatore C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="3ef50-119">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="3ef50-120">-oppure-</span><span class="sxs-lookup"><span data-stu-id="3ef50-120">-or-</span></span>  
  
3. <span data-ttu-id="3ef50-121">È anche possibile definire una costante per il carattere e usarlo se necessario.</span><span class="sxs-lookup"><span data-stu-id="3ef50-121">You can also define a constant for the character, and use it where needed.</span></span>  
  
    ```vb  
    Const quote As String = """"  
    TextBox1.Text = "She said, " & quote & "You deserve a treat!" & quote  
    ```  
  
    ```csharp  
    const string quote = "\"";  
    textBox1.Text = "She said, " + quote +  "You deserve a treat!"+ quote ;  
    ```  
  
    ```cpp  
    const String^ quote = "\"";  
    textBox1->Text = String::Concat("She said, ",  
       const_cast<String^>(quote), "You deserve a treat!",  
       const_cast<String^>(quote));  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3ef50-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ef50-122">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="3ef50-123">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="3ef50-123">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="3ef50-124">Procedura: controllare il punto di inserimento in un controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ef50-124">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="3ef50-125">Procedura: creare una casella di testo Password con il controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ef50-125">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3ef50-126">Procedura: creare una casella di testo in sola lettura</span><span class="sxs-lookup"><span data-stu-id="3ef50-126">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="3ef50-127">Procedura: selezionare testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ef50-127">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3ef50-128">Procedura: visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="3ef50-128">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="3ef50-129">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="3ef50-129">TextBox Control</span></span>](textbox-control-windows-forms.md)
