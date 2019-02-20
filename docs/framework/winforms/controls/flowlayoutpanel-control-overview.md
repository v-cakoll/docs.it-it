---
title: Cenni preliminari sul controllo FlowLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
ms.openlocfilehash: 2b08566f4b13ed54bfc0bb83c39777410251dafa
ms.sourcegitcommit: acd8ed14fe94e9d4e3a7fb685fe83d05e941073c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2019
ms.locfileid: "56441775"
---
# <a name="flowlayoutpanel-control-overview"></a>Cenni preliminari sul controllo FlowLayoutPanel
Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> dispone i contenuti in una direzione di flusso orizzontale o verticale. È possibile eseguire il wrapping dei contenuti del controllo da una riga a quella successiva o da una colonna a quella successiva. In alternativa, è possibile troncare i contenuti.  
  
 È possibile specificare la direzione del flusso impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>. Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> inverte correttamente la direzione del flusso nei layout da destra a sinistra (RTL, Right-To-Left). È anche possibile specificare se i contenuti del controllo <xref:System.Windows.Forms.FlowLayoutPanel> vengono sottoposti a wrapping o troncati impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>.  
  
 Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> viene automaticamente ridimensionato in base ai contenuti quando si imposta la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> su `true`. Fornisce inoltre una **FlowBreak** proprietà ai controlli figlio. Impostando il valore della proprietà FlowBreak su `true` , il controllo <xref:System.Windows.Forms.FlowLayoutPanel> interrompe il layout dei controlli nella direzione di flusso corrente ed esegue il wrapping alla riga o colonna successiva.  
  
 Qualsiasi controllo Windows Form può essere figlio del controllo <xref:System.Windows.Forms.FlowLayoutPanel>, tra cui altre istanze di <xref:System.Windows.Forms.FlowLayoutPanel>. Con questa funzionalità, è possibile costruire layout sofisticati in grado di adattarsi alle dimensioni del form in fase di esecuzione.  
  
 Vedere anche [procedura dettagliata: Disposizione dei controlli in Windows Form usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>
- <xref:System.Windows.Forms.TableLayoutPanel>
- [Controllo FlowLayoutPanel](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
