---
title: 'Procedura dettagliata: serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 297a7080b0c34fa10f976cbbbfb48d8c35786aca
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458088"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a>Procedura dettagliata: serializzare raccolte di tipi standard

I controlli personalizzati a volte espongono una raccolta come proprietà. In questa procedura dettagliata viene illustrato come utilizzare la classe <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> per controllare la modalità di serializzazione di una raccolta in fase di progettazione. L'applicazione del valore <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> alla proprietà della raccolta garantisce che la proprietà verrà serializzata.

Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: serializzare raccolte di tipi standard con DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).

## <a name="prerequisites"></a>Prerequisites

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-a-control-with-a-serializable-collection"></a>Creare un controllo con una raccolta serializzabile

Il primo passaggio consiste nel creare un controllo con una raccolta serializzabile come proprietà. È possibile modificare il contenuto di questa raccolta usando l' **Editor della raccolta**, a cui è possibile accedere dalla finestra **Proprietà** .

1. In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **SerializationDemoControlLib**.

2. Rinominare `UserControl1` in `SerializationDemoControl`. Per altre informazioni, vedere [rinominare un simbolo di codice refactoring](/visualstudio/ide/reference/rename).

3. Nella finestra **Proprietà** impostare il valore della proprietà <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> su **10**.

4. Inserire un controllo <xref:System.Windows.Forms.TextBox> nel `SerializationDemoControl`.

5. Selezionare il controllo <xref:System.Windows.Forms.TextBox>. Nella finestra **Proprietà** impostare le proprietà seguenti.

    |proprietà|Modificare in|
    |--------------|---------------|
    |**Multiline**|`true`|
    |**Dock**|<xref:System.Windows.Forms.DockStyle.Fill>|
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |**ReadOnly**|`true`|

6. Nell' **editor di codice**dichiarare un campo di matrice di stringhe denominato `stringsValue` in `SerializationDemoControl`.

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. Definire la proprietà `Strings` nell'`SerializationDemoControl`.

   > [!NOTE]
   > Il valore <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> viene utilizzato per abilitare la serializzazione della raccolta.

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.

9. Trovare la proprietà **Strings** nel <xref:System.Windows.Forms.PropertyGrid> del **contenitore di test UserControl**. Selezionare la proprietà **Strings** , quindi fare clic sui puntini di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà di Visual Studio](./media/visual-studio-ellipsis-button.png)) per aprire l' **Editor della raccolta di stringhe**.

10. Immettere diverse stringhe nell' **Editor della raccolta di stringhe**. Separarli premendo il tasto **invio** alla fine di ogni stringa. Al termine dell'immissione delle stringhe, fare clic su **OK** .

   > [!NOTE]
   > Le stringhe digitate vengono visualizzate nel <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.

## <a name="serialize-a-collection-property"></a>Serializzare una proprietà di raccolta

Per testare il comportamento di serializzazione del controllo, è necessario inserirlo in un form e modificare il contenuto della raccolta con l' **Editor della raccolta**. È possibile visualizzare lo stato della raccolta serializzata esaminando un file speciale della finestra di progettazione in cui il **Progettazione Windows Form** genera il codice.

1. Aggiungere un progetto di applicazione Windows alla soluzione. Denominare il progetto `SerializationDemoControlTest`.

2. Nella **casella degli strumenti**individuare la scheda denominata **SerializationDemoControlLib Components**. In questa scheda sono disponibili le `SerializationDemoControl`. Per altre informazioni, vedere [Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

3. Inserire un `SerializationDemoControl` sul form.

4. Trovare la proprietà `Strings` nella finestra **Proprietà** . Fare clic sulla proprietà `Strings`, quindi fare clic sui puntini di sospensione (![pulsante con i puntini di sospensione (...) nel pulsante Finestra Proprietà di Visual Studio.](./media/visual-studio-ellipsis-button.png)) per aprire l' **Editor della raccolta di stringhe**.

5. Digitare diverse stringhe nell' **Editor della raccolta di stringhe**. Separarli premendo **invio** alla fine di ogni stringa. Al termine dell'immissione delle stringhe, fare clic su **OK** .

    > [!NOTE]
    > Le stringhe digitate vengono visualizzate nel <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.

6. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.

7. Aprire il nodo **Form1** . Sotto è presente un file denominato **Form1.designer.cs** o **Form1. designer. vb**. Si tratta del file in cui il **Progettazione Windows Form** emette codice che rappresenta lo stato della fase di progettazione del form e dei relativi controlli figlio. Aprire il file nell'**editor di codice**.

8. Aprire l'area denominata **codice generato da Progettazione Windows Form** e trovare la sezione denominata **serializationDemoControl1**. Sotto questa etichetta è riportato il codice che rappresenta lo stato serializzato del controllo. Le stringhe digitate nel passaggio 5 vengono visualizzate in un'assegnazione alla proprietà `Strings`. Gli esempi di codice seguenti C# in e Visual Basic, mostrano codice simile a quello che si noterà se le stringhe sono state digitate "Red", "Orange" e "Yellow".

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. Nell' **editor di codice**, modificare il valore della <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> sulla proprietà `Strings` in <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. Ricompilare la soluzione e ripetere i passaggi 3 e 4.

> [!NOTE]
> In questo caso, il **Progettazione Windows Form** non emette alcuna assegnazione alla proprietà `Strings`.

## <a name="next-steps"></a>Passaggi successivi

Quando si sa come serializzare una raccolta di tipi standard, è consigliabile integrare i controlli personalizzati in modo più approfondito nell'ambiente in fase di progettazione. Negli argomenti seguenti viene descritto come migliorare l'integrazione della fase di progettazione dei controlli personalizzati:

- [Architettura della fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))

- [Attributi nei controlli Windows Forms](attributes-in-windows-forms-controls.md)

- [Panoramica della serializzazione della finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))

- [Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
