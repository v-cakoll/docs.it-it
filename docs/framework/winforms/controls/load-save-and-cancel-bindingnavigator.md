---
title: Aggiungere i pulsanti carica, Salva e Annulla al controllo BindingNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 0305df5e7566f9441ce09fa3346a8b2dc67c8943
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77627968"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form

Il controllo <xref:System.Windows.Forms.BindingNavigator> è un controllo <xref:System.Windows.Forms.ToolStrip> per scopi specifici che deve essere utilizzato per spostarsi e modificare i controlli nel form associati ai dati.

Poiché si tratta di un controllo <xref:System.Windows.Forms.ToolStrip>, il componente <xref:System.Windows.Forms.BindingNavigator> può essere modificato facilmente per includere comandi aggiuntivi o alternativi per l'utente.

Nella procedura seguente, un controllo <xref:System.Windows.Forms.TextBox> viene associato ai dati e il controllo <xref:System.Windows.Forms.ToolStrip> aggiunto al modulo viene modificato in modo da includere i pulsanti carica, Salva e Annulla.

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Aggiungere i pulsanti carica, Salva e Annulla al componente BindingNavigator

1. In Visual Studio aggiungere un controllo <xref:System.Windows.Forms.TextBox> al modulo.

2. Associarlo a un <xref:System.Windows.Forms.BindingSource>, associato a un'origine dati. Per questo esempio, il <xref:System.Windows.Forms.BindingSource> è associato a un database.

3. Dopo aver generato il set di dati e l'adattatore tabella, trascinare un controllo <xref:System.Windows.Forms.BindingNavigator> nel form.

4. Impostare la proprietà <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> del controllo <xref:System.Windows.Forms.BindingNavigator> sul <xref:System.Windows.Forms.BindingSource> nel form associato ai controlli.

5. Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.

6. Fare clic sul glifo azioni della finestra di progettazione (![piccola freccia nera](./media/designer-actions-glyph.gif)) per visualizzare la finestra di dialogo **attività di BindingNavigator** e selezionare **modifica elementi**.

     Viene visualizzato l' **Editor della raccolta Items** .

7. Nell' **Editor della raccolta Items**completare le operazioni seguenti:

    1. Aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> e tre elementi <xref:System.Windows.Forms.ToolStripButton> selezionando il tipo di <xref:System.Windows.Forms.ToolStripItem> appropriato e facendo clic sul pulsante **Aggiungi** .

    2. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Name%2A> dei pulsanti rispettivamente su **LoadButton**, **pulsanteSalva**e **CancelButton**.

    3. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> dei pulsanti su **carica**, **Salva**e **Annulla**.

    4. Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> per ognuno dei pulsanti su **testo**. In alternativa, è possibile impostare questa proprietà su **Image** o **ImageAndText**e impostare l'immagine da visualizzare nella proprietà <xref:System.Windows.Forms.ToolStripItem.Image%2A>.

    5. Fare clic su **OK** per chiudere la finestra di dialogo. I pulsanti vengono aggiunti all'<xref:System.Windows.Forms.ToolStrip>.

8. Fare clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice**.

9. Nell'editor di codice trovare la riga di codice che carica i dati nell'adattatore della tabella. Questo codice è stato generato quando si configura il data binding nel passaggio 2. Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)`. Probabilmente si troverà nell'evento <xref:System.Windows.Forms.Form.Load> del modulo.

10. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> del **carico** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e spostarvi il codice di caricamento dei dati.

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

11. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> del **salvataggio**<xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per aggiornare i dati all'interno della tabella a cui è associato il controllo.

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
    > In alcuni casi, il componente <xref:System.Windows.Forms.BindingNavigator> dispone già di un pulsante **Salva** , ma non è stato generato alcun codice dall'progettazione Windows Form. In questo caso, è possibile inserire il codice precedente nel gestore eventi <xref:System.Windows.Forms.ToolStripItem.Click> per tale pulsante, anziché creare un pulsante completamente nuovo nel <xref:System.Windows.Forms.ToolStrip>. Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario impostare la proprietà <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> del pulsante su `true` per fare in modo che il pulsante funzioni correttamente.

12. Creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> dell'<xref:System.Windows.Forms.ToolStripButton> **Annulla** creato in precedenza e scrivere codice per annullare le modifiche apportate al record di dati visualizzato.

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
    > Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo è limitato alla riga di dati. Salvare le modifiche apportate durante la visualizzazione del singolo record prima di passare al record successivo.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Cenni preliminari sul componente BindingSource](bindingsource-component-overview.md)
