---
title: "Procedura: gestire l'overflow di ToolStrip"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736153"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Procedura: gestire l'overflow di ToolStrip in Windows Form

Quando tutti gli elementi di un controllo <xref:System.Windows.Forms.ToolStrip> non rientrano nello spazio allocato, è possibile abilitare la funzionalità di overflow sul <xref:System.Windows.Forms.ToolStrip> e determinare il comportamento di overflow di <xref:System.Windows.Forms.ToolStripItem>s specifici.

Quando si aggiungono <xref:System.Windows.Forms.ToolStripItem>che richiedono più spazio rispetto a quello assegnato al <xref:System.Windows.Forms.ToolStrip> in base alle dimensioni correnti del modulo, viene visualizzato un <xref:System.Windows.Forms.ToolStripOverflowButton> automaticamente sul <xref:System.Windows.Forms.ToolStrip>. Viene visualizzato il <xref:System.Windows.Forms.ToolStripOverflowButton> e gli elementi abilitati per l'overflow vengono spostati nel menu a discesa di overflow. In questo modo è possibile personalizzare e definire le priorità per adattare correttamente gli elementi <xref:System.Windows.Forms.ToolStrip> alle dimensioni del modulo diverse. È anche possibile modificare l'aspetto degli elementi quando entrano nell'overflow usando le proprietà <xref:System.Windows.Forms.ToolStripItem.Placement%2A> e <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> e l'evento <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>. Se si ingrandisce il form in fase di progettazione o in fase di esecuzione, è possibile visualizzare più <xref:System.Windows.Forms.ToolStripItem>s nel <xref:System.Windows.Forms.ToolStrip> principale e il <xref:System.Windows.Forms.ToolStripOverflowButton> potrebbe persino scomparire fino a quando non si diminuiscono le dimensioni del form.

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>Per abilitare l'overflow su un controllo ToolStrip

- Verificare che la proprietà <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> non sia impostata su `false` per il <xref:System.Windows.Forms.ToolStrip>. Il valore predefinito è `True`.

     Quando <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> viene `True` (impostazione predefinita), viene inviato un <xref:System.Windows.Forms.ToolStripItem> al menu a discesa di overflow quando il contenuto del <xref:System.Windows.Forms.ToolStripItem> supera la larghezza di un <xref:System.Windows.Forms.ToolStrip> orizzontale o l'altezza di una <xref:System.Windows.Forms.ToolStrip>verticale.

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Per specificare il comportamento di overflow di un oggetto ToolStripItem specifico

- Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> del <xref:System.Windows.Forms.ToolStripItem> sul valore desiderato. Le possibilità sono `Always`, `Never`e `AsNeeded`. Il valore predefinito è `AsNeeded`.

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Architettura del controllo ToolStrip](toolstrip-control-architecture.md)
- [Riepilogo della tecnologia ToolStrip](toolstrip-technology-summary.md)
