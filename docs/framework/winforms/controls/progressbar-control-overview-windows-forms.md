---
title: Cenni preliminari sul controllo ProgressBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: 7dd434492cd688527ddbce5aaffa442a0b40a9e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968310"
---
# <a name="progressbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo ProgressBar (Windows Form)
> [!IMPORTANT]
> Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Il controllo <xref:System.Windows.Forms.ProgressBar> Windows Forms indica lo stato di avanzamento di un processo visualizzando un numero appropriato di rettangoli disposti in una barra orizzontale. Al termine del processo, la barra viene compilata. Gli indicatori di stato vengono comunemente usati per fornire all'utente un'idea del tempo di attesa per il completamento di un processo. ad esempio, quando viene caricato un file di grandi dimensioni.  
  
> [!NOTE]
> Il <xref:System.Windows.Forms.ProgressBar> controllo può essere orientato solo orizzontalmente sul form.  
  
## <a name="key-properties-and-methods"></a>Proprietà e metodi chiave  
 Le <xref:System.Windows.Forms.ProgressBar> proprietà chiave del controllo sono <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>e <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Le <xref:System.Windows.Forms.ProgressBar.Minimum%2A> proprietà <xref:System.Windows.Forms.ProgressBar.Maximum%2A> e impostano i valori massimi e minimi che possono essere visualizzati nell'indicatore di stato. La <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà rappresenta lo stato di avanzamento che è stato eseguito per completare l'operazione. Poiché la barra visualizzata nel controllo è costituita da blocchi, il valore visualizzato dal <xref:System.Windows.Forms.ProgressBar> controllo indica solo il <xref:System.Windows.Forms.ProgressBar.Value%2A> valore corrente della proprietà. In base alla dimensione del <xref:System.Windows.Forms.ProgressBar> controllo, la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà determina quando visualizzare il blocco successivo.  
  
 Il modo più comune per aggiornare il valore di stato corrente è scrivere codice per impostare la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà. Nell'esempio relativo al caricamento di un file di grandi dimensioni, è possibile impostare il valore massimo per le dimensioni del file, espressa in kilobyte. Se, ad esempio, <xref:System.Windows.Forms.ProgressBar.Maximum%2A> la proprietà è impostata su 100, <xref:System.Windows.Forms.ProgressBar.Minimum%2A> la proprietà è impostata su 10 e la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà è impostata su 50, verranno visualizzati 5 rettangoli. Questa è la metà del numero che è possibile visualizzare.  
  
 Tuttavia, esistono altri modi per modificare il valore visualizzato dal <xref:System.Windows.Forms.ProgressBar> controllo, oltre a impostare direttamente la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà. La <xref:System.Windows.Forms.ProgressBar.Step%2A> proprietà può essere utilizzata per specificare un valore in base al <xref:System.Windows.Forms.ProgressBar.Value%2A> quale incrementare la proprietà. Quindi, la chiamata <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> al metodo incrementerà il valore. Per variare il valore di incremento, è possibile usare <xref:System.Windows.Forms.ProgressBar.Increment%2A> il metodo e specificare un valore con cui incrementare <xref:System.Windows.Forms.ProgressBar.Value%2A> la proprietà.  
  
 Un altro controllo che informa graficamente l'utente di un'azione corrente è il <xref:System.Windows.Forms.StatusBar> controllo.  
  
> [!IMPORTANT]
> I <xref:System.Windows.Forms.StatusStrip> controlli <xref:System.Windows.Forms.ToolStripStatusLabel> e <xref:System.Windows.Forms.StatusBar> sostituiscono e aggiungono funzionalità ai <xref:System.Windows.Forms.StatusBarPanel> controlli e; tuttavia, <xref:System.Windows.Forms.StatusBar> i <xref:System.Windows.Forms.StatusBarPanel> controlli e vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se scegliere.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ProgressBar>
- [Controllo ProgressBar](progressbar-control-windows-forms.md)
