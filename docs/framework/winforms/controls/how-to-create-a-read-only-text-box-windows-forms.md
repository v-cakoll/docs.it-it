---
title: 'Procedura: creare una casella di testo in sola lettura (Windows Form)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 06e03f67bd1f084b30bce85c3d81ad7b8c97a1b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530146"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="cc390-102">Procedura: creare una casella di testo in sola lettura (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="cc390-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="cc390-103">È possibile trasformare una casella di testo modificabile Windows Form in un controllo di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="cc390-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="cc390-104">Ad esempio, la casella di testo potrebbe visualizzare un valore che viene modificato in genere, ma potrebbe non essere al momento, a causa dello stato dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cc390-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="cc390-105">Per creare una casella di testo di sola lettura</span><span class="sxs-lookup"><span data-stu-id="cc390-105">To create a read-only text box</span></span>  
  
1.  <span data-ttu-id="cc390-106">Impostare il <xref:System.Windows.Forms.TextBox> del controllo <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà `true`.</span><span class="sxs-lookup"><span data-stu-id="cc390-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="cc390-107">Con la proprietà impostata su `true`, gli utenti possono comunque scorrere ed evidenziare il testo in una casella di testo non sono consentite modifiche.</span><span class="sxs-lookup"><span data-stu-id="cc390-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="cc390-108">Oggetto **copia** comando è funzionale in una casella di testo, ma **Taglia** e **Incolla** comandi non sono.</span><span class="sxs-lookup"><span data-stu-id="cc390-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc390-109">Il <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> proprietà influisce solo sull'interazione dell'utente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cc390-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="cc390-110">È possibile modificare contenuto casella di testo a livello di codice in fase di esecuzione, modificando il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà della casella di testo.</span><span class="sxs-lookup"><span data-stu-id="cc390-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc390-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc390-111">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 [<span data-ttu-id="cc390-112">Cenni preliminari sul controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="cc390-112">TextBox Control Overview</span></span>](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [<span data-ttu-id="cc390-113">Procedura: Controllare il punto di inserimento in un controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cc390-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [<span data-ttu-id="cc390-114">Procedura: Creare una casella di testo Password con il controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cc390-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="cc390-115">Procedura: Inserire virgolette in una stringa</span><span class="sxs-lookup"><span data-stu-id="cc390-115">How to: Put Quotation Marks in a String</span></span>](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [<span data-ttu-id="cc390-116">Procedura: Selezionare testo nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cc390-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="cc390-117">Procedura: Visualizzare più righe nel controllo TextBox di Windows Form</span><span class="sxs-lookup"><span data-stu-id="cc390-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [<span data-ttu-id="cc390-118">Controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="cc390-118">TextBox Control</span></span>](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
