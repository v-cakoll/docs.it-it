---
title: 'Procedura: Riassegnare i controlli esistenti a un elemento padre diverso'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 84e662e0bd2689115abe128c6442e4462eed3e18
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987032"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Procedura: Riassegnare i controlli esistenti a un padre diverso

È possibile assegnare i controlli presenti nel form a un nuovo controllo contenitore.

1. In Visual Studio trascinare tre <xref:System.Windows.Forms.Button> controlli dalla **casella degli strumenti** nel form. Posizionarli uno accanto a altro, ma lasciarli non allineati.

2. Nella **Casella degli strumenti**fare clic sull'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> . Non trascinare l'icona nel form.

3. Spostare il puntatore del mouse accanto ai tre controlli <xref:System.Windows.Forms.Button> .

   Il puntatore assume la forma di un mirino con l'icona del controllo <xref:System.Windows.Forms.FlowLayoutPanel> associata.

4. Fare clic e tenere premuto il pulsante del mouse.

5. Trascinare il puntatore del mouse per disegnare la struttura del controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

6. Disegnare la struttura intorno ai tre controlli <xref:System.Windows.Forms.Button> .

7. Rilasciare il pulsante del mouse.

   I tre controlli <xref:System.Windows.Forms.Button> sono stati inseriti nel controllo <xref:System.Windows.Forms.FlowLayoutPanel> .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FlowLayoutPanel>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Procedura dettagliata: Disposizione di controlli in Windows Forms tramite TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione di controlli in Windows Forms mediante guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
