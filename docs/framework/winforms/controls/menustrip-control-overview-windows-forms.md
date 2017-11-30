---
title: Cenni preliminari sul controllo MenuStrip (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 06cd4e812f4acf546dad577a2e1ddc571281ebe3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="menustrip-control-overview-windows-forms"></a>Cenni preliminari sul controllo MenuStrip (Windows Form)
I menu espongono funzionalità agli utenti tenendo i comandi che vengono raggruppati in base a un tema comune.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo è una novità di questa versione di Visual Studio e .NET Framework. Con il controllo, è possibile creare facilmente menu simili a quelle disponibili in Microsoft Office.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo supporta l'interfaccia a documenti multipli (MDI) e l'unione di menu, descrizioni comandi e overflow. È possibile migliorare l'usabilità e migliorare la leggibilità dei menu tramite l'aggiunta di chiavi di accesso, tasti di scelta rapida, segni di spunta, immagini e le barre di separazione.  
  
 Il <xref:System.Windows.Forms.MenuStrip> controllo sostituisce e aggiunge la funzionalità per il <xref:System.Windows.Forms.MainMenu> controllo, tuttavia, il <xref:System.Windows.Forms.MainMenu> controllo viene mantenuto per compatibilità con le versioni precedenti e per utilizzo futuro, se si sceglie.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Modalità di utilizzo del controllo MenuStrip  
 Utilizzare il <xref:System.Windows.Forms.MenuStrip> il controllo a:  
  
-   Creare facilmente un personalizzato, impiego frequente menu che supportano utente interfaccia e il layout funzionalità avanzate, ad esempio testo e immagine di ordinamento e l'allineamento, operazioni di trascinamento e rilascio, MDI, overflow e modalità alternative di accesso ai comandi di menu.  
  
-   Supporta l'aspetto tipico e il comportamento del sistema operativo.  
  
-   Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo gestire gli eventi per altri controlli.  
  
 La tabella seguente illustra alcune proprietà particolarmente importanti di <xref:System.Windows.Forms.MenuStrip> e classi associate.  
  
|Proprietà|Descrizione|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Ottiene o imposta il <xref:System.Windows.Forms.ToolStripMenuItem> utilizzato per visualizzare un elenco di form figlio MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Ottiene o imposta il menu figlio vengono uniti ai menu padre nelle applicazioni MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Ottiene o imposta la posizione di un elemento unito all'interno di un menu nelle applicazioni MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Ottiene o imposta un valore che indica se il form è un contenitore per form figlio MDI.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Ottiene o imposta un valore che indica se le descrizioni comandi vengono visualizzate per il <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Ottiene o imposta un valore che indica se il controllo <xref:System.Windows.Forms.MenuStrip> supporta la funzionalità di overflow.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Ottiene o imposta i tasti di scelta rapida associati il <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Ottiene o imposta un valore che indica se i tasti di scelta rapida sono associati i <xref:System.Windows.Forms.ToolStripMenuItem> sono visualizzati accanto al <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 La tabella seguente illustra l'importante <xref:System.Windows.Forms.MenuStrip> classi correlate.  
  
|Classe|Descrizione|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Rappresenta un'opzione selezionabile visualizzata in un <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Viene visualizzato un menu di scelta rapida.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Rappresenta un controllo che consente all'utente di selezionare un singolo elemento da un elenco che viene visualizzato quando l'utente sceglie un <xref:System.Windows.Forms.ToolStripDropDownButton> o una voce di menu di livello superiore.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Fornisce funzionalità di base per i controlli derivano da <xref:System.Windows.Forms.ToolStripItem> che visualizzano gli elementi di elenco a discesa quando si fa clic.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
