---
title: Aggiungere i pulsanti carica, Salva e Annulla al controllo BindingNavigator
description: Informazioni su come aggiungere i pulsanti carica, Salva e Annulla al Windows Forms controllo BindingNavigator.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], manipulating
- BindingNavigator control [Windows Forms], adding buttons
ms.assetid: faa33042-186e-4bb2-8798-17ceb987ec62
ms.openlocfilehash: d4db91b8cfaf2df253d0c4cf5d8a66e9157d4986
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173419"
---
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="6d147-103">Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6d147-103">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="6d147-104">Il <xref:System.Windows.Forms.BindingNavigator> controllo è un <xref:System.Windows.Forms.ToolStrip> controllo per scopi specifici che consente di spostarsi e modificare i controlli nel form associati ai dati.</span><span class="sxs-lookup"><span data-stu-id="6d147-104">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="6d147-105">Poiché si tratta di un <xref:System.Windows.Forms.ToolStrip> controllo, è <xref:System.Windows.Forms.BindingNavigator> possibile modificare facilmente il componente per includere comandi aggiuntivi o alternativi per l'utente.</span><span class="sxs-lookup"><span data-stu-id="6d147-105">Because it's a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="6d147-106">Nella procedura seguente <xref:System.Windows.Forms.TextBox> viene associato un controllo ai dati e il <xref:System.Windows.Forms.ToolStrip> controllo aggiunto al form viene modificato per includere i pulsanti Load, Save e Cancel.</span><span class="sxs-lookup"><span data-stu-id="6d147-106">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="6d147-107">Aggiungere i pulsanti carica, Salva e Annulla al componente BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="6d147-107">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="6d147-108">In Visual Studio aggiungere un <xref:System.Windows.Forms.TextBox> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="6d147-108">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="6d147-109">Associarlo a un oggetto <xref:System.Windows.Forms.BindingSource> , che è associato a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6d147-109">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="6d147-110">Per questo esempio, l'oggetto <xref:System.Windows.Forms.BindingSource> è associato a un database.</span><span class="sxs-lookup"><span data-stu-id="6d147-110">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="6d147-111">Dopo aver generato il set di dati e l'adattatore tabella, trascinare un <xref:System.Windows.Forms.BindingNavigator> controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="6d147-111">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="6d147-112">Impostare la <xref:System.Windows.Forms.BindingNavigator> proprietà del controllo <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> <xref:System.Windows.Forms.BindingSource> su sul form associato ai controlli.</span><span class="sxs-lookup"><span data-stu-id="6d147-112">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="6d147-113">Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="6d147-113">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="6d147-114">Fare clic sul glifo azioni della finestra di progettazione ( ![ piccola freccia nera ](./media/designer-actions-glyph.gif) ) per visualizzare la finestra di dialogo **attività di BindingNavigator** e selezionare **modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="6d147-114">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="6d147-115">Viene visualizzato l' **Editor della raccolta Items** .</span><span class="sxs-lookup"><span data-stu-id="6d147-115">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="6d147-116">Nell' **Editor della raccolta Items**completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6d147-116">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="6d147-117">Aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> e tre <xref:System.Windows.Forms.ToolStripButton> elementi selezionando il tipo appropriato di <xref:System.Windows.Forms.ToolStripItem> e facendo clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="6d147-117">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="6d147-118">Impostare la <xref:System.Windows.Forms.ToolStripItem.Name%2A> proprietà dei pulsanti rispettivamente su **LoadButton**, **pulsanteSalva**e **CancelButton**.</span><span class="sxs-lookup"><span data-stu-id="6d147-118">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="6d147-119">Impostare la <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà dei pulsanti su **carica**, **Salva**e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="6d147-119">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="6d147-120">Impostare la <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà per ognuno dei pulsanti su **testo**.</span><span class="sxs-lookup"><span data-stu-id="6d147-120">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="6d147-121">In alternativa, è possibile impostare questa proprietà su **Image** o **ImageAndText**e impostare l'immagine da visualizzare nella <xref:System.Windows.Forms.ToolStripItem.Image%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="6d147-121">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="6d147-122">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6d147-122">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="6d147-123">I pulsanti vengono aggiunti a <xref:System.Windows.Forms.ToolStrip> .</span><span class="sxs-lookup"><span data-stu-id="6d147-123">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="6d147-124">Fare clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="6d147-124">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="6d147-125">Nell'editor di codice trovare la riga di codice che carica i dati nell'adattatore della tabella.</span><span class="sxs-lookup"><span data-stu-id="6d147-125">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="6d147-126">Questo codice è stato generato quando si configura il data binding nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="6d147-126">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="6d147-127">Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)` .</span><span class="sxs-lookup"><span data-stu-id="6d147-127">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="6d147-128">Probabilmente si troverà nell'evento del modulo <xref:System.Windows.Forms.Form.Load> .</span><span class="sxs-lookup"><span data-stu-id="6d147-128">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="6d147-129">Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento del **carico** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e spostarvi il codice di caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="6d147-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="6d147-130">Il codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6d147-130">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="6d147-131">Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento del **salvataggio** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per aggiornare i dati all'interno della tabella a cui è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="6d147-131">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="6d147-132">In alcuni casi, il <xref:System.Windows.Forms.BindingNavigator> componente ha già un pulsante **Salva** , ma non è stato generato alcun codice dal progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="6d147-132">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="6d147-133">In questo caso, è possibile inserire il codice precedente nel <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per tale pulsante, anziché creare un pulsante completamente nuovo in <xref:System.Windows.Forms.ToolStrip> .</span><span class="sxs-lookup"><span data-stu-id="6d147-133">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="6d147-134">Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario impostare la <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> proprietà del pulsante su per fare in modo che `true` il pulsante funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="6d147-134">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="6d147-135">Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento dell' **annullamento** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per annullare tutte le modifiche apportate al record di dati visualizzato.</span><span class="sxs-lookup"><span data-stu-id="6d147-135">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="6d147-136">Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo ha come ambito la riga di dati.</span><span class="sxs-lookup"><span data-stu-id="6d147-136">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="6d147-137">Salvare le modifiche apportate durante la visualizzazione del singolo record prima di passare al record successivo.</span><span class="sxs-lookup"><span data-stu-id="6d147-137">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d147-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d147-138">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="6d147-139">Controllo BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="6d147-139">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="6d147-140">Cenni preliminari sul componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="6d147-140">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
