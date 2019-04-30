---
title: Controllo ToolBar (Windows Form)
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 3f0a1b6a7f83753ccae1a129528ed320a2613122
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009547"
---
# <a name="toolbar-control-windows-forms"></a>Controllo ToolBar (Windows Form)
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo `ToolBar` aggiungendovi funzionalità, il controllo `ToolBar` viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il controllo `ToolBar` Windows Form viene usato nei form come barra di controllo sulla quale viene visualizzata una riga di menu a discesa e pulsanti bitmap per l'attivazione dei comandi. Fare clic su un pulsante della barra degli strumenti equivale pertanto a scegliere un comando di menu. È possibile configurare i pulsanti affinché abbiano l'aspetto e il comportamento di pulsanti di comando, menu a discesa o separatori. In genere, una barra degli strumenti contiene pulsanti e menu che corrispondono alle voci della struttura di menu di un'applicazione e forniscono un rapido accesso alle funzioni e ai comandi usati più di frequente in un'applicazione.  
  
> [!NOTE]
>  La proprietà <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A> del controllo `ToolBar` accetta un'istanza della classe <xref:System.Windows.Forms.ContextMenu> come riferimento. Prestare particolare attenzione al riferimento che viene passato quando si implementa questo tipo di pulsanti sulle barre degli strumenti dell'applicazione, poiché la proprietà accetterà qualsiasi oggetto che eredita dalla classe <xref:System.Windows.Forms.Menu>.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Panoramica sul controllo ToolBar](toolbar-control-overview-windows-forms.md)  
 Introduce i concetti generali relativi al controllo `ToolBar`, che consente di creare barre degli strumenti personalizzate che possono essere usate dagli utenti.  
  
 [Procedura: Aggiungere pulsanti a un controllo ToolBar](how-to-add-buttons-to-a-toolbar-control.md)  
 Descrive come aggiungere pulsanti a un controllo `ToolBar`.  
  
 [Procedura: Definire un'icona per un pulsante della barra degli strumenti](how-to-define-an-icon-for-a-toolbar-button.md)  
 Descrive come visualizzare icone all'interno dei pulsanti di un controllo `ToolBar`.  
  
 [Procedura: Attivare eventi di Menu per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 Illustra come scrivere il codice che consente di identificare il pulsante su cui l'utente ha fatto clic in un controllo `ToolBar`.  
  
 Vedere anche [come: Definire un'icona per un pulsante della barra degli strumenti utilizzando la finestra di progettazione](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [come: Aggiungere pulsanti a un controllo ToolBar mediante la finestra di progettazione](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).  
  
## <a name="reference"></a>Riferimenti  
 Classe <xref:System.Windows.Forms.ToolBar>  
 Fornisce informazioni di riferimento sulla classe e sui relativi membri.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)  
 Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.  
  
 [Controllo ToolStrip](toolstrip-control-windows-forms.md)  
 Descrive barre degli strumenti che possono ospitare menu, controlli e controlli utente nelle applicazioni Windows Forms.
