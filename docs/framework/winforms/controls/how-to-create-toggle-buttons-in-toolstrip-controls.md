---
title: 'Procedura: Creare pulsanti interruttore nei controlli ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toggle buttons [Windows Forms], creating
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], creating toggle buttons
ms.assetid: d9c197df-4c65-43f2-beee-b68b52b2befc
ms.openlocfilehash: 6a003b91cd4db5db2790a20db97dbaa4d8925e96
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68972358"
---
# <a name="how-to-create-toggle-buttons-in-toolstrip-controls"></a>Procedura: Creare pulsanti interruttore nei controlli ToolStrip

Quando un utente fa clic su un interruttore, viene visualizzato incassato e mantiene l'aspetto incassato fino a quando l'utente fa nuovamente clic sul pulsante.

## <a name="to-create-a-toggling-toolstripbutton"></a>Per creare un elemento ToolStripButton

- Usare codice come l'esempio di codice seguente. Questo codice presuppone che il form contenga <xref:System.Windows.Forms.ToolStrip> un controllo e che la <xref:System.Windows.Forms.ToolStrip.Items%2A> raccolta contenga <xref:System.Windows.Forms.ToolStripButton> un `toolStripButton1`oggetto denominato. Si presuppone inoltre che si disponga di un gestore eventi `toolStripButton1_CheckedChanged`denominato.

    ```vb
    toolStripButton1.CheckOnClick = True
    toolStripButton1.CheckedChanged AddressOf _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

    ```csharp
    toolStripButton1.CheckOnClick = true;
    toolStripButton1.CheckedChanged += new _
    EventHandler(toolStripButton1_CheckedChanged);
    ```

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStripButton>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
