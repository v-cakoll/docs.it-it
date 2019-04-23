---
title: 'Procedura: Inserire virgolette in una stringa (Windows Form)'
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
ms.openlocfilehash: 14180f0326b38872f5d1b112c3d9a87022fb79e9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59328062"
---
# <a name="how-to-put-quotation-marks-in-a-string-windows-forms"></a><span data-ttu-id="63673-102">Procedura: Inserire virgolette in una stringa (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="63673-102">How to: Put Quotation Marks in a String (Windows Forms)</span></span>
<span data-ttu-id="63673-103">In alcuni casi è possibile racchiudere tra virgolette (" ") una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="63673-103">Sometimes you might want to place quotation marks (" ") in a string of text.</span></span> <span data-ttu-id="63673-104">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="63673-104">For example:</span></span>  
  
 <span data-ttu-id="63673-105">Ha detto, "Meritate un treat!"</span><span class="sxs-lookup"><span data-stu-id="63673-105">She said, "You deserve a treat!"</span></span>  
  
 <span data-ttu-id="63673-106">In alternativa, è anche possibile usare il <xref:Microsoft.VisualBasic.ControlChars.Quote> campo come costante.</span><span class="sxs-lookup"><span data-stu-id="63673-106">As an alternative, you can also use the <xref:Microsoft.VisualBasic.ControlChars.Quote> field as a constant.</span></span>  
  
### <a name="to-place-quotation-marks-in-a-string-in-your-code"></a><span data-ttu-id="63673-107">Per inserire le virgolette in una stringa nel codice</span><span class="sxs-lookup"><span data-stu-id="63673-107">To place quotation marks in a string in your code</span></span>  
  
1. <span data-ttu-id="63673-108">In Visual Basic, inserire due virgolette in una riga come virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="63673-108">In Visual Basic, insert two quotation marks in a row as an embedded quotation mark.</span></span> <span data-ttu-id="63673-109">Nell'oggetto visivo C# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], inserire la sequenza di escape \\"come virgolette incorporate.</span><span class="sxs-lookup"><span data-stu-id="63673-109">In Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)], insert the escape sequence \\" as an embedded quotation mark.</span></span> <span data-ttu-id="63673-110">Ad esempio, per creare la stringa precedente, usare il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="63673-110">For example, to create the preceding string, use the following code.</span></span>  
  
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
  
     <span data-ttu-id="63673-111">-oppure-</span><span class="sxs-lookup"><span data-stu-id="63673-111">-or-</span></span>  
  
2. <span data-ttu-id="63673-112">Inserire il carattere ASCII o Unicode per una virgoletta.</span><span class="sxs-lookup"><span data-stu-id="63673-112">Insert the ASCII or Unicode character for a quotation mark.</span></span> <span data-ttu-id="63673-113">In Visual Basic, usare il carattere ASCII (34).</span><span class="sxs-lookup"><span data-stu-id="63673-113">In Visual Basic, use the ASCII character (34).</span></span> <span data-ttu-id="63673-114">Nell'oggetto visivo C#, usare il carattere Unicode (\u0022).</span><span class="sxs-lookup"><span data-stu-id="63673-114">In Visual C#, use the Unicode character (\u0022).</span></span>  
  
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
    >  <span data-ttu-id="63673-115">In questo esempio, non è possibile usare \u0022 perché non è possibile usare un nome di carattere universale che indica un carattere nel set di caratteri di base.</span><span class="sxs-lookup"><span data-stu-id="63673-115">In this example, you cannot use \u0022 because you cannot use a universal character name that designates a character in the basic character set.</span></span> <span data-ttu-id="63673-116">In caso contrario, si otterrebbe C3851.</span><span class="sxs-lookup"><span data-stu-id="63673-116">Otherwise, you produce C3851.</span></span> <span data-ttu-id="63673-117">Per altre informazioni, vedere l'[L'errore del compilatore C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span><span class="sxs-lookup"><span data-stu-id="63673-117">For more information, see [Compiler Error C3851](/cpp/error-messages/compiler-errors-2/compiler-error-c3851).</span></span>  
  
     <span data-ttu-id="63673-118">-oppure-</span><span class="sxs-lookup"><span data-stu-id="63673-118">-or-</span></span>  
  
3. <span data-ttu-id="63673-119">È anche possibile definire una costante per il carattere e usarlo se necessario.</span><span class="sxs-lookup"><span data-stu-id="63673-119">You can also define a constant for the character, and use it where needed.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="63673-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63673-120">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:Microsoft.VisualBasic.ControlChars.Quote>
- [<span data-ttu-id="63673-121">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="63673-121">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="63673-122">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="63673-122">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="63673-123">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="63673-123">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="63673-124">Procedura: Creare una casella di testo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="63673-124">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="63673-125">Procedura: Selezionare il testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="63673-125">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="63673-126">Procedura: Visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="63673-126">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="63673-127">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="63673-127">TextBox Control</span></span>](textbox-control-windows-forms.md)
