---
title: Cenni preliminari sui controlli HScrollBar e VScrollBar (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- HScrollBar
- VScrollBar
helpviewer_keywords:
- ScrollBar control [Windows Forms]
- HScrollBar control [Windows Forms], about HScrollBar
- VScrollBar control [Windows Forms], about VScrollBar control
- ScrollBar control [Windows Forms], about ScrollBar control
- scroll bars [Windows Forms], about scroll bars
ms.assetid: 8b307679-1cae-41d8-99aa-3d1efd207cd6
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fbdb3778959d1691200cde49e485d8a63c6e645
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Cenni preliminari sui controlli HScrollBar e VScrollBar (Windows Form)
Windows Form <xref:System.Windows.Forms.ScrollBar> controlli vengono utilizzati per semplificare la navigazione tramite un lungo elenco di elementi o di una grande quantità di informazioni mediante lo scorrimento orizzontale o verticale all'interno di un'applicazione o un controllo. Barre di scorrimento sono un elemento comune dell'interfaccia di Windows, pertanto la <xref:System.Windows.Forms.ScrollBar> controllo viene spesso utilizzato con i controlli che non derivano dalla <xref:System.Windows.Forms.ScrollableControl> classe. Analogamente, molti sviluppatori scelgono di incorporare il <xref:System.Windows.Forms.ScrollBar> controllo durante la creazione di controlli utente personalizzati.  
  
 Il <xref:System.Windows.Forms.HScrollBar> (orizzontale) e <xref:System.Windows.Forms.VScrollBar> controlli (verticali) funzionano in modo indipendente da altri controlli e avere il proprio set di metodi, proprietà ed eventi. <xref:System.Windows.Forms.ScrollBar>i controlli non sono uguali alle barre di scorrimento predefinite associate a caselle di testo, caselle di riepilogo, caselle combinate o i form MDI (il <xref:System.Windows.Forms.TextBox> controllo ha un <xref:System.Windows.Forms.TextBox.ScrollBars%2A> proprietà per visualizzare o nascondere le barre di scorrimento sono associate al controllo).  
  
 Il <xref:System.Windows.Forms.ScrollBar> controlli utilizzano il <xref:System.Windows.Forms.ScrollBar.Scroll> evento per monitorare lo spostamento della casella di scorrimento (detta anche la casella di scorrimento) lungo la barra di scorrimento. Utilizzo di <xref:System.Windows.Forms.ScrollBar.Scroll> eventi consente di accedere al valore di barra di scorrimento viene trascinata.  
  
## <a name="value-property"></a>Proprietà Value  
 Il <xref:System.Windows.Forms.ScrollBar.Value%2A> proprietà (ovvero, per impostazione predefinita, 0) è un `integer` valore corrisponde alla posizione della casella di scorrimento nella barra di scorrimento. Una volta alla casella di scorrimento dal valore minimo, si sposta la posizione più a sinistra (per le barre di scorrimento orizzontale) o la posizione in alto (per le barre di scorrimento verticale). Quando la casella di scorrimento è il valore massimo, la casella di scorrimento portarsi all'estrema destra o posizione inferiore. Analogamente, il valore intermedio tra la parte inferiore e superiore dell'intervallo consente di posizionare il bordo iniziale della casella di scorrimento al centro della barra di scorrimento.  
  
 Oltre a utilizzare il mouse per modificare il valore della barra di scorrimento, un utente può trascinare anche la casella di scorrimento in qualsiasi punto lungo la barra. Il valore risultante dipende dalla posizione della casella di scorrimento, ma è sempre compreso tra il <xref:System.Windows.Forms.ScrollBar.Minimum%2A> a <xref:System.Windows.Forms.ScrollBar.Maximum%2A> impostate dall'utente.  
  
## <a name="largechange-and-smallchange-properties"></a>LargeChange e SmallChange  
 Quando l'utente preme il tasto PGSU o PGGIÙ o fa clic sull'indicatore di avanzamento su entrambi i lati della casella di scorrimento, il <xref:System.Windows.Forms.ScrollBar.Value%2A> le modifiche alle proprietà in base al valore impostato nel <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> proprietà.  
  
 Quando l'utente preme uno della freccia di chiavi o fa clic su uno dei pulsanti della barra di scorrimento, il <xref:System.Windows.Forms.ScrollBar.Value%2A> le modifiche alle proprietà in base al valore impostato nel <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [Aggiunte a un Windows Form per .NET Framework 2.0](http://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
