---
title: Controllo ToolBar (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 8162dfc898f7965d65de918d2a5b1f7afbfdf9b2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43400849"
---
# <a name="toolbar-control-windows-forms"></a>Controllo ToolBar (Windows Form)
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo `ToolBar` aggiungendovi funzionalità, il controllo `ToolBar` viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il controllo `ToolBar` Windows Form viene usato nei form come barra di controllo sulla quale viene visualizzata una riga di menu a discesa e pulsanti bitmap per l'attivazione dei comandi. Fare clic su un pulsante della barra degli strumenti equivale pertanto a scegliere un comando di menu. È possibile configurare i pulsanti affinché abbiano l'aspetto e il comportamento di pulsanti di comando, menu a discesa o separatori. In genere, una barra degli strumenti contiene pulsanti e menu che corrispondono alle voci della struttura di menu di un'applicazione e forniscono un rapido accesso alle funzioni e ai comandi usati più di frequente in un'applicazione.  
  
> [!NOTE]
>  La proprietà <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> del controllo `ToolBar` accetta un'istanza della classe <xref:System.Windows.Forms.ContextMenu> come riferimento. Prestare particolare attenzione al riferimento che viene passato quando si implementa questo tipo di pulsanti sulle barre degli strumenti dell'applicazione, poiché la proprietà accetterà qualsiasi oggetto che eredita dalla classe <xref:System.Windows.Forms.Menu>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica sul controllo ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-overview-windows-forms.md)  
 Introduce i concetti generali relativi al controllo `ToolBar`, che consente di creare barre degli strumenti personalizzate che possono essere usate dagli utenti.  
  
 [Procedura: Aggiungere pulsanti a un controllo ToolBar](../../../../docs/framework/winforms/controls/how-to-add-buttons-to-a-toolbar-control.md)  
 Descrive come aggiungere pulsanti a un controllo `ToolBar`.  
  
 [Procedura: Definire un'icona per un pulsante ToolBar](../../../../docs/framework/winforms/controls/how-to-define-an-icon-for-a-toolbar-button.md)  
 Descrive come visualizzare icone all'interno dei pulsanti di un controllo `ToolBar`.  
  
 [Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 Illustra come scrivere il codice che consente di identificare il pulsante su cui l'utente ha fatto clic in un controllo `ToolBar`.  
  
 Vedere anche [procedura: definire un'icona per un pulsante della barra degli strumenti usando la finestra di progettazione](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [procedura: aggiungere pulsanti a un controllo ToolBar mediante la finestra di progettazione](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).  
  
## <a name="reference"></a>Riferimenti  
 Classe <xref:System.Windows.Forms.ToolBar>  
 Fornisce informazioni di riferimento sulla classe e sui relativi membri.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.  
  
 [Controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)  
 Descrive barre degli strumenti che possono ospitare menu, controlli e controlli utente nelle applicazioni Windows Forms.
