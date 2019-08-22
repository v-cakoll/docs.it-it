---
title: "Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 49e93f12bebbf409e6b3a06634556b9103c85f44
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666209"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione

> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.

<xref:System.Windows.Forms.ToolBar>i pulsanti sono in grado di visualizzare le icone al loro interno per facilitarne l'identificazione da parte degli utenti. Questa operazione viene eseguita tramite l'aggiunta di <xref:System.Windows.Forms.ImageList> immagini al componente e l'associazione con <xref:System.Windows.Forms.ToolBar> il controllo.

Per la procedura seguente è necessario un progetto di **applicazione Windows** con un <xref:System.Windows.Forms.ToolBar> modulo contenente un <xref:System.Windows.Forms.ImageList> controllo e un componente. Per informazioni sulla configurazione di un progetto di questo tipo [, vedere Procedura: Creare un progetto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) Windows Forms Application e [procedura: Aggiungere i controlli Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Per impostare un'icona per un pulsante della barra degli strumenti in fase di progettazione

1. Aggiungere immagini al <xref:System.Windows.Forms.ImageList> componente. Per altre informazioni, vedere [Procedura: Aggiungere o rimuovere immagini ImageList con la finestra](how-to-add-or-remove-imagelist-images-with-the-designer.md)di progettazione.

2. Selezionare il <xref:System.Windows.Forms.ToolBar> controllo nel form.

3. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.ToolBar> <xref:System.Windows.Forms.ToolBar.ImageList%2A> proprietà <xref:System.Windows.Forms.ImageList> del controllo sul componente.

4. Fare clic <xref:System.Windows.Forms.ToolBar> sulla <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà del controllo per selezionarla, quindi fare clic sui![puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio](./media/visual-studio-ellipsis-button.png).) per aprire l' **Editor della raccolta ToolBarButton**.

5. Usare il pulsante **Aggiungi** per aggiungere pulsanti al <xref:System.Windows.Forms.ToolBar> controllo.

6. Nella finestra **Proprietà** visualizzata nel riquadro sul lato destro dell' **Editor della raccolta ToolBarButton**, impostare la <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà di ogni pulsante della barra degli strumenti su uno dei valori dell'elenco, che viene disegnato dalle immagini aggiunte al <xref:System.Windows.Forms.ImageList> componente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: Eventi del menu trigger per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
