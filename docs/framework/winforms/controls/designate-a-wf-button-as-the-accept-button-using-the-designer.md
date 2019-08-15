---
title: 'Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 27ecb26c493232bcfb996d012f9760b7ef91e5b2
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039651"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>Procedura: Designare un pulsante Windows Forms come pulsante di conferma usando la finestra di progettazione
In qualsiasi Windows Form è possibile designare un <xref:System.Windows.Forms.Button> controllo come pulsante di accettazione, noto anche come pulsante predefinito. Ogni volta che l'utente preme il tasto invio, viene fatto clic sul pulsante predefinito, indipendentemente da quale altro controllo nel form abbia lo stato attivo. Le eccezioni a questo si verificano quando il controllo con lo stato attivo è un altro pulsante, in tal caso verrà fatto clic sul pulsante con lo stato attivo o su una casella di testo a più righe o un controllo personalizzato che intrappola il tasto INVIO.

## <a name="to-designate-the-accept-button"></a>Per impostare il pulsante accetta

1. Selezionare il form in cui si trova il pulsante.

2. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.Form.AcceptButton%2A> proprietà <xref:System.Windows.Forms.Button> del modulo sul nome del controllo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Panoramica sul controllo Button](button-control-overview-windows-forms.md)
- [Modalità di selezione di un controllo Button di Windows Form](ways-to-select-a-windows-forms-button-control.md)
- [Procedura: Rispondi a Windows Forms clic sui pulsanti](how-to-respond-to-windows-forms-button-clicks.md)
- [Procedura: Designare un pulsante di Windows Forms come pulsante Annulla utilizzando la finestra di progettazione](designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Controllo Button](button-control-windows-forms.md)
