---
title: 'Procedura: Aggiungere pulsanti a un controllo ToolBar usando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: e5069dd46a31a65f65a17d750b685d82762e3d11
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038211"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Procedura: Aggiungere pulsanti a un controllo ToolBar usando la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.

Una parte integrante del <xref:System.Windows.Forms.ToolBar> controllo è costituita dai pulsanti da aggiungere. Questi possono essere usati per semplificare l'accesso ai comandi di menu o, in alternativa, possono essere posizionati in un'altra area dell'interfaccia utente dell'applicazione per esporre i comandi agli utenti che non sono disponibili nella struttura dei menu.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.ToolBar> modulo contenente un controllo. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).


### <a name="to-add-buttons-at-design-time"></a>Per aggiungere pulsanti in fase di progettazione

1. Selezionare il controllo <xref:System.Windows.Forms.ToolBar>.

2. Nella finestra **Proprietà** fare clic sulla <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà per selezionarla e fare clic sui **puntini** di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio.) per aprire ToolBarButton.](./media/visual-studio-ellipsis-button.png)  **Editor della raccolta**.

3. Usare i pulsanti **Aggiungi** e **Rimuovi** per aggiungere e rimuovere i <xref:System.Windows.Forms.ToolBar> pulsanti dal controllo.

4. Configurare le proprietà dei singoli pulsanti nella finestra **Proprietà** visualizzata nel riquadro sul lato destro dell'editor. Nella tabella seguente vengono illustrate alcune proprietà importanti da considerare.

    |Proprietà|Descrizione|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Imposta il menu da visualizzare nel pulsante della barra degli strumenti a discesa. La <xref:System.Windows.Forms.ToolBarButton.Style%2A> proprietà del pulsante della barra degli strumenti deve <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>essere impostata su. Questa proprietà accetta un'istanza della <xref:System.Windows.Forms.ContextMenu> classe come riferimento.|
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Imposta un valore che indica se un pulsante della barra degli strumenti di tipo interruttore viene inserito parzialmente. La <xref:System.Windows.Forms.ToolBarButton.Style%2A> proprietà del pulsante della barra degli strumenti deve <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>essere impostata su.|
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Imposta un valore che indica se un pulsante della barra degli strumenti di tipo interruttore si trova attualmente nello stato di push. La <xref:System.Windows.Forms.ToolBarButton.Style%2A> proprietà del pulsante della barra degli strumenti deve <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> essere <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>impostata su o.|
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Imposta lo stile del pulsante della barra degli strumenti. Deve essere uno dei valori <xref:System.Windows.Forms.ToolBarButtonStyle> dell'enumerazione.|
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|Stringa di testo visualizzata dal pulsante.|
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Testo visualizzato come descrizione comando per il pulsante.|

5. Fare clic su **OK** per chiudere la finestra di dialogo e creare i pannelli specificati.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: Definire un'icona per un pulsante della barra degli strumenti](how-to-define-an-icon-for-a-toolbar-button.md)
- [Procedura: Eventi del menu trigger per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Panoramica sul controllo ToolBar](toolbar-control-overview-windows-forms.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
