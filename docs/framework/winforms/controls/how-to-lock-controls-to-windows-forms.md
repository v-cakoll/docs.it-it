---
title: Bloccare i controlli
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 16eb151dc435614e1edc82bf9f0acf3974f36690
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736242"
---
# <a name="how-to-lock-controls-to-windows-forms"></a>Procedura: bloccare i controlli per Windows Forms

Quando si progetta l'interfaccia utente dell'applicazione Windows, è possibile bloccare i controlli una volta posizionati correttamente, in modo che non vengano spostati o ridimensionati inavvertitamente durante l'impostazione di altre proprietà.

Inoltre, è possibile bloccare e sbloccare tutti i controlli del form contemporaneamente, che risulta utile per i moduli con molti controlli oppure è possibile sbloccare singoli controlli. Dopo aver inserito tutti i controlli in cui si desidera nel form, bloccarli tutti sul posto per evitare un movimento errato.

## <a name="to-lock-a-control"></a>Per bloccare un controllo

Nella finestra **Proprietà** di Visual Studio selezionare la proprietà **Locked** , quindi selezionare **true**. Facendo doppio clic sul nome, l'impostazione della proprietà viene attivata o disattivata.

In alternativa, fare clic con il pulsante destro del mouse sul controllo e scegliere **Blocca controlli**.

> [!NOTE]
> I controlli di blocco ne impediscono il trascinamento in una nuova dimensione o posizione nell'area di progettazione. Tuttavia, è comunque possibile modificare la dimensione o la posizione dei controlli per mezzo della finestra **Proprietà** o nel codice.

## <a name="to-lock-all-the-controls-on-a-form"></a>Per bloccare tutti i controlli in un form

Scegliere **Blocca controlli**dal menu **formato** .

> [!NOTE]
> Questo comando blocca anche le dimensioni del form, perché un modulo è un controllo.

## <a name="to-unlock-all-locked-controls-on-a-form"></a>Per sbloccare tutti i controlli bloccati in un form

Scegliere **Blocca controlli**dal menu **formato** .

Tutti i controlli bloccati in precedenza nel modulo sono ora sbloccati.

## <a name="to-unlock-locked-controls-individually"></a>Per sbloccare singolarmente i controlli bloccati

Nella finestra **Proprietà** selezionare la proprietà **Locked** , quindi selezionare **false**. Facendo doppio clic sul nome, l'impostazione della proprietà viene attivata o disattivata.

## <a name="see-also"></a>Vedere anche

- [Controlli Windows Form](index.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da utilizzare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
