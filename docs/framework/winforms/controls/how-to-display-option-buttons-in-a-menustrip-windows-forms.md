---
title: 'Procedura: visualizzare pulsanti di opzione in un controllo MenuStrip (Windows Form)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15f2d1492148a4b00a4b96844f546a4dc968eef6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Procedura: visualizzare pulsanti di opzione in un controllo MenuStrip (Windows Form)
Noto anche come pulsanti, pulsanti di opzione sono simili alle caselle di controllo ad eccezione del fatto che gli utenti possono selezionare solo una alla volta. Anche se per impostazione predefinita il <xref:System.Windows.Forms.ToolStripMenuItem> classe non fornisce il comportamento del pulsante di opzione, la classe fornisce il comportamento della casella di controllo che è possibile personalizzare per implementare il comportamento del pulsante di opzione per le voci di menu in un <xref:System.Windows.Forms.MenuStrip> controllo.  
  
 Quando il <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà di una voce di menu è `true`, gli utenti possono selezionare l'elemento per attivare o disattivare la visualizzazione di un segno di spunta. Il <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà indica lo stato corrente dell'elemento. Per implementare il comportamento di base dei pulsanti di opzione, è necessario assicurarsi che quando viene selezionato un elemento, impostare il <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> proprietà per l'elemento selezionato in precedenza da `false`.  
  
 Le procedure seguenti descrivono come implementare questa e altre funzionalità in una classe che eredita la <xref:System.Windows.Forms.ToolStripMenuItem> classe. Il `ToolStripRadioButtonMenuItem` classe esegue l'override di membri, ad esempio <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> e <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> per fornire il comportamento di selezione e l'aspetto di pulsanti di opzione. Inoltre, questa classe esegue l'override di <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà in modo che le opzioni di un sottomenu sono disabilitati, a meno che non viene selezionato l'elemento padre.  
  
### <a name="to-implement-option-button-selection-behavior"></a>Per implementare il comportamento di selezione del pulsante di opzione  
  
1.  Inizializzare il <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> proprietà `true` per abilitare la selezione di elementi.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  Eseguire l'override di <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> metodo per cancellare la selezione dell'elemento selezionato in precedenza quando viene selezionato un nuovo elemento.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  Eseguire l'override di <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> metodo per garantire che facendo clic su un elemento che è già stato selezionato non cancellerà la selezione.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a>Per modificare l'aspetto degli elementi dei pulsanti di opzione  
  
1.  Eseguire l'override di <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> metodo da utilizzare per sostituire il segno di spunta predefinito con un pulsante di opzione di <xref:System.Windows.Forms.RadioButtonRenderer> classe.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  Eseguire l'override di <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, e <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> metodi per tenere traccia dello stato del mouse e assicurarsi che il <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> metodo disegni lo stato corretto del pulsante di opzione.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Per disabilitare le opzioni di un sottomenu quando l'elemento padre non è selezionata.  
  
1.  Eseguire l'override di <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> proprietà in modo che la voce è disabilitata quando si dispone di un elemento padre sia con un <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> valore `true` e un <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> valore `false`.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  Eseguire l'override di <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> metodo per sottoscrivere il <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> evento dell'elemento padre.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  Nel gestore per l'elemento padre <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> evento invalidare l'elemento per aggiornare la visualizzazione con il nuovo stato attivato.  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a>Esempio  
 L'esempio di codice seguente viene fornito completo `ToolStripRadioButtonMenuItem` (classe) e un <xref:System.Windows.Forms.Form> classe e `Program` classe per illustrare il comportamento del pulsante di opzione.  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.RadioButtonRenderer>  
 [Controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-windows-forms.md)  
 [Procedura: Implementare un oggetto ToolStripRenderer personalizzato](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-toolstriprenderer.md)
