---
title: 'Procedura: visualizzare pulsanti di opzione in un controllo MenuStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735520"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="b578d-102">Procedura: Visualizzare pulsanti di opzione in un controllo MenuStrip (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="b578d-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>

<span data-ttu-id="b578d-103">I pulsanti di opzione, noti anche come pulsanti di opzione, sono simili alle caselle di controllo, ad eccezione del fatto che gli utenti possono selezionare solo uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="b578d-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="b578d-104">Sebbene per impostazione predefinita la classe <xref:System.Windows.Forms.ToolStripMenuItem> non fornisca il comportamento del pulsante di opzione, la classe fornisce il comportamento della casella di controllo che è possibile personalizzare per implementare il comportamento del pulsante di opzione per le voci di menu in un controllo <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="b578d-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>

<span data-ttu-id="b578d-105">Quando la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà di una voce di menu è `true`, gli utenti possono fare clic sull'elemento per visualizzare o disabilitare la visualizzazione di un segno di spunta.</span><span class="sxs-lookup"><span data-stu-id="b578d-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="b578d-106">La proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> indica lo stato corrente dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b578d-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="b578d-107">Per implementare il comportamento di base dei pulsanti di opzione, è necessario assicurarsi che, quando si seleziona un elemento, impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> per l'elemento selezionato in precedenza su `false`.</span><span class="sxs-lookup"><span data-stu-id="b578d-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>

<span data-ttu-id="b578d-108">Nelle procedure seguenti viene descritto come implementare questa e funzionalità aggiuntiva in una classe che eredita la classe <xref:System.Windows.Forms.ToolStripMenuItem>.</span><span class="sxs-lookup"><span data-stu-id="b578d-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="b578d-109">La classe `ToolStripRadioButtonMenuItem` esegue l'override di membri quali <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> e <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> per fornire il comportamento di selezione e l'aspetto dei pulsanti di opzione.</span><span class="sxs-lookup"><span data-stu-id="b578d-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="b578d-110">Inoltre, questa classe esegue l'override della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> in modo che le opzioni di un sottomenu siano disabilitate, a meno che l'elemento padre non sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="b578d-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>

## <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="b578d-111">Per implementare il comportamento di selezione dei pulsanti di opzione</span><span class="sxs-lookup"><span data-stu-id="b578d-111">To implement option-button selection behavior</span></span>

1. <span data-ttu-id="b578d-112">Inizializzare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> su `true` per abilitare la selezione dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b578d-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. <span data-ttu-id="b578d-113">Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> per cancellare la selezione dell'elemento selezionato in precedenza quando viene selezionato un nuovo elemento.</span><span class="sxs-lookup"><span data-stu-id="b578d-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. <span data-ttu-id="b578d-114">Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> per assicurarsi che fare clic su un elemento già selezionato non cancelli la selezione.</span><span class="sxs-lookup"><span data-stu-id="b578d-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="b578d-115">Per modificare l'aspetto degli elementi del pulsante di opzione</span><span class="sxs-lookup"><span data-stu-id="b578d-115">To modify the appearance of the option-button items</span></span>

1. <span data-ttu-id="b578d-116">Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> per sostituire il segno di spunta predefinito con un pulsante di opzione usando la classe <xref:System.Windows.Forms.RadioButtonRenderer>.</span><span class="sxs-lookup"><span data-stu-id="b578d-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <span data-ttu-id="b578d-117">Eseguire l'override dei metodi <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>e <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> per tenere traccia dello stato del mouse e assicurarsi che il metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> disegni lo stato corretto del pulsante di opzione.</span><span class="sxs-lookup"><span data-stu-id="b578d-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="b578d-118">Per disabilitare le opzioni in un sottomenu quando l'elemento padre non è selezionato</span><span class="sxs-lookup"><span data-stu-id="b578d-118">To disable options on a submenu when the parent item is not selected</span></span>

1. <span data-ttu-id="b578d-119">Eseguire l'override della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> in modo che l'elemento venga disabilitato quando dispone di un elemento padre con un valore <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` e un valore <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false`.</span><span class="sxs-lookup"><span data-stu-id="b578d-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. <span data-ttu-id="b578d-120">Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> per sottoscrivere l'evento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="b578d-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. <span data-ttu-id="b578d-121">Nel gestore per l'evento padre-elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged>, invalidare l'elemento per aggiornare la visualizzazione con il nuovo stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="b578d-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a><span data-ttu-id="b578d-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="b578d-122">Example</span></span>

<span data-ttu-id="b578d-123">Nell'esempio di codice seguente vengono fornite la classe `ToolStripRadioButtonMenuItem` completa e una classe <xref:System.Windows.Forms.Form> e `Program` classe per illustrare il comportamento del pulsante di opzione.</span><span class="sxs-lookup"><span data-stu-id="b578d-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a><span data-ttu-id="b578d-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b578d-124">Compiling the Code</span></span>

<span data-ttu-id="b578d-125">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b578d-125">This example requires:</span></span>

- <span data-ttu-id="b578d-126">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b578d-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="b578d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b578d-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="b578d-128">Controllo MenuStrip</span><span class="sxs-lookup"><span data-stu-id="b578d-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="b578d-129">Procedura: Implementare un oggetto ToolStripRenderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="b578d-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
