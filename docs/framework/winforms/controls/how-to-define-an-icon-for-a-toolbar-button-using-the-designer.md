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
ms.openlocfilehash: f8fe28a7827c0f69f80a3078d604b1818f4134ac
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65877413"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Procedura: Definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 <xref:System.Windows.Forms.ToolBar> i pulsanti sono in grado di visualizzare icone all'interno di essi per facilitare l'identificazione da parte degli utenti. Questo risultato viene ottenuto tramite l'aggiunta di immagini per le <xref:System.Windows.Forms.ImageList> componenti e associandolo al <xref:System.Windows.Forms.ToolBar> controllo.  
  
 La procedura seguente richiede un **dell'applicazione Windows** progetto con un form contenente una <xref:System.Windows.Forms.ToolBar> controllo e un <xref:System.Windows.Forms.ImageList> componente. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Per impostare un'icona per un pulsante della barra degli strumenti in fase di progettazione  
  
1. Aggiungere immagini al <xref:System.Windows.Forms.ImageList> componente. Per altre informazioni, vedere [Procedura: Aggiungere o rimuovere immagini ImageList con la finestra di progettazione](how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2. Selezionare il <xref:System.Windows.Forms.ToolBar> controllo sul form.  
  
3. Nel **proprietà** impostare nella finestra di <xref:System.Windows.Forms.ToolBar> del controllo <xref:System.Windows.Forms.ToolBar.ImageList%2A> proprietà per il <xref:System.Windows.Forms.ImageList> componente.  
  
4.  Fare clic sui <xref:System.Windows.Forms.ToolBar> del controllo <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà per selezionarlo, quindi fare clic sui puntini di sospensione (![The puntini di sospensione nella finestra proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) per aprire il **ToolBarButton raccolta Editor**.  
  
5. Usare il **Add** per aggiungere i pulsanti per il <xref:System.Windows.Forms.ToolBar> controllo.  
  
6. Nel **delle proprietà** finestra visualizzata nel riquadro a destra del **insieme ToolBarButton**, impostare il <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà dei pulsanti della barra degli strumenti a uno dei valori nell'elenco, che viene disegnato da immagini di cui è stato aggiunto per il <xref:System.Windows.Forms.ImageList> componente.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: Attivare eventi di Menu per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
- [Componente ImageList](imagelist-component-windows-forms.md)
