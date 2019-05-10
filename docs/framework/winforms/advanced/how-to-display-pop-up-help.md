---
title: 'Procedura: Visualizzare la Guida rapida'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: bf3bcbff0cd6f3bbf71e96e748cb170d5ce68dfc
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211405"
---
# <a name="how-to-display-pop-up-help"></a>Procedura: Guida rapida di visualizzazione

Un modo per visualizzare la Guida sui moduli di Windows è usare il **aiutare** pulsante, che si trova sul lato destro della barra del titolo, accessibile tramite il <xref:System.Windows.Forms.Form.HelpButton%2A> proprietà. Questo tipo di visualizzazione della Guida è ideale con le finestre di dialogo. Con le finestre di dialogo visualizzate come modali (con il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A>) risulta difficile accedere a sistemi di Guida esterni, perché le finestre di dialogo modali devono venire chiuse prima che lo stato attivo possa passare a un'altra finestra. Inoltre, tramite il **aiutare** pulsante richiede che sia presente alcun **Riduci a icona** pulsante o **Ingrandisci** pulsante visualizzato nella barra del titolo. Questa è una convenzione standard-finestra di dialogo, mentre i form dispongono in genere **Riduci a icona** e **Ingrandisci** pulsanti.

È anche possibile usare il <xref:System.Windows.Forms.HelpProvider> componente per collegare i controlli ai file in un sistema di Guida in linea, anche se è stata implementata la Guida rapida. Per altre informazioni, vedere [visualizzazione della Guida in un'applicazione Windows](how-to-provide-help-in-a-windows-application.md).

## <a name="display-pop-up-help"></a>Guida rapida di visualizzazione

1. In Visual Studio, trascinare un [HelpProvider](../controls/helpprovider-component-windows-forms.md) componente dalla casella degli strumenti al form.

   Il componente verrà posizionato sulla barra delle applicazioni in basso in Progettazione Windows Form.

2. Nella finestra Proprietà impostare la proprietà <xref:System.Windows.Forms.Form.HelpButton%2A> su `true`. Sulla destra della barra del titolo del form verrà visualizzato un pulsante con un punto interrogativo.

3. Per visualizzare <xref:System.Windows.Forms.Form.HelpButton%2A>, è necessario impostare le proprietà <xref:System.Windows.Forms.Form.MinimizeBox%2A> e <xref:System.Windows.Forms.Form.MaximizeBox%2A> del form su `false`, la proprietà <xref:System.Windows.Forms.Form.ControlBox%2A> su `true` e la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A> su uno dei valori seguenti: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> o <xref:System.Windows.Forms.FormBorderStyle.Sizable>.

4. Selezionare il controllo per il quale si desidera visualizzare la Guida nel form e impostare la stringa della Guida nella finestra Proprietà. Si tratta della stringa di testo che verrà visualizzato in una finestra simile a un [ToolTip](../controls/tooltip-component-windows-forms.md).

5. Premere **F5**.

6. Premere il **aiutare** pulsante sulla barra del titolo e fare clic sul controllo su cui impostare la stringa della Guida.

## <a name="see-also"></a>Vedere anche

- [Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi](control-help-using-tooltips.md)
- [Integrazione della Guida dell'utente in Windows Form](integrating-user-help-in-windows-forms.md)
- [Windows Form](../index.md)
