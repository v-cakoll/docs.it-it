---
title: Nozioni fondamentali sullo sviluppo di controlli Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], derivation types
- programming concepts [Windows Forms], Windows Forms controls
- controls [Windows Forms], creating
ms.assetid: 6277bb81-90f7-4c5b-9f4b-b02bb42dd316
ms.openlocfilehash: 21b8b08e56e8b4d48fb738b86247d3f04dc4150b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759869"
---
# <a name="windows-forms-control-development-basics"></a>Nozioni fondamentali sullo sviluppo di controlli Windows Form
Un controllo Windows Form è una classe che deriva direttamente o indirettamente da <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Nell'elenco seguente vengono descritti scenari comuni per lo sviluppo di controlli Windows Form:  
  
- Combinazione di controlli esistenti per creare un controllo composito.  
  
     I controlli compositi incapsulano un'interfaccia utente che può essere riutilizzata come un controllo. Un esempio di un controllo composito è un controllo che è costituito da una casella di testo e un pulsante Reimposta. Finestre di progettazione visiva offrono supporto avanzato per la creazione di controlli composti. Per modificare un controllo composito, derivarlo da <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>. La classe di base <xref:System.Windows.Forms.UserControl> fornisce il routing della tastiera per controlli figlio e consente ai controlli figlio di funzionare come gruppo. Per altre informazioni, vedere [Sviluppo di un controllo Windows Form composito](developing-a-composite-windows-forms-control.md).  
  
- Estensione di un controllo esistente per personalizzarla o per aggiungere alle relative funzionalità.  
  
     Un pulsante di cui colore non può essere modificato e un pulsante che ha una proprietà aggiuntiva che tiene traccia di quante volte è stato fatto clic sono esempi di controlli estesi. È possibile personalizzare qualsiasi controllo Windows Form che deriva da quest'ultimo e si esegue l'override o aggiungendo proprietà, metodi ed eventi.  
  
- Modifica di un controllo che non combinare o estendere i controlli esistenti.  
  
     In questo scenario, derivarlo dalla classe di base <xref:System.Windows.Forms.Control>. È possibile aggiungere, nonché eseguire l'override di proprietà, metodi ed eventi della classe di base. Per iniziare, vedere [come: Sviluppare un controllo Form Windows semplice](how-to-develop-a-simple-windows-forms-control.md).  
  
 La classe base per controlli Windows Form, <xref:System.Windows.Forms.Control>, fornisce l'infrastruttura necessaria per la visualizzazione nelle applicazioni basate su Windows client-side. <xref:System.Windows.Forms.Control> fornisce un handle di finestra, gestisce il routing dei messaggi e fornisce gli eventi di mouse e tastiera, oltre a molti altri utenti dell'interfaccia eventi. Fornisce un layout avanzato e ha le proprietà specifiche per la visualizzazione, ad esempio <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>e molti altri. Inoltre, offre sicurezza, supporto del threading e l'interoperabilità con i controlli ActiveX. Poiché gran parte dell'infrastruttura viene definita dalla classe di base, è relativamente semplice sviluppare i propri controlli Windows Form.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Sviluppare un controllo di semplice Windows Form](how-to-develop-a-simple-windows-forms-control.md)
- [Sviluppo di un controllo di Windows Form composto](developing-a-composite-windows-forms-control.md)
- [Procedura: Creare un controllo di Windows Form che mostra lo stato di avanzamento](how-to-create-a-windows-forms-control-that-shows-progress.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
