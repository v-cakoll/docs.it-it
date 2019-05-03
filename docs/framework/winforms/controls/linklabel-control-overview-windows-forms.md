---
title: Cenni preliminari sul controllo LinkLabel (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 541467b0f1285d372e5f6d502d9d8f28c8c6333e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012958"
---
# <a name="linklabel-control-overview-windows-forms"></a>Cenni preliminari sul controllo LinkLabel (Windows Form)
I moduli di Windows <xref:System.Windows.Forms.LinkLabel> controllo consente di aggiungere collegamenti ipertestuali alle applicazioni Windows Form. È possibile usare la <xref:System.Windows.Forms.LinkLabel> controllo di tutto ciò che è possibile usare il <xref:System.Windows.Forms.Label> controllare per; è anche possibile impostare una parte del testo come un collegamento a un file, cartella o pagina Web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Operazioni eseguibili con il controllo LinkLabel  
 Oltre a tutte le proprietà, metodi e gli eventi dei <xref:System.Windows.Forms.Label> (controllo), il <xref:System.Windows.Forms.LinkLabel> controllo dispone di proprietà per i collegamenti ipertestuali e i colori di collegamento. Il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà imposta l'area di testo che attiva il collegamento. Il <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>, e <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> impostano i colori del collegamento. Il <xref:System.Windows.Forms.LinkLabel.LinkClicked> eventi determinano ciò che accade quando si seleziona il testo del collegamento.  
  
 L'uso più semplice del <xref:System.Windows.Forms.LinkLabel> controllo consiste nel visualizzare un singolo collegamento usando il <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà, ma è anche possibile visualizzare più collegamenti ipertestuali utilizzando il <xref:System.Windows.Forms.LinkLabel.Links%2A> proprietà. Il <xref:System.Windows.Forms.LinkLabel.Links%2A> proprietà consente di accedere a una raccolta di collegamenti. È inoltre possibile specificare i dati nel <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> proprietà di ogni singolo <xref:System.Windows.Forms.LinkLabel.Link> oggetto. Il valore della <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> proprietà può essere utilizzata per archiviare il percorso di un file di visualizzazione o l'indirizzo di un sito Web.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel>
- [Panoramica sul controllo Label](label-control-overview-windows-forms.md)
- [Procedura: Collegarsi a un oggetto o Web Page con il controllo LinkLabel di Windows Form](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Procedura: Modificare l'aspetto del controllo Windows Form LinkLabel](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
