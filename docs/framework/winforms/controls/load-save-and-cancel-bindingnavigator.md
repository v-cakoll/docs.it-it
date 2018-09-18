---
title: 'Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: 97be77b6591e4b7fa3db8176222dcb1feb3481bc
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45972689"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form
Il <xref:System.Windows.Forms.BindingNavigator> controllo è una speciale <xref:System.Windows.Forms.ToolStrip> controllo specifico per la navigazione e modifica dei controlli sul form che vengono associati ai dati.  
  
 Perché è un <xref:System.Windows.Forms.ToolStrip> (controllo), il <xref:System.Windows.Forms.BindingNavigator> componente può essere facilmente modificato per includere comandi aggiuntivi o alternativi dell'utente.  
  
 Nella procedura seguente, un <xref:System.Windows.Forms.TextBox> è associato a dati e il <xref:System.Windows.Forms.ToolStrip> controllo che viene aggiunto al form viene modificato per includere caricamento, salvataggio e i pulsanti Annulla.  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Per aggiungere carica, Salva e Annulla i pulsanti per il componente di BindingNavigator  
  
1.  Aggiungere un oggetto <xref:System.Windows.Forms.TextBox> al form.  
  
2.  Associarlo a un <xref:System.Windows.Forms.BindingSource>, che è associato a un'origine dati. In questo esempio il <xref:System.Windows.Forms.BindingSource> è associato a un database.  
  
3.  Una volta generato il set di dati e tabella la scheda, trascinare un <xref:System.Windows.Forms.BindingNavigator> controllo al form.  
  
4.  Impostare il <xref:System.Windows.Forms.BindingNavigator> del controllo <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> proprietà di <xref:System.Windows.Forms.BindingSource> nel form di cui è associato ai controlli.  
  
5.  Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.  
  
6.  Fare clic sul glifo dello smart tag (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in modo che il **le attività di BindingNavigator** finestra di dialogo e selezionare **Modifica elementi**.  
  
     Il **Editor della raccolta Items** viene visualizzata.  
  
7.  Nel **Editor della raccolta Items**, completare le operazioni seguenti:  
  
    1.  Aggiungi un <xref:System.Windows.Forms.ToolStripSeparator> e tre <xref:System.Windows.Forms.ToolStripButton> selezionando il tipo appropriato di elementi <xref:System.Windows.Forms.ToolStripItem> e facendo clic sui **Add** pulsante.  
  
    2.  Impostare il <xref:System.Windows.Forms.ToolStripItem.Name%2A> proprietà dei pulsanti per **LoadButton**, **PulsanteSalva**, e **CancelButton**, rispettivamente.  
  
    3.  Impostare il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà dei pulsanti per **Load**, **salvare**, e **Annulla**.  
  
    4.  Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà per ognuno dei pulsanti per **testo**. In alternativa, è possibile impostare questa proprietà **immagine** oppure **ImageAndText**e impostare l'immagine da visualizzare nel <xref:System.Windows.Forms.ToolStripItem.Image%2A> proprietà.  
  
    5.  Fare clic su **OK** per chiudere la finestra di dialogo. Vengono aggiunti i pulsanti per il <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Fare clic sulla forma e scegliere **Visualizza codice**.  
  
9. Nell'Editor di codice, trovare la riga di codice che carica i dati nell'adattatore di tabella. Questo codice è stato generato quando si configura il data binding nel passaggio 2. Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)`. Si verifica più probabilmente avere il formato <xref:System.Windows.Forms.Form.Load> evento.  
  
10. Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> eventi del **Load** <xref:System.Windows.Forms.ToolStripButton> è creato in precedenza e spostare il codice di caricamento dei dati al suo interno.  
  
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
  
11. Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> eventi del **salvare** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere il codice per aggiornare i dati all'interno della tabella del controllo associato a.  
  
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
    > In alcuni casi, il <xref:System.Windows.Forms.BindingNavigator> componente avrà già una **salvare** pulsante, ma nessun codice verrà sono stati generati da Progettazione Windows Form. In questo caso, è possibile inserire il codice precedente nel <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per tale pulsante, anziché creare un pulsante completamente nuovo nel <xref:System.Windows.Forms.ToolStrip>. Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario impostare il <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> proprietà del pulsante su `true` affinché funzioni correttamente.
  
12. Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> eventi del **annullare** <xref:System.Windows.Forms.ToolStripButton> è creato in precedenza e scrivere codice per annullare le modifiche al record di dati che viene visualizzato.  
  
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
    >  Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo ha come ambito la riga di dati. Salvare le modifiche apportate durante la visualizzazione dei singoli record prima di passare al record successivo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [Controllo BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Cenni preliminari sul componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
