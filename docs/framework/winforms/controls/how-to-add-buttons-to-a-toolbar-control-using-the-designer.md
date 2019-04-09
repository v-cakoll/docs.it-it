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
ms.openlocfilehash: 133190426229a10ed6f637293326c229e808bfdb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084024"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Procedura: Aggiungere pulsanti a un controllo ToolBar usando la finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Parte integrante del <xref:System.Windows.Forms.ToolBar> controllo è i pulsanti e aggiungervi. Possono essere usati per fornire l'accesso facile ai comandi di menu o, in alternativa, possono essere posizionati in un'altra area dell'interfaccia utente dell'applicazione per esporre i comandi per gli utenti che non sono disponibili nella struttura di menu.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.ToolBar> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [come: Creare un progetto Windows Forms application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [come: Aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-buttons-at-design-time"></a>Per aggiungere i pulsanti in fase di progettazione  
  
1.  Selezionare il controllo <xref:System.Windows.Forms.ToolBar>.  
  
2.  Nel **delle proprietà** finestra, fare clic sul <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà per selezionarlo, quindi fare clic sul **puntini di sospensione** (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png " vbEllipsesButton")) per aprire la **insieme ToolBarButton**.  
  
3.  Usare la **Add** e **rimuovere** pulsanti per aggiungere e rimuovere pulsanti dal <xref:System.Windows.Forms.ToolBar> controllo.  
  
4.  Configurare le proprietà dei pulsanti in singoli il **proprietà** finestra visualizzata nel riquadro a destra dell'editor. Nella tabella seguente mostra alcune proprietà importanti da considerare.  
  
    |Proprietà|Descrizione|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>|Imposta il menu da visualizzare nel pulsante della barra degli strumenti elenco a discesa. Del pulsante della barra degli strumenti <xref:System.Windows.Forms.ToolBarButton.Style%2A> proprietà deve essere impostata su <xref:System.Windows.Forms.ToolBarButtonStyle.DropDownButton>. Questa proprietà accetta un'istanza di <xref:System.Windows.Forms.ContextMenu> classe come riferimento.|  
    |<xref:System.Windows.Forms.ToolBarButton.PartialPush%2A>|Determina se un pulsante interruttore è parzialmente premuto. Del pulsante della barra degli strumenti <xref:System.Windows.Forms.ToolBarButton.Style%2A> proprietà deve essere impostata su <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Pushed%2A>|Imposta se un interruttore della barra degli strumenti è attualmente premuto. Del pulsante della barra degli strumenti <xref:System.Windows.Forms.ToolBarButton.Style%2A> proprietà deve essere impostata su <xref:System.Windows.Forms.ToolBarButtonStyle.ToggleButton> o <xref:System.Windows.Forms.ToolBarButtonStyle.PushButton>.|  
    |<xref:System.Windows.Forms.ToolBarButton.Style%2A>|Imposta lo stile del pulsante della barra degli strumenti. Deve essere uno dei valori di <xref:System.Windows.Forms.ToolBarButtonStyle> enumerazione.|  
    |<xref:System.Windows.Forms.ToolBarButton.Text%2A>|La stringa di testo visualizzata dal pulsante.|  
    |<xref:System.Windows.Forms.ToolBarButton.ToolTipText%2A>|Il testo visualizzato come descrizione comando del pulsante.|  
  
5.  Fare clic su **OK** per chiudere la finestra di dialogo e creare i pannelli specificati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Procedura: Definire un'icona per un pulsante della barra degli strumenti](how-to-define-an-icon-for-a-toolbar-button.md)
- [Procedura: Attivare eventi di menu per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [Panoramica del controllo ToolBar](toolbar-control-overview-windows-forms.md)
- [Controllo ToolBar](toolbar-control-windows-forms.md)
