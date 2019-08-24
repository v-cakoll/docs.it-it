---
title: 'Procedura: Creare un controllo con associazione semplice in un Windows Form'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: df87f00e6e03de67c3fb1adc28472c96f4a47ef4
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015625"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a>Procedura: Creare un controllo con associazione semplice in un Windows Form

Con l' *associazione semplice*, è possibile visualizzare un singolo elemento dati, ad esempio un valore di colonna da una tabella del set di dati, in un controllo. È possibile associare in modo semplice qualsiasi proprietà di un controllo a un valore di dati.

## <a name="to-simple-bind-a-control"></a>Per eseguire l'associazione semplice di un controllo

1. Effettuare una connessione a un'origine dati. Per ulteriori informazioni, vedere [connessione a un'origine dati](../data/adonet/connecting-to-a-data-source.md).

2. In Visual Studio selezionare il controllo nel form e visualizzare la finestra **Proprietà** .

3. Espandere la proprietà **(DataBindings)** .

     Le proprietà associate più spesso vengono visualizzate sotto la proprietà **(DataBindings)** . Nella maggior parte dei controlli, ad esempio, la proprietà **Text** viene associata con maggiore frequenza.

4. Se la proprietà che si desidera associare non è una delle proprietà comunemente associate, fare clic sul pulsante con i![puntini di sospensione (...) nella finestra proprietà di Visual Studio.](./media/how-to-create-a-simple-bound-control-on-a-windows-form/visual-studio-ellipsis-button.png)) nella casella **(avanzate)** per visualizzare il  **Finestra di dialogo formattazione e associazione avanzata** con un elenco completo delle proprietà per il controllo.

5. Selezionare la proprietà che si desidera associare, quindi fare clic sulla freccia a discesa sotto **Binding**.

     Verrà visualizzato un elenco di origini dati disponibili.

6. Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati. Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.

7. Fare clic sul nome dell'elemento a cui effettuare il binding.

8. Se si utilizza la finestra di dialogo **formattazione e binding avanzato** , fare clic su **OK** per tornare alla finestra **proprietà** .

9. Se si desidera associare proprietà aggiuntive del controllo, ripetere i passaggi da 3 a 7.

    > [!NOTE]
    > Poiché i controlli con associazione semplice mostrano solo un singolo elemento dati, è molto normale includere la logica di navigazione in un Windows Form con controlli ad associazione semplice.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Binding>
- [Data binding in Windows Form](windows-forms-data-binding.md)
- [Data binding e Windows Forms](data-binding-and-windows-forms.md)
