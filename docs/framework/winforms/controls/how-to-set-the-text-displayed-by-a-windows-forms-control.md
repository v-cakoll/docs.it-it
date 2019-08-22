---
title: 'Procedura: Impostare il testo visualizzato da un controllo di Windows Forms'
ms.date: 08/20/2019
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
ms.openlocfilehash: 887aa5ec9b97770903cd87459d6df5adc3f7ddf0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666147"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="6f9c5-102">Procedura: Imposta il testo visualizzato da un controllo Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f9c5-102">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="6f9c5-103">I controlli Windows Forms in genere visualizzano testo correlato alla funzione primaria del controllo.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-103">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="6f9c5-104">Un <xref:System.Windows.Forms.Button> controllo, ad esempio, Visualizza in genere una didascalia che indica l'azione che verrà eseguita se si fa clic sul pulsante.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="6f9c5-105">Per tutti i controlli, il testo può essere impostato o restituito mediante la proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="6f9c5-106">È possibile modificare il tipo di carattere usando la proprietà <xref:System.Windows.Forms.Control.Font%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="6f9c5-107">È anche possibile impostare il testo usando la [finestra di progettazione](#designer).</span><span class="sxs-lookup"><span data-stu-id="6f9c5-107">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="6f9c5-108">A livello</span><span class="sxs-lookup"><span data-stu-id="6f9c5-108">Programmatic</span></span>

1. <span data-ttu-id="6f9c5-109">Impostare la proprietà <xref:System.Windows.Forms.Control.Text%2A> su una stringa.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-109">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="6f9c5-110">Per creare una chiave di accesso sottolineata, include una e commerciale (&) prima della lettera che sarà il tasto di accesso.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-110">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="6f9c5-111">Impostare la proprietà <xref:System.Windows.Forms.Control.Font%2A> su un oggetto di tipo <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-111">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="6f9c5-112">È possibile usare un carattere di escape per visualizzare un carattere speciale in elementi dell'interfaccia utente in cui tale carattere verrebbe in genere interpretato in modo diverso, ad esempio nelle voci di menu.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-112">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="6f9c5-113">La riga di codice seguente, ad esempio, imposta il testo della voce di menu in modo da leggere "& ora per qualcosa di completamente diverso":</span><span class="sxs-lookup"><span data-stu-id="6f9c5-113">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="6f9c5-114">Designer</span><span class="sxs-lookup"><span data-stu-id="6f9c5-114">Designer</span></span>

1. <span data-ttu-id="6f9c5-115">Nella finestra **Proprietà** di Visual Studio impostare la proprietà **Text** del controllo su una stringa appropriata.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-115">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="6f9c5-116">Per creare un tasto di scelta rapida sottolineato, include una e commerciale (&) prima della lettera che sarà il tasto di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-116">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="6f9c5-117">Nella finestra **Proprietà** selezionare il pulsante con i puntini![di sospensione (pulsante con i puntini di sospensione (..](./media/visual-studio-ellipsis-button.png).) nella finestra proprietà di Visual Studio) accanto alla proprietà **font** .</span><span class="sxs-lookup"><span data-stu-id="6f9c5-117">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="6f9c5-118">Nella finestra di dialogo tipo di carattere standard selezionare il tipo di carattere, lo stile del carattere, le dimensioni, gli effetti (ad esempio, l'attacco o la sottolineatura) e lo script desiderato.</span><span class="sxs-lookup"><span data-stu-id="6f9c5-118">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f9c5-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f9c5-119">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="6f9c5-120">Procedura: Creare chiavi di accesso per i controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f9c5-120">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="6f9c5-121">Procedura: Rispondi a Windows Forms clic sui pulsanti</span><span class="sxs-lookup"><span data-stu-id="6f9c5-121">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
