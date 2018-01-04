---
title: 'Procedura: definire un''icona per un pulsante di una barra degli strumenti mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90e72b2516efab3bc5b5d8cc7cacb66f149f3a66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>Procedura: definire un'icona per un pulsante di una barra degli strumenti mediante la finestra di progettazione
> [!NOTE]
>  Benché il controllo <xref:System.Windows.Forms.ToolStrip> sostituisca il controllo <xref:System.Windows.Forms.ToolBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 <xref:System.Windows.Forms.ToolBar>i pulsanti sono in grado di visualizzare icone al loro interno per semplificarne l'identificazione da parte degli utenti. Questo risultato viene ottenuto tramite l'aggiunta di immagini per il <xref:System.Windows.Forms.ImageList> componente e la relativa associazione con il <xref:System.Windows.Forms.ToolBar> controllo.  
  
 La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.ToolBar> controllo e un <xref:System.Windows.Forms.ImageList> componente. Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>Per impostare un'icona per un pulsante della barra degli strumenti in fase di progettazione  
  
1.  Aggiungere immagini per il <xref:System.Windows.Forms.ImageList> componente. Per ulteriori informazioni, vedere [procedura: aggiungere o rimuovere immagini ImageList con la finestra di progettazione](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).  
  
2.  Selezionare il <xref:System.Windows.Forms.ToolBar> controllo sul form.  
  
3.  Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.ToolBar> del controllo <xref:System.Windows.Forms.ToolBar.ImageList%2A> proprietà per il <xref:System.Windows.Forms.ImageList> componente.  
  
4.  Fare clic su di <xref:System.Windows.Forms.ToolBar> del controllo <xref:System.Windows.Forms.ToolBar.Buttons%2A> proprietà per selezionarlo e fare clic sui puntini di sospensione (![schermata VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Insieme ToolBarButton**.  
  
5.  Utilizzare il **Aggiungi** pulsante per aggiungere i pulsanti per la <xref:System.Windows.Forms.ToolBar> controllo.  
  
6.  Nel **proprietà** finestra che viene visualizzata nel riquadro a destra del **insieme ToolBarButton**, impostare il <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> proprietà di ogni pulsante della barra degli strumenti per uno dei valori nell'elenco, che viene disegnato da immagini aggiunte per la <xref:System.Windows.Forms.ImageList> componente.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolBar>  
 [Procedura: Attivare eventi di menu per i pulsanti di una barra degli strumenti](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [Controllo ToolBar](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [Componente ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
