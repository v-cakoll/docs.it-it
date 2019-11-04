---
title: 'Procedura: riassegnare i controlli esistenti a un padre diverso'
ms.date: 03/30/2017
helpviewer_keywords:
- container controls [Windows Forms], Windows Forms
- layout [Windows Forms], resizing
- layout [Windows Forms], child controls
ms.assetid: 5a5723ff-34e0-4b6f-a57b-be4ebe35cb34
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 1767fcff1742f4ad630b4b996c709b7ded53a129
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459206"
---
# <a name="how-to-reassign-existing-controls-to-a-different-parent"></a>Procedura: riassegnare i controlli esistenti a un padre diverso

È possibile assegnare i controlli presenti nel form a un nuovo controllo contenitore.

1. In Visual Studio trascinare tre controlli <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nel form. Posizionarli uno accanto a altro, ma lasciarli non allineati.

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
- [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Procedura dettagliata: Disposizione dei controlli in Windows Form usando guide di allineamento](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
