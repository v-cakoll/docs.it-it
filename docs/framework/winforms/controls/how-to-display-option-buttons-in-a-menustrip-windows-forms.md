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
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Procedura: Visualizzare pulsanti di opzione in un controllo MenuStrip (Windows Form)

I pulsanti di opzione, noti anche come pulsanti di opzione, sono simili alle caselle di controllo, ad eccezione del fatto che gli utenti possono selezionare solo uno alla volta. Sebbene per impostazione predefinita la classe <xref:System.Windows.Forms.ToolStripMenuItem> non fornisca il comportamento del pulsante di opzione, la classe fornisce il comportamento della casella di controllo che è possibile personalizzare per implementare il comportamento del pulsante di opzione per le voci di menu in un controllo <xref:System.Windows.Forms.MenuStrip>.

Quando la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà di una voce di menu è `true`, gli utenti possono fare clic sull'elemento per visualizzare o disabilitare la visualizzazione di un segno di spunta. La proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> indica lo stato corrente dell'elemento. Per implementare il comportamento di base dei pulsanti di opzione, è necessario assicurarsi che, quando si seleziona un elemento, impostare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> per l'elemento selezionato in precedenza su `false`.

Nelle procedure seguenti viene descritto come implementare questa e funzionalità aggiuntiva in una classe che eredita la classe <xref:System.Windows.Forms.ToolStripMenuItem>. La classe `ToolStripRadioButtonMenuItem` esegue l'override di membri quali <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> e <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> per fornire il comportamento di selezione e l'aspetto dei pulsanti di opzione. Inoltre, questa classe esegue l'override della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> in modo che le opzioni di un sottomenu siano disabilitate, a meno che l'elemento padre non sia selezionato.

## <a name="to-implement-option-button-selection-behavior"></a>Per implementare il comportamento di selezione dei pulsanti di opzione

1. Inizializzare la proprietà <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> su `true` per abilitare la selezione dell'elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> per cancellare la selezione dell'elemento selezionato in precedenza quando viene selezionato un nuovo elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> per assicurarsi che fare clic su un elemento già selezionato non cancelli la selezione.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>Per modificare l'aspetto degli elementi del pulsante di opzione

1. Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> per sostituire il segno di spunta predefinito con un pulsante di opzione usando la classe <xref:System.Windows.Forms.RadioButtonRenderer>.

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. Eseguire l'override dei metodi <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>e <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> per tenere traccia dello stato del mouse e assicurarsi che il metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> disegni lo stato corretto del pulsante di opzione.

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Per disabilitare le opzioni in un sottomenu quando l'elemento padre non è selezionato

1. Eseguire l'override della proprietà <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> in modo che l'elemento venga disabilitato quando dispone di un elemento padre con un valore <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> `true` e un valore <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `false`.

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. Eseguire l'override del metodo <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> per sottoscrivere l'evento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> dell'elemento padre.

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. Nel gestore per l'evento padre-elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged>, invalidare l'elemento per aggiornare la visualizzazione con il nuovo stato abilitato.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>Esempio

Nell'esempio di codice seguente vengono fornite la classe `ToolStripRadioButtonMenuItem` completa e una classe <xref:System.Windows.Forms.Form> e `Program` classe per illustrare il comportamento del pulsante di opzione.

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>Compilazione del codice

L'esempio presenta i requisiti seguenti:

- Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [Controllo MenuStrip](menustrip-control-windows-forms.md)
- [Procedura: Implementare un oggetto ToolStripRenderer personalizzato](how-to-implement-a-custom-toolstriprenderer.md)
