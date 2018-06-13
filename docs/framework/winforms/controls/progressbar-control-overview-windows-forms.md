---
title: Cenni preliminari sul controllo ProgressBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: bd2b9615b0061a8f2133229edb49357cde69b39e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539429"
---
# <a name="progressbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo ProgressBar (Windows Form)
> [!IMPORTANT]
>  Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 Windows Form <xref:System.Windows.Forms.ProgressBar> controllo indica lo stato di avanzamento di un processo visualizzando un numero appropriato di rettangoli in una barra orizzontale. Una volta completato il processo, la barra è piena. Indicatori di stato vengono comunemente utilizzati per consentire all'utente un'idea di come tempo necessario per un processo si completi. ad esempio, quando un file di grandi dimensioni è il caricamento.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.ProgressBar> controllo può solo essere orientato orizzontalmente nel form.  
  
## <a name="key-properties-and-methods"></a>Metodi e proprietà chiave  
 Le proprietà della chiave di <xref:System.Windows.Forms.ProgressBar> controllo sono <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, e <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Il <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> proprietà impostare i valori minimi e massimo possa visualizzare l'indicatore di stato. Il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà rappresenta lo stato di avanzamento compiuto verso il completamento dell'operazione. Poiché l'indicatore visualizzato nel controllo è composta da blocchi, il valore visualizzato per il <xref:System.Windows.Forms.ProgressBar> controllo solo un'approssimazione di <xref:System.Windows.Forms.ProgressBar.Value%2A> valore corrente della proprietà. In base alla dimensione del <xref:System.Windows.Forms.ProgressBar> (controllo), il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà determina se visualizzare il blocco successivo.  
  
 Il modo più comune per aggiornare il valore di stato di avanzamento corrente consiste nello scrivere codice per impostare il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà. Nell'esempio di caricamento di un file di grandi dimensioni, è possibile impostare il valore massimo per le dimensioni del file in kilobyte. Ad esempio, se il <xref:System.Windows.Forms.ProgressBar.Maximum%2A> è impostata su 100, il <xref:System.Windows.Forms.ProgressBar.Minimum%2A> è impostata su 10 e <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà è impostata su 50, verranno visualizzati i 5 rettangoli. Questa è la metà del numero di che può essere visualizzato.  
  
 Tuttavia, esistono altri modi per modificare il valore visualizzato per il <xref:System.Windows.Forms.ProgressBar> controllo, oltre all'impostazione di <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà direttamente. Il <xref:System.Windows.Forms.ProgressBar.Step%2A> proprietà può essere utilizzata per specificare un valore da incrementare la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà. Quindi, la chiamata di <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> metodo incrementa il valore. Per modificare il valore di incremento, è possibile utilizzare il <xref:System.Windows.Forms.ProgressBar.Increment%2A> (metodo) e specificare un valore di incremento di <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà.  
  
 Un altro controllo che un'operazione in corso graficamente informa l'utente è il <xref:System.Windows.Forms.StatusBar> controllo.  
  
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> vengono mantenuti per compatibilità con le versioni precedenti e per utilizzo futuro, se si Scegliere.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ProgressBar>  
 [Controllo ProgressBar](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
