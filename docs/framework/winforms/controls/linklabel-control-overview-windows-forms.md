---
title: Panoramica del controllo LinkLabel
ms.date: 03/30/2017
f1_keywords:
- LinkLabel
helpviewer_keywords:
- links [Windows Forms], LinkLabel control
- Label control [Windows Forms], about Label control
- LinkLabel control [Windows Forms], about LinkLabel control
ms.assetid: 9e248549-10ca-43a3-bb5e-60f583d369f1
ms.openlocfilehash: 3e8607644c858ae804e384c974b5e81c1786c6a1
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739512"
---
# <a name="linklabel-control-overview-windows-forms"></a>Cenni preliminari sul controllo LinkLabel (Windows Form)
Il controllo <xref:System.Windows.Forms.LinkLabel> Windows Form consente di aggiungere collegamenti di tipo Web alle applicazioni Windows Form.The Windows Forms control allows you to add Web-style links to Windows Forms applications. È possibile <xref:System.Windows.Forms.LinkLabel> utilizzare il controllo per <xref:System.Windows.Forms.Label> tutti gli elementi per i quali è possibile utilizzare il controllo; è inoltre possibile impostare parte del testo come collegamento a un file, una cartella o una pagina Web.  
  
## <a name="what-you-can-do-with-the-linklabel-control"></a>Operazioni che è possibile eseguire con il controllo LinkLabel  
 Oltre a tutte le proprietà, i <xref:System.Windows.Forms.Label> metodi e <xref:System.Windows.Forms.LinkLabel> gli eventi del controllo, il controllo dispone di proprietà per i collegamenti ipertestuali e i colori dei collegamenti. La <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> proprietà imposta l'area del testo che attiva il collegamento. Le <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>proprietà <xref:System.Windows.Forms.LinkLabel.ActiveLinkColor%2A> , e impostano i colori del collegamento. L'evento <xref:System.Windows.Forms.LinkLabel.LinkClicked> determina cosa accade quando viene selezionato il testo del collegamento.  
  
 L'utilizzo più <xref:System.Windows.Forms.LinkLabel> semplice del controllo consiste <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> nel visualizzare un singolo collegamento utilizzando <xref:System.Windows.Forms.LinkLabel.Links%2A> la proprietà , ma è anche possibile visualizzare più collegamenti ipertestuali utilizzando la proprietà . La <xref:System.Windows.Forms.LinkLabel.Links%2A> proprietà consente di accedere a una raccolta di collegamenti. È inoltre possibile specificare i <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> <xref:System.Windows.Forms.LinkLabel.Link> dati nella proprietà di ogni singolo oggetto. Il valore <xref:System.Windows.Forms.LinkLabel.Link.LinkData%2A> della proprietà può essere utilizzato per archiviare il percorso di un file da visualizzare o l'indirizzo di un sito Web.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.LinkLabel>
- [Cenni preliminari sul controllo Label](label-control-overview-windows-forms.md)
- [Procedura: eseguire il collegamento a un oggetto o a una pagina Web con il controllo LinkLabel di Windows Form](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [Procedura: modificare l'aspetto del controllo LinkLabel di Windows Form](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
