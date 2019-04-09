---
title: Cenni preliminari sul controllo ProgressBar (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
ms.openlocfilehash: 24b47669cdf8ed0a8f0f936b0b3b9c354e62445f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227496"
---
# <a name="progressbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo ProgressBar (Windows Form)
> [!IMPORTANT]
>  Benché il controllo <xref:System.Windows.Forms.ToolStripProgressBar> sostituisca il controllo <xref:System.Windows.Forms.ProgressBar> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.ProgressBar> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.  
  
 I moduli di Windows <xref:System.Windows.Forms.ProgressBar> controllo indica lo stato di avanzamento di un processo mediante la visualizzazione di un numero appropriato di rettangoli in una barra orizzontale. Una volta completato il processo, la barra è piena. Indicatori di stato vengono comunemente usati per concedere all'utente un'idea di come tempo necessario per un processo da completare; ad esempio, quando un file di grandi dimensioni è il caricamento.  
  
> [!NOTE]
>  Il <xref:System.Windows.Forms.ProgressBar> controllo può solo essere orientato in senso orizzontale nel form.  
  
## <a name="key-properties-and-methods"></a>I metodi e proprietà chiave  
 Le proprietà chiave del <xref:System.Windows.Forms.ProgressBar> controllo vengono <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, e <xref:System.Windows.Forms.ProgressBar.Maximum%2A>. Il <xref:System.Windows.Forms.ProgressBar.Minimum%2A> e <xref:System.Windows.Forms.ProgressBar.Maximum%2A> proprietà impostare i valori minimi e massimo possa visualizzare l'indicatore di stato. Il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà rappresenta lo stato di avanzamento compiuto verso il completamento dell'operazione. Poiché l'indicatore visualizzato nel controllo è costituito da blocchi, il valore visualizzato per il <xref:System.Windows.Forms.ProgressBar> controllo solo un'approssimazione di <xref:System.Windows.Forms.ProgressBar.Value%2A> valore corrente della proprietà. In base alla dimensione dei <xref:System.Windows.Forms.ProgressBar> (controllo), il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà determina il momento visualizzare il blocco successivo.  
  
 Il modo più comune per aggiornare il valore di stato di avanzamento corrente consiste nello scrivere codice per impostare il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà. Nell'esempio di caricamento di un file di grandi dimensioni, è possibile impostare il valore massimo per le dimensioni del file nel kilobyte. Ad esempio, se il <xref:System.Windows.Forms.ProgressBar.Maximum%2A> è impostata su 100, il <xref:System.Windows.Forms.ProgressBar.Minimum%2A> è impostata su 10 e il <xref:System.Windows.Forms.ProgressBar.Value%2A> viene impostata su 50, verranno visualizzati i 5 rettangoli. Questa è la metà del numero di che può essere visualizzato.  
  
 Tuttavia, esistono altri modi per modificare il valore visualizzato per il <xref:System.Windows.Forms.ProgressBar> controllo, oltre all'impostazione il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà direttamente. Il <xref:System.Windows.Forms.ProgressBar.Step%2A> proprietà può essere utilizzata per specificare un valore da incrementare la <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà. Quindi, chiamare il <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> metodo incrementa il valore. Per modificare il valore di incremento, è possibile usare il <xref:System.Windows.Forms.ProgressBar.Increment%2A> metodo e specificare un valore di cui incrementare il <xref:System.Windows.Forms.ProgressBar.Value%2A> proprietà.  
  
 È un altro controllo che graficamente informa l'utente su un'operazione in corso il <xref:System.Windows.Forms.StatusBar> controllo.  
  
> [!IMPORTANT]
>  Il <xref:System.Windows.Forms.StatusStrip> e <xref:System.Windows.Forms.ToolStripStatusLabel> controlli sostituire e aggiungano funzionalità rispetto al <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli; tuttavia, il <xref:System.Windows.Forms.StatusBar> e <xref:System.Windows.Forms.StatusBarPanel> controlli vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si Scegliere.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ProgressBar>
- [Controllo ProgressBar](progressbar-control-windows-forms.md)
