---
title: Panoramica del controllo ProgressBar
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: a0c4a0401d06614ab3ad148b932ebc64080c592c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741288"
---
# <a name="progressbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo ProgressBar (Windows Form)
> [!IMPORTANT]
> Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il controllo Windows Forms <xref:System.Windows.Forms.ProgressBar> indica lo stato di avanzamento di un processo visualizzando un numero appropriato di rettangoli disposti in una barra orizzontale. Al termine del processo, la barra viene compilata. Gli indicatori di stato vengono comunemente usati per fornire all'utente un'idea del tempo di attesa per il completamento di un processo. ad esempio, quando viene caricato un file di grandi dimensioni.  
  
> [!NOTE]
> Il controllo <xref:System.Windows.Forms.ProgressBar> può essere orientato solo orizzontalmente sul form.  
  
## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave  
 Le proprietà chiave del controllo <xref:System.Windows.Forms.ProgressBar> sono <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>e <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Le proprietà <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> consentono di impostare i valori massimo e minimo che possono essere visualizzati nell'indicatore di stato. La proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A> rappresenta lo stato di avanzamento che è stato eseguito per completare l'operazione. Poiché la barra visualizzata nel controllo è costituita da blocchi, il valore visualizzato dal controllo <xref:System.Windows.Forms.ProgressBar> approssimatamente al valore corrente della proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A>. In base alla dimensione del controllo <xref:System.Windows.Forms.ProgressBar>, la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A> determina quando visualizzare il blocco successivo.  
  
 Il modo più comune per aggiornare il valore di stato corrente è scrivere codice per impostare la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A>. Nell'esempio relativo al caricamento di un file di grandi dimensioni, è possibile impostare il valore massimo per le dimensioni del file, espressa in kilobyte. Se, ad esempio, la proprietà <xref:System.Windows.Forms.ProgressBar.Maximum%2A> è impostata su 100, la proprietà <xref:System.Windows.Forms.ProgressBar.Minimum%2A> è impostata su 10 e la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A> è impostata su 50, verranno visualizzati 5 rettangoli. Questa è la metà del numero che è possibile visualizzare.  
  
 Tuttavia, esistono altri modi per modificare il valore visualizzato dal controllo <xref:System.Windows.Forms.ProgressBar>, oltre a impostare direttamente la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A>. È possibile utilizzare la proprietà <xref:System.Windows.Forms.ProgressBar.Step%2A> per specificare un valore per incrementare la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A>. Quindi, la chiamata del metodo <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> incrementerà il valore. Per variare il valore di incremento, è possibile usare il metodo <xref:System.Windows.Forms.ProgressBar.Increment%2A> e specificare un valore con cui incrementare la proprietà <xref:System.Windows.Forms.ProgressBar.Value%2A>.  
  
 Un altro controllo che informa graficamente l'utente di un'azione corrente è il controllo <xref:System.Windows.Forms.StatusBar>.  
  
> [!IMPORTANT]
> I controlli <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel>; Tuttavia, se si sceglie, i controlli <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ProgressBar>
- [Controllo ProgressBar](progressbar-control-windows-forms.md)
