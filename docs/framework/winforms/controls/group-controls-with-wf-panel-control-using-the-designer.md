---
title: 'Procedura: Raggruppare i controlli con il controllo Panel di Windows Forms usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Panel control [Windows Forms], grouping controls
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
ms.assetid: 7e1cd708-fdb1-49d8-9ca2-5640b276bf2e
ms.openlocfilehash: cadfa715b140c63b216ec0ca2e6d6a6589ae3458
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040380"
---
# <a name="how-to-group-controls-with-the-windows-forms-panel-control-using-the-designer"></a>Procedura: Raggruppare i controlli con il controllo Panel di Windows Forms usando la finestra di progettazione
I <xref:System.Windows.Forms.Panel> controlli Windows Forms vengono usati per raggruppare altri controlli. Esistono tre motivi per raggruppare i controlli. Uno è il raggruppamento visivo di elementi del form correlati per un'interfaccia utente chiara; un altro è il raggruppamento programmatico di pulsanti di opzione, ad esempio. l'ultimo consiste nello trasferire i controlli come unità in fase di progettazione.

## <a name="to-create-a-group-of-controls"></a>Per creare un gruppo di controlli

1. Trascinare un <xref:System.Windows.Forms.Panel> controllo dalla scheda **Windows Forms** della casella degli strumenti in un form.

2. Aggiungere altri controlli al pannello, disegnando ognuno all'interno del pannello.

     Se si dispone di controlli esistenti che si desidera includere in un pannello, è possibile selezionare tutti i controlli, tagliarli negli Appunti, selezionare il <xref:System.Windows.Forms.Panel> controllo e quindi incollarli nel pannello. È anche possibile trascinarli nel pannello.

3. Opzionale Se si desidera aggiungere un bordo a un pannello, impostarne la <xref:System.Windows.Forms.BorderStyle> proprietà. Sono disponibili tre opzioni: <xref:System.Windows.Forms.BorderStyle.Fixed3D>, <xref:System.Windows.Forms.BorderStyle.FixedSingle>e <xref:System.Windows.Forms.BorderStyle.None>.

## <a name="see-also"></a>Vedere anche

- [Controllo Panel](panel-control-windows-forms.md)
- [Panoramica sul controllo Panel](panel-control-overview-windows-forms.md)
- [Procedura: Impostare lo sfondo di un pannello](how-to-set-the-background-of-a-windows-forms-panel.md)
