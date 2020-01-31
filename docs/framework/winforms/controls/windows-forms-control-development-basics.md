---
title: Nozioni fondamentali per lo sviluppo di controlli
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: fab0a76e2f9fdb7e2f89e9d6a10dd9c522a6d8e1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739911"
---
# <a name="windows-forms-control-development-basics"></a>Nozioni di base sullo sviluppo di controlli Windows Form
Un controllo Windows Forms è una classe che deriva direttamente o indirettamente da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Nell'elenco seguente vengono descritti gli scenari comuni per lo sviluppo di controlli Windows Forms:  
  
- Combinazione di controlli esistenti per la creazione di un controllo composito.  
  
     I controlli compositi incapsulano un'interfaccia utente che può essere riutilizzata come controllo. Un esempio di controllo composito è costituito da un controllo costituito da una casella di testo e da un pulsante Reimposta. Le finestre di progettazione visiva offrono un supporto completo per la creazione di controlli compositi. Per creare un controllo composito, derivare da <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. La classe di base <xref:System.Windows.Forms.UserControl> fornisce il routing della tastiera per i controlli figlio e consente ai controlli figlio di funzionare come un gruppo. Per altre informazioni, vedere [Sviluppo di un controllo Windows Form composito](developing-a-composite-windows-forms-control.md).  
  
- Estensione di un controllo esistente per personalizzarlo o per aggiungerne le funzionalità.  
  
     Un pulsante il cui colore non può essere modificato e un pulsante con una proprietà aggiuntiva che tiene traccia del numero di volte in cui è stato fatto clic sono esempi di controlli estesi. È possibile personalizzare qualsiasi controllo Windows Forms derivando da esso ed eseguendo l'override o l'aggiunta di proprietà, metodi ed eventi.  
  
- Creazione di un controllo che non combina o estende i controlli esistenti.  
  
     In questo scenario, derivare il controllo dalla classe base <xref:System.Windows.Forms.Control>. È possibile aggiungere così come eseguire l'override di proprietà, metodi ed eventi della classe di base. Per iniziare, vedere [procedura: sviluppare un controllo di Windows Forms semplice](how-to-develop-a-simple-windows-forms-control.md).  
  
 La classe base per i controlli Windows Forms, <xref:System.Windows.Forms.Control>, fornisce il plumbing necessario per la visualizzazione visiva nelle applicazioni basate su Windows sul lato client. <xref:System.Windows.Forms.Control> fornisce un handle di finestra, gestisce il routing del messaggio e fornisce gli eventi del mouse e della tastiera, oltre a molti altri eventi dell'interfaccia utente. Fornisce un layout avanzato con proprietà specifiche per la visualizzazione visiva, ad esempio <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>e molte altre. Inoltre, fornisce sicurezza, supporto del threading e interoperabilità con i controlli ActiveX. Poiché gran parte dell'infrastruttura viene definita dalla classe di base, è relativamente semplice sviluppare i propri controlli Windows Form.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Sviluppare un controllo di Windows Form semplice](how-to-develop-a-simple-windows-forms-control.md)
- [Sviluppo di un controllo di Windows Form composto](developing-a-composite-windows-forms-control.md)
- [Procedura: Creare un controllo di Windows Form che visualizzi lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
