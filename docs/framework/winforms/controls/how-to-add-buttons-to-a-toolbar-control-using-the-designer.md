---
title: 'Procedura: aggiungere pulsanti a un controllo ToolBar mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding buttons
- ToolBar control [Windows Forms], adding separators
- examples [Windows Forms], toolbars
- ToolBar control [Windows Forms], adding drop-down menus
ms.assetid: d9ce3040-3e21-4e2d-80ae-b430982b2db8
ms.openlocfilehash: b96f112c83d2296356e3eb566a24315bcefeff1f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43488326"
---
# <a name="how-to-add-buttons-to-a-toolbar-control-using-the-designer"></a>Procedura: aggiungere pulsanti a un controllo ToolBar mediante la finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Parte integrante del <xref:System.Windows.Forms.ToolBar> controllo è i pulsanti e aggiungervi. Possono essere usati per fornire l'accesso facile ai comandi di menu o, in alternativa, possono essere posizionati in un'altra area dell'interfaccia utente dell'applicazione per esporre i comandi per gli utenti che non sono disponibili nella struttura di menu.  
  
 La procedura seguente richiede un **applicazione di Windows** progetto con un form contenente un <xref:System.Windows.Forms.ToolBar> controllo. Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto di applicazione Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere i controlli Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-buttons-at-design-time"></a>Per aggiungere i pulsanti in fase di progettazione  
  
1.  Selezionare il controllo <xref:System.Windows.Forms.ToolBar>.  
  
2.  Nel **delle proprietà** finestra, fare clic sul <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà per selezionarlo, quindi fare clic sul **puntini di sospensione** (![schermata di VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) per aprire la **insieme ToolBarButton**.  
  
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
 <xref:System.Windows.Forms.ToolBar>  
 [Procedura: Definire un'icona per un pulsante ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 [Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [Panoramica sul controllo ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 [Controllo ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
