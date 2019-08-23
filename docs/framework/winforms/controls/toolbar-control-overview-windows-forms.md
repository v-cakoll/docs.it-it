---
title: Cenni preliminari sul controllo ToolBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ToolBar
helpviewer_keywords:
- toolbars [Windows Forms], about toolbars
- ToolBar control [Windows Forms], about ToolBar controls
ms.assetid: d426b203-0216-4dbe-b834-1641e50a9c29
ms.openlocfilehash: c7c19783963bb315a0356979797c6f4d4e3b9e08
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929588"
---
# <a name="toolbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo ToolBar (Windows Form)
> [!NOTE]
> Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il controllo <xref:System.Windows.Forms.ToolBar> Windows Form viene usato nei form come barra di controllo sulla quale viene visualizzata una riga di menu a discesa e pulsanti bitmap per l'attivazione dei comandi. Fare clic su un pulsante della barra degli strumenti può equivalere a scegliere un comando di menu. È possibile configurare i pulsanti affinché abbiano l'aspetto e il comportamento di pulsanti di comando, menu a discesa o separatori. In genere, una barra degli strumenti contiene pulsanti e menu che corrispondono alle voci della struttura di menu di un'applicazione e forniscono un rapido accesso alle funzioni e ai comandi usati più di frequente in un'applicazione.  
  
## <a name="working-with-the-toolbar-control"></a>Uso del controllo ToolBar  
 Un <xref:System.Windows.Forms.ToolBar> controllo è in genere "ancorato" lungo la parte superiore della finestra padre, ma può anche essere ancorato a qualsiasi lato della finestra. Una barra degli strumenti può visualizzare le descrizioni comando quando l'utente sposta il puntatore del mouse su uno dei pulsanti. Una descrizione comando è una piccola finestra popup che fornisce una breve descrizione dello scopo del pulsante o del menu. Per visualizzare le descrizioni comandi, <xref:System.Windows.Forms.ToolBar.ShowToolTips%2A> la proprietà deve essere impostata `true`su.  
  
> [!NOTE]
> I controlli di determinate applicazioni sono molto simili alla barra degli strumenti, in quanto possono essere riposizionati e "ancorati" al di sopra della finestra dell'applicazione. Il controllo ToolBar Windows Form non consente di eseguire queste operazioni.  
  
 Quando la <xref:System.Windows.Forms.ToolBar.Appearance%2A> proprietà è impostata su <xref:System.Windows.Forms.ToolBarAppearance>, i pulsanti della barra degli strumenti vengono visualizzati in rilievo e tridimensionali. È possibile impostare la <xref:System.Windows.Forms.ToolBar.Appearance%2A> proprietà della <xref:System.Windows.Forms.ToolBarAppearance> barra degli strumenti su per assegnare un aspetto alla barra degli strumenti e ai relativi pulsanti. I pulsanti assumono un aspetto tridimensionale quando il puntatore del mouse viene spostato su di essi. I pulsanti della barra degli strumenti possono essere suddivisi in gruppi logici tramite dei separatori. Un separatore è un pulsante della barra <xref:System.Windows.Forms.ToolBarButton.Style%2A> degli strumenti con <xref:System.Windows.Forms.ToolBarButtonStyle>la proprietà impostata su. Viene visualizzato sulla barra degli strumenti come uno spazio vuoto. Quando per la barra degli strumenti viene impostato l'aspetto piatto, i separatori sono visualizzati come linee anziché come spazi tra i pulsanti.  
  
 Il <xref:System.Windows.Forms.ToolBar> controllo consente di creare barre degli strumenti aggiungendo <xref:System.Windows.Forms.Button> oggetti a una <xref:System.Windows.Forms.ToolBar.Buttons%2A> raccolta. È possibile utilizzare l'editor della raccolta per aggiungere pulsanti a <xref:System.Windows.Forms.ToolBar> un controllo; <xref:System.Windows.Forms.Button> a ogni oggetto deve essere assegnato un testo o un'immagine, sebbene sia possibile assegnare entrambi. L'immagine viene fornita da un componente [ImageList](imagelist-component-windows-forms.md) associato. In fase di esecuzione è possibile aggiungere o rimuovere pulsanti da <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection> usando i <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Add%2A> metodi e <xref:System.Windows.Forms.ToolBar.ToolBarButtonCollection.Remove%2A> . Per programmare i pulsanti di un <xref:System.Windows.Forms.ToolBar>oggetto, aggiungere il codice <xref:System.Windows.Forms.ToolBar.ButtonClick> agli eventi di <xref:System.Windows.Forms.ToolBar>, usando la <xref:System.Windows.Forms.ToolBarButtonClickEventArgs.Button%2A> proprietà della <xref:System.Windows.Forms.ToolBarButtonClickEventArgs> classe per determinare il pulsante su cui è stato fatto clic.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolBar>
- [Controllo ToolBar](toolbar-control-windows-forms.md)
- [Procedura: Aggiungere pulsanti a un controllo ToolBar](how-to-add-buttons-to-a-toolbar-control.md)
- [Procedura: Definire un'icona per un pulsante della barra degli strumenti](how-to-define-an-icon-for-a-toolbar-button.md)
- [Procedura: Eventi del menu trigger per i pulsanti della barra degli strumenti](how-to-trigger-menu-events-for-toolbar-buttons.md)
