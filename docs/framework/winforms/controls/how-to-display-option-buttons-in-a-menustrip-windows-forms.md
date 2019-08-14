---
title: 'Procedura: Pulsanti di opzione di visualizzazione in un MenuStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: 94d683369edd6583ad8b01c2ce3f393567a5ed75
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971930"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Procedura: Pulsanti di opzione di visualizzazione in un MenuStrip (Windows Forms)

I pulsanti di opzione, noti anche come pulsanti di opzione, sono simili alle caselle di controllo, ad eccezione del fatto che gli utenti possono selezionare solo uno alla volta. Anche se, per <xref:System.Windows.Forms.ToolStripMenuItem> impostazione predefinita, la classe non fornisce il comportamento del pulsante di opzione, la classe fornisce il comportamento della casella di controllo che è possibile personalizzare per implementare il comportamento del <xref:System.Windows.Forms.MenuStrip> pulsante di opzione per le voci di menu in un controllo.

Quando la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà di una voce di menu `true`è, gli utenti possono fare clic sull'elemento per abilitare o disabilitare la visualizzazione di un segno di spunta. La <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà indica lo stato corrente dell'elemento. Per implementare il comportamento di base dei pulsanti di opzione, è necessario assicurarsi che, quando si seleziona un elemento <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> , impostare la proprietà per l'elemento `false`selezionato in precedenza su.

Nelle procedure seguenti viene descritto come implementare questa e funzionalità aggiuntiva in una classe che eredita <xref:System.Windows.Forms.ToolStripMenuItem> la classe. La `ToolStripRadioButtonMenuItem` classe esegue l'override dei <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> membri <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> , ad esempio e, per fornire il comportamento di selezione e l'aspetto dei pulsanti di opzione. Questa classe, inoltre, esegue <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> l'override della proprietà in modo che le opzioni di un sottomenu siano disabilitate, a meno che non sia selezionato l'elemento padre.

## <a name="to-implement-option-button-selection-behavior"></a>Per implementare il comportamento di selezione dei pulsanti di opzione

1. Inizializza la <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà su `true` per abilitare la selezione dell'elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. Eseguire l' <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> override del metodo per cancellare la selezione dell'elemento selezionato in precedenza quando viene selezionato un nuovo elemento.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. Eseguire l' <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> override del metodo per fare in modo che facendo clic su un elemento già selezionato non venga cancellata la selezione.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>Per modificare l'aspetto degli elementi del pulsante di opzione

1. Eseguire l' <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> override del metodo per sostituire il segno di spunta predefinito con un pulsante di opzione <xref:System.Windows.Forms.RadioButtonRenderer> usando la classe.

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. Eseguire l' <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>override <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>dei <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>metodi, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> , e per tenere traccia dello stato del mouse e assicurarsi che <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> il metodo disegni lo stato corretto del pulsante di opzione.

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Per disabilitare le opzioni in un sottomenu quando l'elemento padre non è selezionato

1. Eseguire l' <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> override della proprietà in modo che l'elemento venga disabilitato quando dispone di un elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> padre con `true` un valore <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> e un `false`valore.

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. Eseguire l' <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> override del metodo per sottoscrivere l' <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> evento dell'elemento padre.

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. Nel gestore per l'evento padre-elemento <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> , invalidare l'elemento per aggiornare la visualizzazione con il nuovo stato abilitato.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>Esempio

Nell'esempio di codice seguente vengono fornite `ToolStripRadioButtonMenuItem` la classe completa e <xref:System.Windows.Forms.Form> una classe `Program` e una classe per illustrare il comportamento del pulsante di opzione.

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
