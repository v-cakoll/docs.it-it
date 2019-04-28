---
title: 'Procedura: Bloccare i controlli di Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: ac5fbf33564ed2dd1a030132a35b36164f777519
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638567"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Procedura: Bloccare i controlli di Windows Forms
Quando si progetta l'interfaccia utente (UI) dell'applicazione Windows, è possibile bloccare i controlli di una volta posizionati in modo corretto, in modo che non vengano spostati o li ridimensiono quando si impostano altre proprietà non inavvertitamente.  
  
 Inoltre, è possibile bloccare e sbloccare tutti i controlli del form in una sola volta, ciò è utile per i moduli con molti controlli, oppure è possibile sbloccare singoli controlli. Dopo avere impostato tutti i controlli in cui si desidera utilizzarle sul form, bloccarli in unica posizione per evitare lo spostamento non corretti.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-lock-a-control"></a>Per bloccare un controllo  
  
1. Nel **delle proprietà** finestra, fare clic sul **Locked** proprietà e selezionare `true`. (Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)  
  
     In alternativa, il pulsante destro del controllo e scegliere **controlli di blocco**.  
  
    > [!NOTE]
    >  Il blocco dei controlli ne impedisce che viene trascinato in un percorso o nuove dimensioni nella finestra di progettazione. Tuttavia, è possibile comunque modificare le dimensioni o la posizione dei controlli per mezzo del **proprietà** finestra o nel codice.  
  
### <a name="to-lock-all-the-controls-on-a-form"></a>Per bloccare tutti i controlli in un form  
  
1. Dal **formato** menu, scegliere **Blocca controlli**.  
  
    > [!NOTE]
    >  Questo comando Blocca le dimensioni del form, perché un form è un controllo.  
  
### <a name="to-unlock-all-locked-controls-on-a-form"></a>Per sbloccare tutti i controlli bloccati in un form  
  
1. Dal **formato** menu, scegliere **Blocca controlli**.  
  
     Tutti i controlli precedentemente bloccati nel form sono ora sbloccato.  
  
### <a name="to-unlock-locked-controls-individually"></a>Per sbloccare i controlli bloccati singolarmente  
  
1. Nel **delle proprietà** finestra, fare clic sul **Locked** proprietà e selezionare `false`. (Fare doppio clic sul nome attiva o disattiva l'impostazione della proprietà.)  
  
## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
