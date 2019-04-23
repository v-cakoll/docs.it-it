---
title: 'Procedura: Impostare il testo visualizzato da un controllo di Windows Forms'
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
ms.openlocfilehash: 59570af89e6236e3c13866d45dc5361d52b84274
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308523"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="094a0-102">Procedura: Impostare il testo visualizzato da un controllo di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="094a0-102">How to: Set the Text Displayed by a Windows Forms Control</span></span>
<span data-ttu-id="094a0-103">I controlli Windows Form in genere visualizzano il testo relativo alla funzione principale del controllo.</span><span class="sxs-lookup"><span data-stu-id="094a0-103">Windows Forms controls usually display some text that is related to the primary function of the control.</span></span> <span data-ttu-id="094a0-104">Un controllo <xref:System.Windows.Forms.Button>, ad esempio, solitamente visualizza una didascalia indicante l'azione che verrà eseguita quando si sceglie il pulsante.</span><span class="sxs-lookup"><span data-stu-id="094a0-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed when the button is clicked.</span></span> <span data-ttu-id="094a0-105">Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="094a0-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="094a0-106">È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="094a0-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span> <span data-ttu-id="094a0-107">È anche possibile impostare il testo nella finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="094a0-107">You can also set the text using the designer.</span></span>  <span data-ttu-id="094a0-108">Vedere anche [come: Creare le chiavi di accesso per Windows Form usando la finestra di progettazione di controlli](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [come: Impostare il testo visualizzato da un Windows Form mediante la finestra di progettazione](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [come: Impostare l'immagine visualizzata da un Windows Form mediante la finestra di progettazione](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="094a0-108">Also see [How to: Create Access Keys for Windows Forms Controls Using the Designer](how-to-create-access-keys-for-windows-forms-controls-using-the-designer.md), [How to: Set the Text Displayed by a Windows Forms Control Using the Designer](how-to-set-the-text-displayed-by-a-windows-forms-control-using-the-designer.md), [How to: Set the Image Displayed by a Windows Forms Control Using the Designer](how-to-set-the-image-displayed-by-a-windows-forms-control-using-the-designer.md).</span></span>  
  
### <a name="to-set-the-text-displayed-by-a-control-programmatically"></a><span data-ttu-id="094a0-109">Per impostare il testo visualizzato da un controllo a livello di codice</span><span class="sxs-lookup"><span data-stu-id="094a0-109">To set the text displayed by a control programmatically</span></span>  
  
1. <span data-ttu-id="094a0-110">Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su una stringa.</span><span class="sxs-lookup"><span data-stu-id="094a0-110">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>  
  
     <span data-ttu-id="094a0-111">Per creare un tasto di scelta sottolineato, includere una e commerciale (&) alla lettera che sarà la chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="094a0-111">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>  
  
2. <span data-ttu-id="094a0-112">Impostare la proprietà <xref:System.Windows.Forms.Control.Font%2A> su un oggetto di tipo <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="094a0-112">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>  
  
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
    >  <span data-ttu-id="094a0-113">È possibile usare un carattere di escape per visualizzare un carattere speciale in elementi dell'interfaccia utente in cui tale carattere verrebbe in genere interpretato in modo diverso, ad esempio nelle voci di menu.</span><span class="sxs-lookup"><span data-stu-id="094a0-113">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="094a0-114">Ad esempio, la riga di codice seguente imposta il testo della voce di menu da leggere "& Now For Something completamente diverso":</span><span class="sxs-lookup"><span data-stu-id="094a0-114">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>  
  
    ```vb  
    MPMenuItem.Text = "&& Now For Something Completely Different"  
    ```  
  
    ```csharp  
    mpMenuItem.Text = "&& Now For Something Completely Different";  
    ```  
  
    ```cpp  
    mpMenuItem->Text = "&& Now For Something Completely Different";  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="094a0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="094a0-115">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="094a0-116">Procedura: Creare le chiavi di accesso per i controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="094a0-116">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="094a0-117">Procedura: Rispondere alle selezioni dei pulsanti di Windows Form</span><span class="sxs-lookup"><span data-stu-id="094a0-117">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
