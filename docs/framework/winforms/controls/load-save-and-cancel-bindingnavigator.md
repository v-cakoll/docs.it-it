---
title: 'Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dd45b33fb1f99c280e126b9e601692a85da5dba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a>Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form
Il <xref:System.Windows.Forms.BindingNavigator> controllo è una speciale <xref:System.Windows.Forms.ToolStrip> controllo destinato per lo spostamento e modifica dei controlli sul form che sono associati a dati.  
  
 Perché è un <xref:System.Windows.Forms.ToolStrip> (controllo), il <xref:System.Windows.Forms.BindingNavigator> componente può essere modificato facilmente per includere comandi aggiuntivi o alternativi per l'utente.  
  
 Nella procedura seguente, un <xref:System.Windows.Forms.TextBox> è associato a dati e <xref:System.Windows.Forms.ToolStrip> controllo aggiunto al form viene modificato per includere carica, Salva e Annulla.  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a>Per aggiungere carica, Salva e Annulla pulsanti per il componente di BindingNavigator  
  
1.  Aggiungere un oggetto <xref:System.Windows.Forms.TextBox> al form.  
  
2.  Associarlo a un <xref:System.Windows.Forms.BindingSource>, che è associato a un'origine dati. Per questo esempio, il <xref:System.Windows.Forms.BindingSource> è associato a un database.  
  
3.  Dopo avere generato il set di dati e il TableAdapter, trascinare un <xref:System.Windows.Forms.BindingNavigator> al form.  
  
4.  Impostare il <xref:System.Windows.Forms.BindingNavigator> del controllo <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> proprietà per il <xref:System.Windows.Forms.BindingSource> sul form che è associato ai controlli.  
  
5.  Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.  
  
6.  Fare clic sul glifo smart tag (![Smart Tag glifo](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) pertanto **attività BindingNavigator** finestra di dialogo e selezionare **Modifica elementi**.  
  
     Il **Editor della raccolta Items** viene visualizzato.  
  
7.  Nel **Editor della raccolta Items**, completare le operazioni seguenti:  
  
    1.  Aggiungi un <xref:System.Windows.Forms.ToolStripSeparator> e tre <xref:System.Windows.Forms.ToolStripButton> elementi selezionando il tipo appropriato di <xref:System.Windows.Forms.ToolStripItem> e scegliendo il **Aggiungi** pulsante.  
  
    2.  Impostare il <xref:System.Windows.Forms.ToolStripItem.Name%2A> proprietà dei pulsanti per**LoadButton**,**PulsanteSalva**, e**CancelButton**, rispettivamente.  
  
    3.  Impostare il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà dei pulsanti per**carico** `,` **salvare**, e**Annulla**.  
  
    4.  Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà per ognuno dei pulsanti per**testo**. In alternativa, è possibile impostare questa proprietà**immagine**o**ImageAndText**e impostare l'immagine da visualizzare nella <xref:System.Windows.Forms.ToolStripItem.Image%2A> proprietà.  
  
    5.  Fare clic su **OK** per chiudere la finestra di dialogo. Vengono aggiunti i pulsanti di <xref:System.Windows.Forms.ToolStrip>.  
  
8.  Il modulo di mouse e scegliere **Visualizza codice**.  
  
9. Nell'Editor di codice, individuare la riga di codice che carica i dati nell'adattatore di tabella. Questo codice è stato generato quando si configura l'associazione di dati nel passaggio 2. Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)`. Si verifica più probabilmente avere il formato <xref:System.Windows.Forms.Form.Load> evento.  
  
10. Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento del**carico** <xref:System.Windows.Forms.ToolStripButton> è creato in precedenza e spostare il codice di caricamento dei dati al suo interno.  
  
     Il codice dovrebbe risultare simile al seguente:  
  
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
  
11. Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento del **salvare** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere il codice per aggiornare i dati all'interno della tabella di controllo è associato a.  
  
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
    >  In alcuni casi, il <xref:System.Windows.Forms.BindingNavigator> componente avranno già un**salvare** pulsante ma nessun codice verrà sono stati generati da Progettazione Windows Form. In questo caso, è possibile inserire il codice precedente il <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per tale pulsante, anziché creare un pulsante completamente nuovo nel <xref:System.Windows.Forms.ToolStrip>. Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario impostare il <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> proprietà del pulsante su `true` affinché funzioni correttamente.  
  
12. Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> evento del**Annulla** <xref:System.Windows.Forms.ToolStripButton> è creato in precedenza e scrivere codice per annullare le modifiche al record di dati che viene visualizzato.  
  
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
    >  Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo ambito è la riga di dati. Salvare le modifiche apportate durante la visualizzazione del singolo record prima di spostarsi al record successivo.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [Controllo BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Cenni preliminari sul componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
