---
title: Designare un pulsante come pulsante Annulla utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: 95d1139b6e339055f944ad0b0967a6d91283d49e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746059"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>Procedura: designare un pulsante Windows Form come pulsante Annulla utilizzando la finestra di progettazione
In qualsiasi Windows Form è possibile designare un controllo <xref:System.Windows.Forms.Button> come pulsante Annulla. Quando l'utente preme il tasto ESC, viene fatto clic su un pulsante Annulla, indipendentemente da quale altro controllo nel form abbia lo stato attivo. Un pulsante di questo tipo è in genere programmato per consentire all'utente di uscire rapidamente da un'operazione senza eseguire il commit in alcuna azione.

## <a name="to-designate-the-cancel-button"></a>Per impostare il pulsante Annulla

1. Selezionare il form in cui si trova il pulsante.

2. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.Form.CancelButton%2A> del modulo sul nome del controllo <xref:System.Windows.Forms.Button>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form.CancelButton%2A>
- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante Windows Form come pulsante di conferma usando la finestra di progettazione](designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
