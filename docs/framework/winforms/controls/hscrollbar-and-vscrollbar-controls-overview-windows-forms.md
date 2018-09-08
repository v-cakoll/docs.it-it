---
title: Cenni preliminari sui controlli HScrollBar e VScrollBar (Windows Form)
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
ms.openlocfilehash: 2c6436e77753322733580acba5a20d6bb220f29c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205374"
---
# <a name="hscrollbar-and-vscrollbar-controls-overview-windows-forms"></a>Cenni preliminari sui controlli HScrollBar e VScrollBar (Windows Form)
Windows Form <xref:System.Windows.Forms.ScrollBar> controlli vengono utilizzati per semplificare la navigazione tramite un lungo elenco di elementi o una grande quantità di informazioni mediante lo scorrimento orizzontale o verticale all'interno di un'applicazione o un controllo. Le barre di scorrimento rappresentano un elemento comune dell'interfaccia di Windows, in modo che il <xref:System.Windows.Forms.ScrollBar> controllo viene spesso usato con i controlli che non derivano dal <xref:System.Windows.Forms.ScrollableControl> classe. In modo analogo, molti sviluppatori scelgono incorporare il <xref:System.Windows.Forms.ScrollBar> controllare quando si creano i propri controlli utente.  
  
 Il <xref:System.Windows.Forms.HScrollBar> (orizzontale) e <xref:System.Windows.Forms.VScrollBar> controlli (verticali) funzionano in modo indipendente da altri controlli e avere il proprio set di metodi, proprietà ed eventi. <xref:System.Windows.Forms.ScrollBar> i controlli non sono uguali alle barre di scorrimento incorporate sono associate a caselle di testo, caselle di riepilogo, caselle combinate o i form MDI (il <xref:System.Windows.Forms.TextBox> controllo ha un <xref:System.Windows.Forms.TextBox.ScrollBars%2A> proprietà per visualizzare o nascondere le barre di scorrimento che sono associate al controllo).  
  
 Il <xref:System.Windows.Forms.ScrollBar> controlli usano il <xref:System.Windows.Forms.ScrollBar.Scroll> evento per monitorare lo spostamento della casella di scorrimento (anche detta il controllo thumb) lungo la barra di scorrimento. Uso di <xref:System.Windows.Forms.ScrollBar.Scroll> evento consente di accedere al valore della barra di scorrimento durante il trascinamento.  
  
## <a name="value-property"></a>Proprietà Value  
 Il <xref:System.Windows.Forms.ScrollBar.Value%2A> proprietà (ovvero, per impostazione predefinita, 0) è un `integer` valore corrisponde alla posizione della casella di scorrimento nella barra di scorrimento. Una volta la posizione di casella di scorrimento dal valore minimo, sposta la posizione più a sinistra (per le barre di scorrimento orizzontale) o la posizione superiore (per le barre di scorrimento verticale). Quando la casella di scorrimento è il valore massimo, la casella si sposta al più a destra o posizione inferiore. Un valore compreso tra la parte inferiore e superiore dell'intervallo in modo analogo, posiziona il bordo iniziale della casella di scorrimento al centro della barra di scorrimento.  
  
 Oltre a utilizzare il mouse per modificare il valore della barra di scorrimento, un utente può trascinare anche la casella di scorrimento in qualsiasi punto lungo la barra. Il valore risultante dipende dalla posizione della casella di scorrimento, ma è sempre compreso tra il <xref:System.Windows.Forms.ScrollBar.Minimum%2A> a <xref:System.Windows.Forms.ScrollBar.Maximum%2A> proprietà impostate dall'utente.  
  
## <a name="largechange-and-smallchange-properties"></a>Proprietà SmallChange e LargeChange  
 Quando l'utente preme il tasto PGSU o PGGIÙ o fa clic sull'indicatore di avanzamento in entrambi i lati della casella di scorrimento, il <xref:System.Windows.Forms.ScrollBar.Value%2A> le modifiche alle proprietà in base al valore impostato <xref:System.Windows.Forms.ScrollBar.LargeChange%2A> proprietà.  
  
 Quando l'utente preme uno della freccia di tasti o fa clic su uno dei pulsanti della barra di scorrimento, il <xref:System.Windows.Forms.ScrollBar.Value%2A> le modifiche alle proprietà in base al valore impostato <xref:System.Windows.Forms.ScrollBar.SmallChange%2A> proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.HScrollBar>  
 <xref:System.Windows.Forms.VScrollBar>  
 [Aggiunte a un Windows Form per .NET Framework 2.0](https://msdn.microsoft.com/library/c61a923d-3d6a-4c8c-820c-e94c83f3f9a8)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
