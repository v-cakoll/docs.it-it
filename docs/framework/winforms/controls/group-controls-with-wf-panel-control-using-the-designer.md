---
title: Raggruppare i controlli con il controllo Panel usando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: 927aeb5b51bc1ac4e22a45e487b49424b4e67b71
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745647"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Procedura: raggruppare i controlli con il controllo Panel di Windows Form nella finestra di progettazione
Per raggruppare altri controlli, vengono usati Windows Forms controlli <xref:System.Windows.Forms.Panel>. Esistono tre motivi per raggruppare i controlli. Uno è il raggruppamento visivo di elementi del form correlati per un'interfaccia utente chiara; un altro è il raggruppamento programmatico di pulsanti di opzione, ad esempio. l'ultimo consiste nello trasferire i controlli come unità in fase di progettazione.

## <a name="to-create-a-group-of-controls"></a>Per creare un gruppo di controlli

1. Trascinare un controllo <xref:System.Windows.Forms.Panel> dalla scheda **Windows Forms** della casella degli strumenti in un form.

2. Aggiungere altri controlli al pannello, disegnando ognuno all'interno del pannello.

     Se si dispone di controlli esistenti che si desidera includere in un pannello, è possibile selezionare tutti i controlli, tagliarli negli Appunti, selezionare il controllo <xref:System.Windows.Forms.Panel> e quindi incollarli nel pannello. È anche possibile trascinarli nel pannello.

3. Opzionale Se si desidera aggiungere un bordo a un pannello, impostarne la proprietà <xref:System.Windows.Forms.BorderStyle>. Sono disponibili tre opzioni: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>e <xref:System.Windows.Forms.BorderStyle.None>.

## <a name="see-also"></a>Vedere anche

- [Controllo Panel](panel-control-windows-forms.md)
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
- [Procedura: Impostare lo sfondo di un controllo Panel](how-to-set-the-background-of-a-windows-forms-panel.md)
