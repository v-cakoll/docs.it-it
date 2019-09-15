---
title: 'Procedura: Aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 2d4867c0bc4feb7b43e15614fc56a3c709cef9e7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991743"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Procedura: Aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Forms

Il <xref:System.Windows.Forms.BindingNavigator> controllo è un controllo per scopi <xref:System.Windows.Forms.ToolStrip> specifici che consente di spostarsi e modificare i controlli nel form associati ai dati.

Poiché si tratta di <xref:System.Windows.Forms.ToolStrip> un controllo, <xref:System.Windows.Forms.BindingNavigator> è possibile modificare facilmente il componente per includere comandi aggiuntivi o alternativi per l'utente.

Nella procedura seguente viene associato un <xref:System.Windows.Forms.TextBox> controllo ai dati e il controllo aggiunto al <xref:System.Windows.Forms.ToolStrip> form viene modificato per includere i pulsanti Load, Save e Cancel.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Aggiungere i pulsanti carica, Salva e Annulla al componente BindingNavigator

1. In Visual Studio aggiungere un <xref:System.Windows.Forms.TextBox> controllo al form.

2. Associarlo a un <xref:System.Windows.Forms.BindingSource>oggetto, che è associato a un'origine dati. Per questo esempio, l' <xref:System.Windows.Forms.BindingSource> oggetto è associato a un database.

3. Dopo aver generato il set di dati e l'adattatore tabella <xref:System.Windows.Forms.BindingNavigator> , trascinare un controllo nel form.

4. Impostare la <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> proprietà<xref:System.Windows.Forms.BindingSource> del controllo su sul form associato ai controlli.

5. Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.

6. Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in modo che venga visualizzata la finestra di dialogo **attività di BindingNavigator** e selezionare **modifica elementi**.

     Viene visualizzato l' **Editor della raccolta Items** .

7. Nell' **Editor della raccolta Items**completare le operazioni seguenti:

    1. Aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> e tre <xref:System.Windows.Forms.ToolStripButton> elementi selezionando il tipo appropriato di <xref:System.Windows.Forms.ToolStripItem> e facendo clic sul pulsante **Aggiungi** .

    2. Impostare la <xref:System.Windows.Forms.ToolStripItem.Name%2A> proprietà dei pulsanti rispettivamente su **LoadButton**, **pulsanteSalva**e **CancelButton**.

    3. Impostare la <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà dei pulsanti su **carica**, **Salva**e **Annulla**.

    4. Impostare la <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà per ognuno dei pulsanti su **testo**. In alternativa, è possibile impostare questa proprietà su **Image** o **ImageAndText**e impostare l'immagine da <xref:System.Windows.Forms.ToolStripItem.Image%2A> visualizzare nella proprietà.

    5. Fare clic su **OK** per chiudere la finestra di dialogo. I pulsanti vengono aggiunti a <xref:System.Windows.Forms.ToolStrip>.

8. Fare clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice**.

9. Nell'editor di codice trovare la riga di codice che carica i dati nell'adattatore della tabella. Questo codice è stato generato quando si configura il data binding nel passaggio 2. Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)`. Probabilmente si troverà nell' <xref:System.Windows.Forms.Form.Load> evento del modulo.

10. Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento del **carico** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e spostarvi il codice di caricamento dei dati.

     Il codice dovrebbe ora essere simile al seguente:

    ```vb
    Private Sub LoadButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles LoadButton.Click
        TableAdapterName.Fill(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void LoadButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Fill(DataSetName.TableName);
    }
    ```

11. Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento del **salvataggio** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per aggiornare i dati all'interno della tabella a cui è associato il controllo.

    ```vb
    Private Sub SaveButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles SaveButton.Click
        TableAdapterName.Update(DataSetName.TableName)
    End Sub
    ```

    ```csharp
    private void SaveButton_Click(System.Object sender,
        System.EventArgs e)
    {
        TableAdapterName.Update(DataSetName.TableName);
    }
    ```

    > [!NOTE]
    > In alcuni casi, il <xref:System.Windows.Forms.BindingNavigator> componente ha già un pulsante **Salva** , ma non è stato generato alcun codice dal progettazione Windows Form. In questo caso, è possibile inserire il codice precedente nel <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per tale pulsante, anziché creare un pulsante completamente nuovo <xref:System.Windows.Forms.ToolStrip>in. Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> impostare la proprietà del pulsante `true` su per fare in modo che il pulsante funzioni correttamente.

12. Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento dell' **annullamento** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per annullare tutte le modifiche apportate al record di dati visualizzato.

    ```vb
    Private Sub CancelButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles CancelButton.Click
        BindingSourceName.CancelEdit()
    End Sub
    ```

    ```csharp
    private void CancelButton_Click(System.Object sender, System.EventArgs e)
    {
        BindingSourceName.CancelEdit();
    }
    ```

    > [!NOTE]
    > Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo ha come ambito la riga di dati. Salvare le modifiche apportate durante la visualizzazione del singolo record prima di passare al record successivo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Cenni preliminari sul componente BindingSource](bindingsource-component-overview.md)
