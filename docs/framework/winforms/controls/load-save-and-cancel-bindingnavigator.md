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
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="a444a-102">Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form</span><span class="sxs-lookup"><span data-stu-id="a444a-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="a444a-103">Il controllo <xref:System.Windows.Forms.BindingNavigator> è un controllo <xref:System.Windows.Forms.ToolStrip> per scopi specifici che deve essere utilizzato per spostarsi e modificare i controlli nel form associati ai dati.</span><span class="sxs-lookup"><span data-stu-id="a444a-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="a444a-104">Poiché si tratta di un controllo <xref:System.Windows.Forms.ToolStrip>, il componente <xref:System.Windows.Forms.BindingNavigator> può essere modificato facilmente per includere comandi aggiuntivi o alternativi per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a444a-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="a444a-105">Nella procedura seguente, un controllo <xref:System.Windows.Forms.TextBox> viene associato ai dati e il controllo <xref:System.Windows.Forms.ToolStrip> aggiunto al modulo viene modificato in modo da includere i pulsanti carica, Salva e Annulla.</span><span class="sxs-lookup"><span data-stu-id="a444a-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="a444a-106">Aggiungere i pulsanti carica, Salva e Annulla al componente BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="a444a-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="a444a-107">In Visual Studio aggiungere un controllo <xref:System.Windows.Forms.TextBox> al modulo.</span><span class="sxs-lookup"><span data-stu-id="a444a-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="a444a-108">Associarlo a un <xref:System.Windows.Forms.BindingSource>, associato a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a444a-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="a444a-109">Per questo esempio, il <xref:System.Windows.Forms.BindingSource> è associato a un database.</span><span class="sxs-lookup"><span data-stu-id="a444a-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="a444a-110">Dopo aver generato il set di dati e l'adattatore tabella, trascinare un controllo <xref:System.Windows.Forms.BindingNavigator> nel form.</span><span class="sxs-lookup"><span data-stu-id="a444a-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="a444a-111">Impostare la proprietà <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> del controllo <xref:System.Windows.Forms.BindingNavigator> sul <xref:System.Windows.Forms.BindingSource> nel form associato ai controlli.</span><span class="sxs-lookup"><span data-stu-id="a444a-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="a444a-112">Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="a444a-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="a444a-113">Fare clic sul glifo azioni della finestra di progettazione (![piccola freccia nera](./media/designer-actions-glyph.gif)) per visualizzare la finestra di dialogo **attività di BindingNavigator** e selezionare **modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="a444a-113">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="a444a-114">Viene visualizzato l' **Editor della raccolta Items** .</span><span class="sxs-lookup"><span data-stu-id="a444a-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="a444a-115">Nell' **Editor della raccolta Items**completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a444a-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="a444a-116">Aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> e tre elementi <xref:System.Windows.Forms.ToolStripButton> selezionando il tipo di <xref:System.Windows.Forms.ToolStripItem> appropriato e facendo clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="a444a-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="a444a-117">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Name%2A> dei pulsanti rispettivamente su **LoadButton**, **pulsanteSalva**e **CancelButton**.</span><span class="sxs-lookup"><span data-stu-id="a444a-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="a444a-118">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.Text%2A> dei pulsanti su **carica**, **Salva**e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="a444a-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="a444a-119">Impostare la proprietà <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> per ognuno dei pulsanti su **testo**.</span><span class="sxs-lookup"><span data-stu-id="a444a-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="a444a-120">In alternativa, è possibile impostare questa proprietà su **Image** o **ImageAndText**e impostare l'immagine da visualizzare nella proprietà <xref:System.Windows.Forms.ToolStripItem.Image%2A>.</span><span class="sxs-lookup"><span data-stu-id="a444a-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="a444a-121">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="a444a-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="a444a-122">I pulsanti vengono aggiunti all'<xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="a444a-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="a444a-123">Fare clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="a444a-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="a444a-124">Nell'editor di codice trovare la riga di codice che carica i dati nell'adattatore della tabella.</span><span class="sxs-lookup"><span data-stu-id="a444a-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="a444a-125">Questo codice è stato generato quando si configura il data binding nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="a444a-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="a444a-126">Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="a444a-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="a444a-127">Probabilmente si troverà nell'evento <xref:System.Windows.Forms.Form.Load> del modulo.</span><span class="sxs-lookup"><span data-stu-id="a444a-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="a444a-128">Creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> del **carico** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e spostarvi il codice di caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="a444a-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="a444a-129">Il codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="a444a-129">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="a444a-130">Creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> del **salvataggio**<xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per aggiornare i dati all'interno della tabella a cui è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="a444a-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="a444a-131">In alcuni casi, il componente <xref:System.Windows.Forms.BindingNavigator> dispone già di un pulsante **Salva** , ma non è stato generato alcun codice dall'progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="a444a-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="a444a-132">In questo caso, è possibile inserire il codice precedente nel gestore eventi <xref:System.Windows.Forms.ToolStripItem.Click> per tale pulsante, anziché creare un pulsante completamente nuovo nel <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="a444a-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="a444a-133">Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario impostare la proprietà <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> del pulsante su `true` per fare in modo che il pulsante funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="a444a-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="a444a-134">Creare un gestore eventi per l'evento <xref:System.Windows.Forms.ToolStripItem.Click> dell'<xref:System.Windows.Forms.ToolStripButton> **Annulla** creato in precedenza e scrivere codice per annullare le modifiche apportate al record di dati visualizzato.</span><span class="sxs-lookup"><span data-stu-id="a444a-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="a444a-135">Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo è limitato alla riga di dati.</span><span class="sxs-lookup"><span data-stu-id="a444a-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="a444a-136">Salvare le modifiche apportate durante la visualizzazione del singolo record prima di passare al record successivo.</span><span class="sxs-lookup"><span data-stu-id="a444a-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="a444a-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a444a-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="a444a-138">Controllo BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="a444a-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="a444a-139">Cenni preliminari sul componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="a444a-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
