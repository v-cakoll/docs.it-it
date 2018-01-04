---
title: Cenni preliminari sul controllo ToolStrip (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 45dab820072b3eb0bcc448ce32251e3ff5a3e622
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="toolstrip-control-overview-windows-forms"></a>Cenni preliminari sul controllo ToolStrip (Windows Form)
Windows Form <xref:System.Windows.Forms.ToolStrip> controllo e le classi associate forniscono un framework comune per combinare gli elementi dell'interfaccia utente nelle barre degli strumenti, barre di stato e menu. <xref:System.Windows.Forms.ToolStrip>controlli offrono esperienze in fase di progettazione che include l'attivazione sul posto e la modifica, layout personalizzato e raggruppamento verticale/orizzontale, ovvero la possibilità di barre degli strumenti di condividere lo spazio orizzontale o verticale.  
  
 Sebbene <xref:System.Windows.Forms.ToolStrip> sostituisca e funzionalità per il controllo nelle versioni precedenti, <xref:System.Windows.Forms.ToolBar> viene mantenuto per compatibilità con le versioni precedenti e un utilizzo futuro, se si desidera.  
  
## <a name="features-of-the-toolstrip-controls"></a>Funzionalità dei controlli ToolStrip  
 Utilizzare il <xref:System.Windows.Forms.ToolStrip> il controllo a:  
  
-   Presentare un'interfaccia utente comune tra contenitori.  
  
-   Creare facilmente personalizzato, impiego frequente barre degli strumenti che supportano avanzate funzionalità di layout e l'interfaccia utente, ad esempio ancoraggio, raggruppamento verticale/orizzontale, i pulsanti con testo e immagini, caselle di riepilogo e i controlli, pulsanti di overflow e in fase di esecuzione riordinamento di <xref:System.Windows.Forms.ToolStrip> elementi.  
  
-   Supportano l'overflow e il riordino degli elementi in fase di esecuzione. La funzionalità di overflow sposta gli elementi in un menu a discesa quando non vi è spazio sufficiente per visualizzarli in un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Supporta l'aspetto tipico e il comportamento del sistema operativo tramite un modello comune di rendering.  
  
-   Gestire gli eventi in modo coerente per tutti i contenitori e gli elementi contenuti, nello stesso modo gestire gli eventi per altri controlli.  
  
-   Trascinare gli elementi da una <xref:System.Windows.Forms.ToolStrip> a un altro o in un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Creare i controlli elenco a discesa e utente editor di tipi di interfaccia con layout avanzati in un <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Utilizzare il <xref:System.Windows.Forms.ToolStripControlHost> classe da utilizzare altri controlli in un <xref:System.Windows.Forms.ToolStrip> e ottenere <xref:System.Windows.Forms.ToolStrip> funzionalità relativa.  
  
 È possibile estendere le funzionalità e modificare l'aspetto e il comportamento tramite il <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, e <xref:System.Windows.Forms.ToolStripManager> lungo con il <xref:System.Windows.Forms.ToolStripRenderMode> e <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumerazioni.  
  
 Il <xref:System.Windows.Forms.ToolStrip> controllo è particolarmente configurabile ed estendibile e fornisce molte proprietà, metodi ed eventi per personalizzare l'aspetto e comportamento. Di seguito sono alcuni membri importanti:  
  
### <a name="important-toolstrip-members"></a>Membri importanti di ToolStrip  
  
|nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Ottiene o imposta il bordo del contenitore padre un <xref:System.Windows.Forms.ToolStrip> è ancorato.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Ottiene o imposta un valore che indica se le operazioni di trascinamento della selezione e ridisposizione degli elementi devono essere gestite privatamente dalla classe <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Ottiene o imposta un valore che indica come il <xref:System.Windows.Forms.ToolStrip> definisce i relativi elementi.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Ottiene o imposta se un <xref:System.Windows.Forms.ToolStripItem> è collegato il <xref:System.Windows.Forms.ToolStrip> o <xref:System.Windows.Forms.ToolStripOverflowButton> oppure può spostarsi tra i due.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Ottiene un valore che indica se un <xref:System.Windows.Forms.ToolStripItem> Visualizza altri elementi in un elenco a discesa elenco quando la <xref:System.Windows.Forms.ToolStripItem> si fa clic.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Ottiene l'oggetto <xref:System.Windows.Forms.ToolStripItem> che rappresenta il pulsante di overflow di un oggetto <xref:System.Windows.Forms.ToolStrip> con l'overflow abilitato.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Ottiene o imposta un <xref:System.Windows.Forms.ToolStripRenderer> consentono di personalizzare l'aspetto e comportamento (aspetto) di un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Ottiene o imposta gli stili di disegno da applicare per il <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Eccezione generata quando il <xref:System.Windows.Forms.ToolStrip.Renderer%2A> le modifiche alle proprietà.|  
  
 Il <xref:System.Windows.Forms.ToolStrip> flessibilità del controllo viene ottenuta tramite l'utilizzo di un numero di classi correlate. Di seguito sono riportate alcune la più importante:  
  
### <a name="important-toolstrip-companion-classes"></a>Classi importanti correlate al controllo ToolStrip  
  
|nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Sostituisce e aggiunge la funzionalità per la <xref:System.Windows.Forms.MainMenu> classe.|  
|<xref:System.Windows.Forms.StatusStrip>|Sostituisce e aggiunge la funzionalità per la <xref:System.Windows.Forms.StatusBar> classe.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Sostituisce e aggiunge la funzionalità per la <xref:System.Windows.Forms.ContextMenu> classe.|  
|<xref:System.Windows.Forms.ToolStripItem>|Classe base astratta che gestisce gli eventi e il layout per tutti gli elementi che un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, o <xref:System.Windows.Forms.ToolStripDropDown> può contenere.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Fornisce un contenitore con un pannello su ciascun lato del form in cui è possibile disporre i controlli in vari modi.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Gestisce la funzionalità di disegno per <xref:System.Windows.Forms.ToolStrip> oggetti.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Fornisce l'aspetto di stile Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controlli <xref:System.Windows.Forms.ToolStrip> per il rendering e il raggruppamento e l'unione di <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, e <xref:System.Windows.Forms.ToolStripMenuItem> oggetti.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Specifica lo stile di disegno (personalizzato, Windows XP o Microsoft Office Professional) applicato a più <xref:System.Windows.Forms.ToolStrip> oggetti contenuti in un form.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Specifica lo stile di disegno (personalizzato, Windows XP o Microsoft Office Professional) applicato a un <xref:System.Windows.Forms.ToolStrip> oggetto contenuto in un form.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Ospita altri controlli che non sono in particolare <xref:System.Windows.Forms.ToolStrip> controlli ma per il quale <xref:System.Windows.Forms.ToolStrip> funzionalità.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Specifica se un <xref:System.Windows.Forms.ToolStripItem> deve essere disposto in principale <xref:System.Windows.Forms.ToolStrip>, l'overflow <xref:System.Windows.Forms.ToolStrip>, o entrambe le opzioni.|  
  
 Per ulteriori informazioni, vedere [riepilogo della tecnologia ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) e [architettura del controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
