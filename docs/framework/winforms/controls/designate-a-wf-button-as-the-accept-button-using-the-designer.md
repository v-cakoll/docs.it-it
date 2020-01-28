---
title: Designare un pulsante come pulsante accetta utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27a5de51f8c5b2c84cc205e09ac1a2179c315752
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746071"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Procedura: designare un pulsante Windows Form come pulsante di conferma utilizzando la finestra di progettazione
In qualsiasi Windows Form è possibile designare un controllo <xref:System.Windows.Forms.Button> come pulsante accetta, noto anche come pulsante predefinito. Ogni volta che l'utente preme il tasto invio, viene fatto clic sul pulsante predefinito, indipendentemente da quale altro controllo nel form abbia lo stato attivo. Le eccezioni a questo si verificano quando il controllo con lo stato attivo è un altro pulsante, in tal caso verrà fatto clic sul pulsante con lo stato attivo o su una casella di testo a più righe o un controllo personalizzato che intrappola il tasto INVIO.

## <a name="to-designate-the-accept-button"></a>Per impostare il pulsante accetta

1. Selezionare il form in cui si trova il pulsante.

2. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.Form.AcceptButton%2A> del modulo sul nome del controllo <xref:System.Windows.Forms.Button>.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondere alla selezione dei pulsanti di Windows Form](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante Windows Form come pulsante Annulla usando la finestra di progettazione](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
