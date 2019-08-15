---
title: 'Procedura: Designare un pulsante Windows Forms come pulsante di annullamento usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: cc352f15fb1e8b531cd0f9b298b2db4ce649d3cf
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039641"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Procedura: Designare un pulsante Windows Forms come pulsante di annullamento usando la finestra di progettazione
In qualsiasi Windows Form è possibile designare un <xref:System.Windows.Forms.Button> controllo come pulsante Annulla. Quando l'utente preme il tasto ESC, viene fatto clic su un pulsante Annulla, indipendentemente da quale altro controllo nel form abbia lo stato attivo. Un pulsante di questo tipo è in genere programmato per consentire all'utente di uscire rapidamente da un'operazione senza eseguire il commit in alcuna azione.

## <a name="to-designate-the-cancel-button"></a>Per impostare il pulsante Annulla

1. Selezionare il form in cui si trova il pulsante.

2. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.Form.CancelButton%2A> proprietà <xref:System.Windows.Forms.Button> del modulo sul nome del controllo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondi a Windows Forms clic sui pulsanti](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante Windows Forms come pulsante accetta utilizzando la finestra di progettazione](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
