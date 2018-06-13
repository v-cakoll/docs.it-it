---
title: 'Procedura: impostare il testo visualizzato da un controllo di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: d39b0b7ccf95f0da22086a72aa2cee424d7ea8ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535613"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="146ea-102">Procedura: impostare il testo visualizzato da un controllo di Windows Form</span><span class="sxs-lookup"><span data-stu-id="146ea-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="146ea-103">I controlli Windows Form in genere visualizzano il testo relativo alla funzione principale del controllo.</span><span class="sxs-lookup"><span data-stu-id="146ea-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="146ea-104">Un controllo <xref:System.Windows.Forms.Button>, ad esempio, solitamente visualizza una didascalia indicante l'azione che verrà eseguita quando si sceglie il pulsante.</span><span class="sxs-lookup"><span data-stu-id="146ea-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="146ea-105">Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="146ea-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="146ea-106">È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="146ea-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="146ea-107">È anche possibile impostare il testo nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="146ea-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="146ea-108">Vedere anche [procedura: creare accesso chiavi per Windows Form controlli usando la finestra di progettazione](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [come: impostare il testo visualizzato da un controllo Form Windows mediante la finestra di progettazione](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [come: impostare l'immagine Visualizzato da un controllo utilizzando la finestra di progettazione Windows Form](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="146ea-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](http://msdn.microsoft.com/library/ms233673\(v=vs.110\)), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233665\(v=vs.110\)), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](http://msdn.microsoft.com/library/ms233656\(v=vs.110\)).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="146ea-109">Per impostare il testo visualizzato da un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="146ea-109">To set the text displayed by a control programmatically</span></span>  
  
1.  <span data-ttu-id="146ea-110">Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su una stringa.</span><span class="sxs-lookup"><span data-stu-id="146ea-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="146ea-111">Per creare un tasto di scelta sottolineato, includere una e commerciale (&) prima della lettera che corrisponderà al tasto di scelta.</span><span class="sxs-lookup"><span data-stu-id="146ea-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2.  <span data-ttu-id="146ea-112">Impostare la proprietà <xref:System.Windows.Forms.Control.Font%2A> su un oggetto di tipo <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="146ea-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
    ```vb  
    Button1.Text = "Click here to save changes"  
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)  
    ```  
  
    ```csharp  
    button1.Text = "Click here to save changes";  
    button1.Font = new Font("Arial", 10, FontStyle.Bold,  
       GraphicsUnit.Point);  
    ```  
  
    ```cpp  
    button1->Text = "Click here to save changes";  
    button1->Font = new System::Drawing::Font("Arial",  
       10, FontStyle::Bold, GraphicsUnit::Point);  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="146ea-113">È possibile usare un carattere di escape per visualizzare un carattere speciale in elementi dell'interfaccia utente in cui tale carattere verrebbe in genere interpretato in modo diverso, ad esempio nelle voci di menu.</span><span class="sxs-lookup"><span data-stu-id="146ea-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="146ea-114">Nella riga di codice seguente, ad esempio, il testo della voce di menu viene impostato in modo che appaia come "& Now For Something Completely Different":</span><span class="sxs-lookup"><span data-stu-id="146ea-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="146ea-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="146ea-115">See Also</span></span>  
 <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="146ea-116">Procedura: Creare tasti di scelta per i controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="146ea-116">How to: Create Access Keys for Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [<span data-ttu-id="146ea-117">Procedura: Rispondere alla selezione dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="146ea-117">How to: Respond to Windows Forms Button Clicks</span></span>](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
