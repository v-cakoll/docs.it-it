---
title: 'Procedura: bloccare i controlli di un Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a0bd0f8dcde95dcbb5ef8fcf398256b6931859c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Procedura: bloccare i controlli di un Windows Form
Quando si progetta l'interfaccia utente (UI) dell'applicazione Windows, è possibile bloccare i controlli di una volta posizionati correttamente, in modo che non vengano spostati o ridimensionati quando si impostano altre proprietà inavvertitamente.  
  
 Inoltre, è possibile bloccare e sbloccare tutti i controlli del form in una sola volta, che è utile per i moduli con molti controlli, o è possibile sbloccare singoli controlli. Dopo aver posizionato tutti i controlli in cui si desidera utilizzarle sul form, bloccarle tutte per evitare lo spostamento errato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-lock-a-control"></a>Per bloccare un controllo  
  
1.  Nel **proprietà** finestra, fare clic su di **bloccato** proprietà e selezionare `true`. (Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)  
  
     In alternativa, il pulsante destro del controllo e scegliere **Blocca controlli**.  
  
    > [!NOTE]
    >  Il blocco dei controlli impedisce trascinati nell'area di progettazione in un percorso o la nuova dimensione. Tuttavia, è possibile comunque modificare dimensioni o la posizione dei controlli mediante il **proprietà** finestra o nel codice.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>Per bloccare tutti i controlli in un form  
  
1.  Dal **formato** menu, scegliere **Blocca controlli**.  
  
    > [!NOTE]
    >  Questo comando Blocca le dimensioni del form, poiché un form è un controllo.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>Per sbloccare tutti i controlli bloccati in un form  
  
1.  Dal **formato** menu, scegliere **Blocca controlli**.  
  
     Tutti i controlli precedentemente bloccati nel form vengono sbloccate.  
  
### <a name="to-unlock-locked-controls-individually"></a>Per sbloccare singolarmente i controlli bloccati  
  
1.  Nel **proprietà** finestra, fare clic su di **bloccato** proprietà e selezionare `false`. (Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Disposizione di controlli in Windows Form](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
