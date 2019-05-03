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
ms.openlocfilehash: c113dcf814a252808ae3232751028947c26821ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012438"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a>Procedura dettagliata: Serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute

I controlli personalizzati a volte esporrà una raccolta come una proprietà. Questa procedura dettagliata illustra come usare il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> classe per controllare la serializzazione di una raccolta in fase di progettazione. Applicando la <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore alla proprietà della raccolta assicura che la proprietà sarà serializzata.

 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Serializzare raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).

> [!NOTE]
> Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

## <a name="prerequisites"></a>Prerequisiti
 Per completare questa procedura dettagliata, è necessario:

- Autorizzazioni sufficienti per essere in grado di creare ed eseguire progetti di applicazione Windows Form nel computer in cui è installato Visual Studio.

## <a name="creating-a-control-that-has-a-serializable-collection"></a>Creazione di un controllo dispone di una raccolta serializzabile
 Il primo passaggio consiste nel creare un controllo dotato di una raccolta serializzabile come una proprietà. È possibile modificare il contenuto di questa raccolta usando il **Editor della raccolta**, che è possibile accedere dalle **proprietà** finestra.

### <a name="to-create-a-control-with-a-serializable-collection"></a>Per creare un controllo con una raccolta serializzabile

1. Creare un progetto libreria di controlli di Windows denominato `SerializationDemoControlLib`. Per altre informazioni, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).

2. Rinominare `UserControl1` a `SerializationDemoControl`. Per altre informazioni, vedere [rinominare un simbolo di codice e refactoring](/visualstudio/ide/reference/rename).

3. Nel **delle proprietà** finestra, impostare il valore della <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> proprietà `10`.

4. Sul posto un <xref:System.Windows.Forms.TextBox> controllare il `SerializationDemoControl`.

5. Selezionare il controllo <xref:System.Windows.Forms.TextBox>. Nel **proprietà** finestra, impostare le proprietà seguenti.

    |Proprietà|Modificare in|
    |--------------|---------------|
    |**Multiline**|`true`|
    |**Dock**|<xref:System.Windows.Forms.DockStyle.Fill>|
    |**ScrollBars**|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |**ReadOnly**|`true`|

6. Nel **Editor di codice**, dichiarare un campo di matrice di stringhe denominato `stringsValue` in `SerializationDemoControl`.

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. Definire le `Strings` proprietà di `SerializationDemoControl`.

> [!NOTE]
> Il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> valore viene usato per abilitare la serializzazione della raccolta.

 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

1. Per compilare il progetto ed eseguire il controllo in **UserControl Test Container**, premere F5.

2. Trovare il `Strings` proprietà nel <xref:System.Windows.Forms.PropertyGrid> delle **UserControl Test Container**. Fare clic sui `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Editor della raccolta String**.

3. Immettere più stringhe nel **Editor della raccolta String**. È necessario separarli premendo il tasto INVIO alla fine di ogni stringa. Fare clic su **OK** dopo aver immesso le stringhe.

> [!NOTE]
> Vengono visualizzate le stringhe immesse nella <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.

## <a name="serializing-a-collection-property"></a>La serializzazione di una proprietà di raccolta

Per testare il comportamento di serializzazione del controllo, si verrà posizionarlo in un form e modificare il contenuto della raccolta con il **Editor della raccolta**. È possibile visualizzare lo stato della raccolta serializzata esaminando un file di progettazione speciale, in cui il **finestra di progettazione Windows Form** emette il codice.

### <a name="to-serialize-a-collection"></a>Per serializzare una raccolta

1. Aggiungere un progetto di applicazione di Windows per la soluzione. Denominare il progetto `SerializationDemoControlTest`.

2. Nel **casella degli strumenti**, individuare la scheda denominata **Componenti SerializationDemoControlLib**. In questa scheda, si noterà il `SerializationDemoControl`. Per altre informazioni, vedere [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).

3. Sul posto un `SerializationDemoControl` sul form.

4. Trovare il `Strings` proprietà il **proprietà** finestra. Fare clic sui `Strings` proprietà, quindi fare clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) per aprire la **Editor della raccolta String**.

5. Digitare più stringhe nel **Editor della raccolta String**. È necessario separarli premendo il tasto INVIO alla fine di ogni stringa. Fare clic su **OK** dopo aver immesso le stringhe.

> [!NOTE]
> Vengono visualizzate le stringhe immesse nella <xref:System.Windows.Forms.TextBox> del `SerializationDemoControl`.

1. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.

2. Aprire il **Form1** nodo. In cui è presente un file denominato **Form1.Designer.cs** oppure **Form1**. Si tratta del file in cui il **finestra di progettazione Windows Form** genera codice che rappresenta lo stato della fase di progettazione del form e i relativi controlli figlio. Aprire il file nell'**editor di codice**.

3. Aprire l'area denominata **codice generato da Progettazione Form di Windows** e individuare la sezione **serializationDemoControl1**. Di sotto di questa etichetta è il codice che rappresenta lo stato serializzato del controllo. Le stringhe digitato nel passaggio 5 vengono visualizzate in un'assegnazione al `Strings` proprietà. Gli esempi di codice seguente in c# e Visual Basic, visualizzare codice simile a ciò che viene visualizzato se digitato le stringhe "rosso", "arancione" e "giallo".

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. Nel **Editor di codice**, modificare il valore della <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> sul `Strings` proprietà <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. Ricompilare la soluzione e ripetere i passaggi 3 e 4.

> [!NOTE]
> In questo caso, il **finestra di progettazione Windows Form** alcuna assegnazione genera la `Strings` proprietà.

## <a name="next-steps"></a>Passaggi successivi

Dopo che in grado di serializzare una raccolta di tipi standard, è consigliabile integrare un livello più profondo i controlli personalizzati nell'ambiente della fase di progettazione. Gli argomenti seguenti descrivono come migliorare l'integrazione in fase di progettazione di controlli personalizzati:

- [Architettura della fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))

- [Attributi nei controlli Windows Forms](attributes-in-windows-forms-controls.md)

- [Cenni preliminari sulla serializzazione della finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))

- [Procedura dettagliata: Creazione di un controllo di Windows Form che consente di sfruttare le funzionalità in fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [Cenni preliminari sulla serializzazione della finestra di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))
- [Procedura: Serializzare raccolte di tipi Standard tramite DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))
- [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
