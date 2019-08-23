---
title: 'Procedura: Bloccare i controlli di Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: 9eb762a9691a6127e2419f9ddc25f3010d3383fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966530"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Procedura: Bloccare i controlli di Windows Forms
Quando si progetta l'interfaccia utente dell'applicazione Windows, è possibile bloccare i controlli una volta posizionati correttamente, in modo che non vengano spostati o ridimensionati inavvertitamente durante l'impostazione di altre proprietà.

 Inoltre, è possibile bloccare e sbloccare tutti i controlli del form contemporaneamente, che risulta utile per i moduli con molti controlli oppure è possibile sbloccare singoli controlli. Dopo aver inserito tutti i controlli in cui si desidera nel form, bloccarli tutti sul posto per evitare un movimento errato.

## <a name="to-lock-a-control"></a>Per bloccare un controllo

1. Nella finestra **Proprietà** fare clic sulla proprietà **Locked** e selezionare `true`. Facendo doppio clic sul nome, l'impostazione della proprietà viene attivata o disattivata.

     In alternativa, fare clic con il pulsante destro del mouse sul controllo e scegliere **Blocca controlli**.

    > [!NOTE]
    > I controlli di blocco ne impediscono il trascinamento in una nuova dimensione o posizione nell'area di progettazione. Tuttavia, è comunque possibile modificare la dimensione o la posizione dei controlli per mezzo della finestra **Proprietà** o nel codice.

## <a name="to-lock-all-the-controls-on-a-form"></a>Per bloccare tutti i controlli in un form

1. Scegliere **Blocca controlli**dal menu **formato** .

    > [!NOTE]
    > Questo comando blocca anche le dimensioni del form, perché un modulo è un controllo.

## <a name="to-unlock-all-locked-controls-on-a-form"></a>Per sbloccare tutti i controlli bloccati in un form

1. Scegliere **Blocca controlli**dal menu **formato** .

     Tutti i controlli bloccati in precedenza nel modulo sono ora sbloccati.

## <a name="to-unlock-locked-controls-individually"></a>Per sbloccare singolarmente i controlli bloccati

1. Nella finestra **Proprietà** fare clic sulla proprietà **Locked** e selezionare `false`. Facendo doppio clic sul nome, l'impostazione della proprietà viene attivata o disattivata.

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
