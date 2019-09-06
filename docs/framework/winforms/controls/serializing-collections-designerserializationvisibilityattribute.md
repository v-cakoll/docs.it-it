---
title: 'Procedura dettagliata: Serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute'
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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4fd1f1dc0c2c0ad9ae2009ed592e48b8eeaa2783
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373679"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a>Procedura dettagliata: Serializzare raccolte di tipi standard

I controlli personalizzati a volte espongono una raccolta come proprietà. In questa procedura dettagliata viene illustrato come <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> utilizzare la classe per controllare la modalità di serializzazione di una raccolta in fase di progettazione. L'applicazione <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> del valore alla proprietà della raccolta garantisce che la proprietà verrà serializzata.

Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Serializzare raccolte di tipi standard con DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-a-control-with-a-serializable-collection"></a>Creare un controllo con una raccolta serializzabile

Il primo passaggio consiste nel creare un controllo con una raccolta serializzabile come proprietà. È possibile modificare il contenuto di questa raccolta usando l' **Editor della raccolta**, a cui è possibile accedere dalla finestra **Proprietà** .

1. In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **SerializationDemoControlLib**.

2. Rinominare `UserControl1` in `SerializationDemoControl`. Per altre informazioni, vedere [rinominare un simbolo di codice refactoring](/visualstudio/ide/reference/rename).

3. Nella finestra **Proprietà** impostare il valore della <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> proprietà su **10**.

4. Inserire un <xref:System.Windows.Forms.TextBox> controllo `SerializationDemoControl`in.

5. Selezionare il controllo <xref:System.Windows.Forms.TextBox>. Nella finestra **Proprietà** impostare le proprietà seguenti.

    |Proprietà|Modificare in|
    |--------------|---------------|
    |**Multiline**|`true`|
    |**Dock**|<xref:System.Windows.Forms.DockStyle.Fill>|
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |**ReadOnly**|`true`|

6. Nell' **editor di codice**dichiarare un campo di matrice di stringhe `stringsValue` denominato `SerializationDemoControl`in.

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. Definire la `Strings` proprietà nell'oggetto `SerializationDemoControl`.

   > [!NOTE]
   > Il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore viene utilizzato per abilitare la serializzazione della raccolta.

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. Premere **F5** per compilare il progetto ed eseguire il controllo in **UserControl Test Container**.

9. Trovare la proprietà **Strings** in <xref:System.Windows.Forms.PropertyGrid> del **contenitore di test UserControl**. Selezionare la proprietà **Strings** , quindi fare clic sui![puntini di sospensione (il pulsante con i puntini di sospensione (](./media/visual-studio-ellipsis-button.png)...) nel pulsante finestra proprietà di Visual Studio) per aprire l' **Editor della raccolta di stringhe**.

10. Immettere diverse stringhe nell' **Editor della raccolta di stringhe**. Separarli premendo il tasto **invio** alla fine di ogni stringa. Al termine dell'immissione delle stringhe, fare clic su **OK** .

   > [!NOTE]
   > Le stringhe digitate vengono visualizzate <xref:System.Windows.Forms.TextBox> nella `SerializationDemoControl`di.

## <a name="serialize-a-collection-property"></a>Serializzare una proprietà di raccolta

Per testare il comportamento di serializzazione del controllo, è necessario inserirlo in un form e modificare il contenuto della raccolta con l' **Editor della raccolta**. È possibile visualizzare lo stato della raccolta serializzata esaminando un file speciale della finestra di progettazione in cui il **Progettazione Windows Form** genera il codice.

1. Aggiungere un progetto di applicazione Windows alla soluzione. Denominare il progetto `SerializationDemoControlTest`.

2. Nella **casella degli strumenti**individuare la scheda denominata **SerializationDemoControlLib Components**. In questa scheda si troverà `SerializationDemoControl`. Per altre informazioni, vedere [Procedura dettagliata: Popolamento automatico della casella degli strumenti con](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)componenti personalizzati.

3. Inserire un `SerializationDemoControl` nel form.

4. Trovare la `Strings` proprietà nella finestra **proprietà** . Fare clic `Strings` sulla proprietà, quindi fare clic sul![pulsante con i puntini di sospensione (...) nel pulsante finestra proprietà](./media/visual-studio-ellipsis-button.png)di Visual Studio.) per aprire l' **Editor della raccolta di stringhe**.

5. Digitare diverse stringhe nell' **Editor della raccolta di stringhe**. Separarli premendo **invio** alla fine di ogni stringa. Al termine dell'immissione delle stringhe, fare clic su **OK** .

    > [!NOTE]
    > Le stringhe digitate vengono visualizzate <xref:System.Windows.Forms.TextBox> nella `SerializationDemoControl`di.

6. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.

7. Aprire il nodo **Form1** . Sotto è presente un file denominato **Form1.designer.cs** o **Form1. designer. vb**. Si tratta del file in cui il **Progettazione Windows Form** emette codice che rappresenta lo stato della fase di progettazione del form e dei relativi controlli figlio. Aprire il file nell'**editor di codice**.

8. Aprire l'area denominata **codice generato da Progettazione Windows Form** e trovare la sezione denominata **serializationDemoControl1**. Sotto questa etichetta è riportato il codice che rappresenta lo stato serializzato del controllo. Le stringhe digitate nel passaggio 5 vengono visualizzate in un'assegnazione `Strings` alla proprietà. Gli esempi di codice seguenti C# in e Visual Basic, mostrano codice simile a quello che si noterà se le stringhe sono state digitate "Red", "Orange" e "Yellow".

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. Nell'Editor di **codice**, modificare il valore <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> della `Strings` proprietà <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>in.

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. Ricompilare la soluzione e ripetere i passaggi 3 e 4.

> [!NOTE]
> In questo caso, il **Progettazione Windows Form** non emette alcuna assegnazione alla `Strings` proprietà.

## <a name="next-steps"></a>Passaggi successivi

Quando si sa come serializzare una raccolta di tipi standard, è consigliabile integrare i controlli personalizzati in modo più approfondito nell'ambiente in fase di progettazione. Negli argomenti seguenti viene descritto come migliorare l'integrazione della fase di progettazione dei controlli personalizzati:

- [Architettura della fase di progettazione](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))

- [Attributi nei controlli Windows Forms](attributes-in-windows-forms-controls.md)

- [Panoramica della serializzazione della finestra di progettazione](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))

- [Procedura dettagliata: Creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [Procedura dettagliata: Popolamento automatico della casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
