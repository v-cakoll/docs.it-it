---
title: Nozioni fondamentali sullo sviluppo di controlli Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ca2bac983e25ab7453230a6718fe7eaa98e82275
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="windows-forms-control-development-basics"></a>Nozioni fondamentali sullo sviluppo di controlli Windows Form
Un controllo Windows Form è una classe che deriva direttamente o indirettamente da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Nell'elenco seguente vengono descritti scenari comuni per lo sviluppo di controlli Windows Form:  
  
-   Combinazione di controlli esistenti per la creazione di un controllo composito.  
  
     Controlli composti incapsulano un'interfaccia utente che può essere riutilizzata come un controllo. Un esempio di un controllo composito è un controllo che include una casella di testo e un pulsante Reimposta. Finestre di progettazione visiva offrono supporto avanzato per la creazione di controlli compositi. Per creare un controllo composito, derivare da <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. La classe di base <xref:System.Windows.Forms.UserControl> fornisce il routing della tastiera per i controlli figlio e consente l'utilizzo come un gruppo di controlli figlio. Per altre informazioni, vedere [Sviluppo di un controllo Windows Form composito](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md).  
  
-   Estensione di un controllo esistente per personalizzarlo o aggiungere funzionalità.  
  
     Sono esempi di controlli estesi di un pulsante, il cui colore non può essere modificato e un pulsante che dispone di una proprietà aggiuntiva che tiene traccia di quante volte è stato fatto clic. È possibile personalizzare qualsiasi controllo Windows Form che deriva da esso e si esegue l'override o l'aggiunta di proprietà, metodi ed eventi.  
  
-   Creazione di un controllo che non è possibile combinare o estendere i controlli esistenti.  
  
     In questo scenario, è necessario derivare il controllo dalla classe di base <xref:System.Windows.Forms.Control>. È possibile aggiungere, nonché eseguire l'override di proprietà, metodi ed eventi della classe di base. Per iniziare, vedere [procedura: sviluppare un controllo Windows Form semplice](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md).  
  
 La classe base per controlli Windows Form, <xref:System.Windows.Forms.Control>, fornisce l'infrastruttura necessaria per la visualizzazione nelle applicazioni client basate su Windows. <xref:System.Windows.Forms.Control>fornisce un handle di finestra, gestisce il routing dei messaggi e fornisce gli eventi di tastiera e mouse, così come molti altri utente gli eventi di interfaccia. Fornisce un layout avanzato e dispone di proprietà specifiche per la visualizzazione, ad esempio <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>e molti altri. Inoltre, offre sicurezza, il supporto del threading e interoperabilità con i controlli ActiveX. Poiché gran parte dell'infrastruttura viene definita dalla classe di base, è relativamente semplice sviluppare i propri controlli Windows Form.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Sviluppare un controllo di Windows Form semplice](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)  
 [Sviluppo di un controllo di Windows Form composto](../../../../docs/framework/winforms/controls/developing-a-composite-windows-forms-control.md)  
 [Procedura: Creare un controllo di Windows Form che visualizzi lo stato di avanzamento](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)  
 [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
