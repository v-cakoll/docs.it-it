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
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="d9899-102">Procedura: Aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d9899-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>

<span data-ttu-id="d9899-103">Il <xref:System.Windows.Forms.BindingNavigator> controllo è un controllo per scopi <xref:System.Windows.Forms.ToolStrip> specifici che consente di spostarsi e modificare i controlli nel form associati ai dati.</span><span class="sxs-lookup"><span data-stu-id="d9899-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>

<span data-ttu-id="d9899-104">Poiché si tratta di <xref:System.Windows.Forms.ToolStrip> un controllo, <xref:System.Windows.Forms.BindingNavigator> è possibile modificare facilmente il componente per includere comandi aggiuntivi o alternativi per l'utente.</span><span class="sxs-lookup"><span data-stu-id="d9899-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>

<span data-ttu-id="d9899-105">Nella procedura seguente viene associato un <xref:System.Windows.Forms.TextBox> controllo ai dati e il controllo aggiunto al <xref:System.Windows.Forms.ToolStrip> form viene modificato per includere i pulsanti Load, Save e Cancel.</span><span class="sxs-lookup"><span data-stu-id="d9899-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>

## <a name="add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="d9899-106">Aggiungere i pulsanti carica, Salva e Annulla al componente BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="d9899-106">Add load, save, and cancel buttons to the BindingNavigator component</span></span>

1. <span data-ttu-id="d9899-107">In Visual Studio aggiungere un <xref:System.Windows.Forms.TextBox> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="d9899-107">In Visual Studio, add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>

2. <span data-ttu-id="d9899-108">Associarlo a un <xref:System.Windows.Forms.BindingSource>oggetto, che è associato a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="d9899-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="d9899-109">Per questo esempio, l' <xref:System.Windows.Forms.BindingSource> oggetto è associato a un database.</span><span class="sxs-lookup"><span data-stu-id="d9899-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>

3. <span data-ttu-id="d9899-110">Dopo aver generato il set di dati e l'adattatore tabella <xref:System.Windows.Forms.BindingNavigator> , trascinare un controllo nel form.</span><span class="sxs-lookup"><span data-stu-id="d9899-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>

4. <span data-ttu-id="d9899-111">Impostare la <xref:System.Windows.Forms.BindingNavigator> <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> proprietà<xref:System.Windows.Forms.BindingSource> del controllo su sul form associato ai controlli.</span><span class="sxs-lookup"><span data-stu-id="d9899-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>

5. <span data-ttu-id="d9899-112">Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="d9899-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>

6. <span data-ttu-id="d9899-113">Fare clic sul glifo smart tag (![glifo smart tag](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in modo che venga visualizzata la finestra di dialogo **attività di BindingNavigator** e selezionare **modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="d9899-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>

     <span data-ttu-id="d9899-114">Viene visualizzato l' **Editor della raccolta Items** .</span><span class="sxs-lookup"><span data-stu-id="d9899-114">The **Items Collection Editor** appears.</span></span>

7. <span data-ttu-id="d9899-115">Nell' **Editor della raccolta Items**completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9899-115">In the **Items Collection Editor**, complete the following:</span></span>

    1. <span data-ttu-id="d9899-116">Aggiungere un <xref:System.Windows.Forms.ToolStripSeparator> e tre <xref:System.Windows.Forms.ToolStripButton> elementi selezionando il tipo appropriato di <xref:System.Windows.Forms.ToolStripItem> e facendo clic sul pulsante **Aggiungi** .</span><span class="sxs-lookup"><span data-stu-id="d9899-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>

    2. <span data-ttu-id="d9899-117">Impostare la <xref:System.Windows.Forms.ToolStripItem.Name%2A> proprietà dei pulsanti rispettivamente su **LoadButton**, **pulsanteSalva**e **CancelButton**.</span><span class="sxs-lookup"><span data-stu-id="d9899-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>

    3. <span data-ttu-id="d9899-118">Impostare la <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà dei pulsanti su **carica**, **Salva**e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="d9899-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>

    4. <span data-ttu-id="d9899-119">Impostare la <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà per ognuno dei pulsanti su **testo**.</span><span class="sxs-lookup"><span data-stu-id="d9899-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="d9899-120">In alternativa, è possibile impostare questa proprietà su **Image** o **ImageAndText**e impostare l'immagine da <xref:System.Windows.Forms.ToolStripItem.Image%2A> visualizzare nella proprietà.</span><span class="sxs-lookup"><span data-stu-id="d9899-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>

    5. <span data-ttu-id="d9899-121">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="d9899-121">Click **OK** to close the dialog box.</span></span> <span data-ttu-id="d9899-122">I pulsanti vengono aggiunti a <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="d9899-122">The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>

8. <span data-ttu-id="d9899-123">Fare clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="d9899-123">Right-click the form and choose **View Code**.</span></span>

9. <span data-ttu-id="d9899-124">Nell'editor di codice trovare la riga di codice che carica i dati nell'adattatore della tabella.</span><span class="sxs-lookup"><span data-stu-id="d9899-124">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="d9899-125">Questo codice è stato generato quando si configura il data binding nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="d9899-125">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="d9899-126">Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="d9899-126">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="d9899-127">Probabilmente si troverà nell' <xref:System.Windows.Forms.Form.Load> evento del modulo.</span><span class="sxs-lookup"><span data-stu-id="d9899-127">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>

10. <span data-ttu-id="d9899-128">Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento del **carico** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e spostarvi il codice di caricamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="d9899-128">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>

     <span data-ttu-id="d9899-129">Il codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="d9899-129">Your code should now look similar to the following:</span></span>

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

11. <span data-ttu-id="d9899-130">Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento del **salvataggio** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per aggiornare i dati all'interno della tabella a cui è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="d9899-130">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>

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
    > <span data-ttu-id="d9899-131">In alcuni casi, il <xref:System.Windows.Forms.BindingNavigator> componente ha già un pulsante **Salva** , ma non è stato generato alcun codice dal progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="d9899-131">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component already has a **Save** button, but no code has been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="d9899-132">In questo caso, è possibile inserire il codice precedente nel <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per tale pulsante, anziché creare un pulsante completamente nuovo <xref:System.Windows.Forms.ToolStrip>in.</span><span class="sxs-lookup"><span data-stu-id="d9899-132">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="d9899-133">Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> impostare la proprietà del pulsante `true` su per fare in modo che il pulsante funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="d9899-133">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>

12. <span data-ttu-id="d9899-134">Creare un gestore eventi per l' <xref:System.Windows.Forms.ToolStripItem.Click> evento dell' **annullamento** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere codice per annullare tutte le modifiche apportate al record di dati visualizzato.</span><span class="sxs-lookup"><span data-stu-id="d9899-134">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>

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
    > <span data-ttu-id="d9899-135">Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo ha come ambito la riga di dati.</span><span class="sxs-lookup"><span data-stu-id="d9899-135">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="d9899-136">Salvare le modifiche apportate durante la visualizzazione del singolo record prima di passare al record successivo.</span><span class="sxs-lookup"><span data-stu-id="d9899-136">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9899-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9899-137">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.ToolStrip>
- [<span data-ttu-id="d9899-138">Controllo BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="d9899-138">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="d9899-139">Cenni preliminari sul componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="d9899-139">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)
