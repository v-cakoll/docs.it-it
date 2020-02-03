---
title: Cenni preliminari sul controllo LinkLabel
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 9837902bf56a402d623adbcf41558dcc568b7105
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745217"
---
# <a name="linklabel-control-overview-windows-forms"></a>Cenni preliminari sul controllo LinkLabel (Windows Form)
Il controllo Windows Forms <xref:System.Windows.Forms.LinkLabel> consente di aggiungere collegamenti di tipo Web alle applicazioni di Windows Forms. È possibile utilizzare il controllo <xref:System.Windows.Forms.LinkLabel> per tutti gli elementi per cui è possibile utilizzare il controllo <xref:System.Windows.Forms.Label> per; è anche possibile impostare parte del testo come collegamento a un file, a una cartella o a una pagina Web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Operazioni possibili con il controllo LinkLabel  
 Oltre a tutte le proprietà, i metodi e gli eventi del controllo <xref:System.Windows.Forms.Label>, il controllo <xref:System.Windows.Forms.LinkLabel> dispone di proprietà per i collegamenti ipertestuali e i colori dei collegamenti. La proprietà <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> imposta l'area del testo che attiva il collegamento. Le proprietà <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>e <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> impostano i colori del collegamento. L'evento <xref:System.Windows.Forms.LinkLabel.LinkClicked> determina cosa accade quando viene selezionato il testo del collegamento.  
  
 L'uso più semplice del controllo <xref:System.Windows.Forms.LinkLabel> consiste nel visualizzare un singolo collegamento usando la proprietà <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, ma è anche possibile visualizzare più collegamenti ipertestuali usando la proprietà <xref:System.Windows.Forms.LinkLabel.Links%2A>. Il <xref:System.Windows.Forms.LinkLabel.Links%2A> proprietà consente di accedere a una raccolta di collegamenti. È anche possibile specificare i dati nella proprietà <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> di ogni singolo <xref:System.Windows.Forms.LinkLabel.Link> oggetto. Il valore della proprietà <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> può essere utilizzato per archiviare il percorso di un file da visualizzare o l'indirizzo di un sito Web.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel>
- [Panoramica sul controllo Label](label-control-overview-windows-forms.md)
- [Procedura: Eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Procedura: Modificare l'aspetto del controllo LinkLabel di Windows Form](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
