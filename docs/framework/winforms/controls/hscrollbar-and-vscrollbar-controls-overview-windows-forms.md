---
title: Cenni preliminari sui controlli HScrollBar e VScrollBar
ms.date: 03/30/2017
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
ms.openlocfilehash: abe0c8da9723f17cb80715454f6ab7297724a21f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728169"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Cenni preliminari sui controlli HScrollBar e VScrollBar (Windows Form)
Windows Forms controlli <xref:System.Windows.Forms.ScrollBar> vengono utilizzati per semplificare la navigazione attraverso un lungo elenco di elementi o una grande quantità di informazioni scorrendo orizzontalmente o verticalmente all'interno di un'applicazione o di un controllo. Le barre di scorrimento sono un elemento comune dell'interfaccia di Windows, pertanto il controllo <xref:System.Windows.Forms.ScrollBar> viene spesso usato con controlli che non derivano dalla classe <xref:System.Windows.Forms.ScrollableControl>. Allo stesso modo, molti sviluppatori scelgono di incorporare il controllo <xref:System.Windows.Forms.ScrollBar> durante la creazione dei propri controlli utente.  
  
 I controlli <xref:System.Windows.Forms.HScrollBar> (orizzontali) e <xref:System.Windows.Forms.VScrollBar> (verticali) funzionano indipendentemente da altri controlli e hanno un proprio set di eventi, proprietà e metodi. i controlli <xref:System.Windows.Forms.ScrollBar> non sono uguali alle barre di scorrimento predefinite collegate a caselle di testo, caselle di riepilogo, caselle combinate o form MDI (il controllo <xref:System.Windows.Forms.TextBox> dispone di una proprietà <xref:System.Windows.Forms.TextBox.ScrollBars%2A> per mostrare o nascondere le barre di scorrimento collegate al controllo).  
  
 I controlli <xref:System.Windows.Forms.ScrollBar> utilizzano l'evento <xref:System.Windows.Forms.ScrollBar.Scroll> per monitorare lo spostamento della casella di scorrimento (talvolta definita cursore) lungo la barra di scorrimento. L'utilizzo dell'evento <xref:System.Windows.Forms.ScrollBar.Scroll> consente di accedere al valore della barra di scorrimento mentre viene trascinato.  
  
## <a name="value-property"></a>Proprietà Value  
 La proprietà <xref:System.Windows.Forms.ScrollBar.Value%2A> (che, per impostazione predefinita, è 0) è un valore `integer` corrispondente alla posizione della casella di scorrimento nella barra di scorrimento. Quando la posizione della casella di scorrimento è impostata sul valore minimo, viene spostata nella posizione più a sinistra (per le barre di scorrimento orizzontali) o nella posizione superiore (per le barre di scorrimento verticali). Quando la casella di scorrimento è impostata sul valore massimo, la casella di scorrimento viene spostata nella posizione più a destra o in basso. Analogamente, un valore a metà tra la parte inferiore e la parte superiore dell'intervallo posiziona il bordo iniziale della casella di scorrimento al centro della barra di scorrimento.  
  
 Oltre a usare i clic del mouse per modificare il valore della barra di scorrimento, un utente può anche trascinare la casella di scorrimento in un punto lungo la barra. Il valore risultante dipende dalla posizione della casella di scorrimento, ma è sempre compreso nell'intervallo del <xref:System.Windows.Forms.ScrollBar.Minimum%2A> <xref:System.Windows.Forms.ScrollBar.Maximum%2A> proprietà impostate dall'utente.  
  
## <a name="largechange-and-smallchange-properties"></a>Proprietà LargeChange e SmallChange  
 Quando l'utente preme il tasto PGSU o PGGIÙ o fa clic sull'indicatore di avanzamento della barra di scorrimento su entrambi i lati della casella di scorrimento, la proprietà <xref:System.Windows.Forms.ScrollBar.Value%2A> cambia in base al valore impostato nella proprietà <xref:System.Windows.Forms.ScrollBar.LargeChange%2A>.  
  
 Quando l'utente preme uno dei tasti di direzione o fa clic su uno dei pulsanti della barra di scorrimento, la proprietà <xref:System.Windows.Forms.ScrollBar.Value%2A> cambia in base al valore impostato nella proprietà <xref:System.Windows.Forms.ScrollBar.SmallChange%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.HScrollBar>
- <xref:System.Windows.Forms.VScrollBar>
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
