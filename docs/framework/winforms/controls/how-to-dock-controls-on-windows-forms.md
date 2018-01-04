---
title: 'Procedura: ancorare i controlli in Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc7227ee46f127070b44771a56a89b82bd0930ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a>Procedura: ancorare i controlli in Windows Form
È possibile ancorare i controlli ai bordi dei form o inserire il contenitore del controllo (un form o un controllo contenitore). Ad esempio, Esplora ancora relativo <xref:System.Windows.Forms.TreeView> controllo sul lato sinistro della finestra e il relativo <xref:System.Windows.Forms.ListView> controllo sul lato destro della finestra. Utilizzare il <xref:System.Windows.Forms.Control.Dock%2A> proprietà per tutti i controlli Windows Form visibili definire la modalità di ancoraggio.  
  
> [!NOTE]
>  I controlli vengono ancorati in ordine inverso.  
  
 Il <xref:System.Windows.Forms.Control.Dock%2A> proprietà interagisce con il <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà. Per ulteriori informazioni, vedere [Cenni preliminari sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md).  
  
### <a name="to-dock-a-control"></a>Per ancorare un controllo  
  
1.  Selezionare il controllo che si desidera ancorare.  
  
2.  Nella finestra Proprietà fare clic sulla freccia a destra della <xref:System.Windows.Forms.Control.Dock%2A> proprietà.  
  
     Viene visualizzato un editor che mostra una serie di finestre che rappresenta i bordi e il centro del form.  
  
3.  Fare clic sul pulsante che rappresenta il bordo del form in cui si desidera ancorare il controllo. Per riempire il contenuto del modulo del controllo o controllo contenitore, fare clic sulla casella al centro. Fare clic su **(nessuno)** per disabilitare l'ancoraggio.  
  
     Il controllo viene ridimensionato automaticamente per adattarsi ai limiti del bordo ancorato.  
  
    > [!NOTE]
    >  I controlli ereditati devono essere `Protected` per poter essere ancorata. Per modificare il livello di accesso di un controllo, impostare il relativo **modificatore** proprietà nella finestra Proprietà.  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [Procedura: Agganciare e ancorare controlli figlio in un controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [Panoramica sulla proprietà AutoSize](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [Procedura: Agganciare i controlli in Windows Form](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
