---
title: Cenni preliminari sul controllo TextBox (Windows Form)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932548"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="6c335-102">Cenni preliminari sul controllo TextBox (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="6c335-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="6c335-103">Le caselle di testo di Windows Form vengono usate per ottenere l'input da parte dell'utente o per visualizzare il testo.</span><span class="sxs-lookup"><span data-stu-id="6c335-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="6c335-104">Il <xref:System.Windows.Forms.TextBox> controllo viene generalmente utilizzato per il testo modificabile, anche se può essere reso anche sola lettura.</span><span class="sxs-lookup"><span data-stu-id="6c335-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="6c335-105">Le caselle di testo possono visualizzare più righe, a capo automatico per le dimensioni del controllo e aggiungere la formattazione di base.</span><span class="sxs-lookup"><span data-stu-id="6c335-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="6c335-106">Il <xref:System.Windows.Forms.TextBox> controllo fornisce un unico stile di formattazione per il testo visualizzato o inserito nel controllo.</span><span class="sxs-lookup"><span data-stu-id="6c335-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="6c335-107">Per visualizzare più tipi di testo formattato, usare il <xref:System.Windows.Forms.RichTextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="6c335-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="6c335-108">Per altre informazioni, vedere [Cenni preliminari sul controllo RichTextBox](richtextbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="6c335-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="6c335-109">Utilizzo del controllo casella di testo</span><span class="sxs-lookup"><span data-stu-id="6c335-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="6c335-110">Il testo visualizzato dal controllo è contenuto nel <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6c335-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="6c335-111">Per impostazione predefinita, è possibile immettere fino a 2048 caratteri in una casella di testo.</span><span class="sxs-lookup"><span data-stu-id="6c335-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="6c335-112">Se si impostano i <xref:System.Windows.Forms.TextBox.Multiline%2A> proprietà `true`, è possibile immettere fino a 32 KB del testo.</span><span class="sxs-lookup"><span data-stu-id="6c335-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="6c335-113">Il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà può essere impostata in fase di progettazione con la finestra Proprietà, in fase di esecuzione nel codice o tramite l'input dell'utente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6c335-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="6c335-114">Il contenuto corrente di una casella di testo può essere recuperato in fase di esecuzione leggendo il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="6c335-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="6c335-115">Esempio di codice seguente imposta il testo nel controllo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6c335-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="6c335-116">Il `InitializeMyControl` procedure non verrà eseguiti automaticamente; deve essere chiamato.</span><span class="sxs-lookup"><span data-stu-id="6c335-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c335-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c335-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="6c335-118">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6c335-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="6c335-119">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6c335-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="6c335-120">Procedura: Creare una casella di testo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="6c335-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="6c335-121">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="6c335-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="6c335-122">Procedura: Selezionare il testo nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="6c335-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="6c335-123">Procedura: Visualizzare più righe nel controllo TextBox Windows Form</span><span class="sxs-lookup"><span data-stu-id="6c335-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="6c335-124">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="6c335-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
