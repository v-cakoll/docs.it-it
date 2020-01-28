---
title: Cenni preliminari sul controllo ToolBar
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: f364e052258703331496f8103b48953a90aa3a9b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735479"
---
# <a name="toolbar-control-overview-windows-forms"></a>Panoramica del controllo ToolBar (Windows Form)
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il controllo <xref:System.Windows.Forms.ToolBar> Windows Form viene usato nei form come barra di controllo sulla quale viene visualizzata una riga di menu a discesa e pulsanti bitmap per l'attivazione dei comandi. Fare clic su un pulsante della barra degli strumenti può equivalere a scegliere un comando di menu. È possibile configurare i pulsanti affinché abbiano l'aspetto e il comportamento di pulsanti di comando, menu a discesa o separatori. In genere, una barra degli strumenti contiene pulsanti e menu che corrispondono alle voci della struttura di menu di un'applicazione e forniscono un rapido accesso alle funzioni e ai comandi usati più di frequente in un'applicazione.  
  
## <a name="working-with-the-toolbar-control"></a>Uso del controllo ToolBar  
 Un controllo <xref:System.Windows.Forms.ToolBar> è in genere "ancorato" lungo la parte superiore della finestra padre, ma può anche essere ancorato a qualsiasi lato della finestra. Una barra degli strumenti può visualizzare le descrizioni comando quando l'utente sposta il puntatore del mouse su uno dei pulsanti. Una descrizione comando è una piccola finestra popup che fornisce una breve descrizione dello scopo del pulsante o del menu. Per visualizzare le descrizioni comandi, è necessario impostare la proprietà <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> su `true`.  
  
> [!NOTE]
> I controlli di determinate applicazioni sono molto simili alla barra degli strumenti, in quanto possono essere riposizionati e "ancorati" al di sopra della finestra dell'applicazione. Il controllo ToolBar Windows Form non consente di eseguire queste operazioni.  
  
 Quando la proprietà <xref:System.Windows.Forms.ToolBar.Appearance%2A> è impostata su <xref:System.Windows.Forms.ToolBarAppearance>, i pulsanti della barra degli strumenti vengono visualizzati in rilievo e tridimensionali. È possibile impostare la proprietà <xref:System.Windows.Forms.ToolBar.Appearance%2A> della barra degli strumenti su <xref:System.Windows.Forms.ToolBarAppearance> per assegnare un aspetto alla barra degli strumenti e ai relativi pulsanti. I pulsanti assumono un aspetto tridimensionale quando il puntatore del mouse viene spostato su di essi. I pulsanti della barra degli strumenti possono essere suddivisi in gruppi logici tramite dei separatori. Un separatore è un pulsante della barra degli strumenti con la proprietà <xref:System.Windows.Forms.ToolBarButton.Style%2A> impostata su <xref:System.Windows.Forms.ToolBarButtonStyle>. Viene visualizzato sulla barra degli strumenti come uno spazio vuoto. Quando per la barra degli strumenti viene impostato l'aspetto piatto, i separatori sono visualizzati come linee anziché come spazi tra i pulsanti.  
  
 Il controllo <xref:System.Windows.Forms.ToolBar> consente di creare barre degli strumenti aggiungendo <xref:System.Windows.Forms.Button> oggetti a una raccolta di <xref:System.Windows.Forms.ToolBar.Buttons%2A>. È possibile usare l'editor della raccolta per aggiungere pulsanti a un controllo <xref:System.Windows.Forms.ToolBar>; a ogni oggetto <xref:System.Windows.Forms.Button> deve essere assegnato un testo o un'immagine, sebbene sia possibile assegnarli entrambi. L'immagine viene fornita da un componente [ImageList](imagelist-component-windows-forms.md) associato. In fase di esecuzione è possibile aggiungere o rimuovere pulsanti dall'<xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> usando i metodi <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> e <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A>. Per programmare i pulsanti di una <xref:System.Windows.Forms.ToolBar>, aggiungere il codice agli eventi <xref:System.Windows.Forms.ToolBar.ButtonClick> della <xref:System.Windows.Forms.ToolBar>, usando la proprietà <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> della classe <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> per determinare il pulsante selezionato.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Controllo ToolBar](toolbar-control-windows-forms.md)
- [Procedura: Aggiungere pulsanti a un controllo ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Procedura: Definire un'icona per un pulsante ToolBar](how-to-define-an-icon-for-a-toolbar-button.md)
- [Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
