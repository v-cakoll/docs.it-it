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
# <a name="how-to-add-load-save-and-cancel-buttons-to-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="92ed3-102">Procedura: aggiungere i pulsanti Carica, Salva e Annulla al controllo BindingNavigator di Windows Form</span><span class="sxs-lookup"><span data-stu-id="92ed3-102">How to: Add Load, Save, and Cancel Buttons to the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="92ed3-103">Il <xref:System.Windows.Forms.BindingNavigator> controllo è una speciale <xref:System.Windows.Forms.ToolStrip> controllo specifico per la navigazione e modifica dei controlli sul form che vengono associati ai dati.</span><span class="sxs-lookup"><span data-stu-id="92ed3-103">The <xref:System.Windows.Forms.BindingNavigator> control is a special-purpose <xref:System.Windows.Forms.ToolStrip> control that is intended for navigating and manipulating controls on your form that are bound to data.</span></span>  
  
 <span data-ttu-id="92ed3-104">Perché è un <xref:System.Windows.Forms.ToolStrip> (controllo), il <xref:System.Windows.Forms.BindingNavigator> componente può essere facilmente modificato per includere comandi aggiuntivi o alternativi dell'utente.</span><span class="sxs-lookup"><span data-stu-id="92ed3-104">Because it is a <xref:System.Windows.Forms.ToolStrip> control, the <xref:System.Windows.Forms.BindingNavigator> component can be easily modified to include additional or alternative commands for the user.</span></span>  
  
 <span data-ttu-id="92ed3-105">Nella procedura seguente, un <xref:System.Windows.Forms.TextBox> è associato a dati e il <xref:System.Windows.Forms.ToolStrip> controllo che viene aggiunto al form viene modificato per includere caricamento, salvataggio e i pulsanti Annulla.</span><span class="sxs-lookup"><span data-stu-id="92ed3-105">In the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to data, and the <xref:System.Windows.Forms.ToolStrip> control that is added to the form is modified to include load, save, and cancel buttons.</span></span>  
  
### <a name="to-add-load-save-and-cancel-buttons-to-the-bindingnavigator-component"></a><span data-ttu-id="92ed3-106">Per aggiungere carica, Salva e Annulla i pulsanti per il componente di BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="92ed3-106">To add load, save, and cancel buttons to the BindingNavigator component</span></span>  
  
1.  <span data-ttu-id="92ed3-107">Aggiungere un oggetto <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="92ed3-107">Add a <xref:System.Windows.Forms.TextBox> control to your form.</span></span>  
  
2.  <span data-ttu-id="92ed3-108">Associarlo a un <xref:System.Windows.Forms.BindingSource>, che è associato a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="92ed3-108">Bind it to a <xref:System.Windows.Forms.BindingSource>, which is bound to a data source.</span></span> <span data-ttu-id="92ed3-109">In questo esempio il <xref:System.Windows.Forms.BindingSource> è associato a un database.</span><span class="sxs-lookup"><span data-stu-id="92ed3-109">For this example, the <xref:System.Windows.Forms.BindingSource> is bound to a database.</span></span>  
  
3.  <span data-ttu-id="92ed3-110">Una volta generato il set di dati e tabella la scheda, trascinare un <xref:System.Windows.Forms.BindingNavigator> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="92ed3-110">After the dataset and table adapter are generated, drag a <xref:System.Windows.Forms.BindingNavigator> control to the form.</span></span>  
  
4.  <span data-ttu-id="92ed3-111">Impostare il <xref:System.Windows.Forms.BindingNavigator> del controllo <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> proprietà di <xref:System.Windows.Forms.BindingSource> nel form di cui è associato ai controlli.</span><span class="sxs-lookup"><span data-stu-id="92ed3-111">Set the <xref:System.Windows.Forms.BindingNavigator> control's <xref:System.Windows.Forms.BindingNavigator.BindingSource%2A> property to the <xref:System.Windows.Forms.BindingSource> on the form that is bound to the controls.</span></span>  
  
5.  <span data-ttu-id="92ed3-112">Selezionare il controllo <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="92ed3-112">Select the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
6.  <span data-ttu-id="92ed3-113">Fare clic sul glifo dello smart tag (![glifo Smart Tag](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) in modo che il **le attività di BindingNavigator** finestra di dialogo e selezionare **Modifica elementi**.</span><span class="sxs-lookup"><span data-stu-id="92ed3-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) so the **BindingNavigator Tasks** dialog appears and select **Edit Items**.</span></span>  
  
     <span data-ttu-id="92ed3-114">Il **Editor della raccolta Items** viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="92ed3-114">The **Items Collection Editor** appears.</span></span>  
  
7.  <span data-ttu-id="92ed3-115">Nel **Editor della raccolta Items**, completare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="92ed3-115">In the **Items Collection Editor**, complete the following:</span></span>  
  
    1.  <span data-ttu-id="92ed3-116">Aggiungi un <xref:System.Windows.Forms.ToolStripSeparator> e tre <xref:System.Windows.Forms.ToolStripButton> selezionando il tipo appropriato di elementi <xref:System.Windows.Forms.ToolStripItem> e facendo clic sui **Add** pulsante.</span><span class="sxs-lookup"><span data-stu-id="92ed3-116">Add a <xref:System.Windows.Forms.ToolStripSeparator> and three <xref:System.Windows.Forms.ToolStripButton> items by selecting the appropriate type of <xref:System.Windows.Forms.ToolStripItem> and clicking the **Add** button.</span></span>  
  
    2.  <span data-ttu-id="92ed3-117">Impostare il <xref:System.Windows.Forms.ToolStripItem.Name%2A> proprietà dei pulsanti per **LoadButton**, **PulsanteSalva**, e **CancelButton**, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="92ed3-117">Set the <xref:System.Windows.Forms.ToolStripItem.Name%2A> property of the buttons to **LoadButton**, **SaveButton**, and **CancelButton**, respectively.</span></span>  
  
    3.  <span data-ttu-id="92ed3-118">Impostare il <xref:System.Windows.Forms.ToolStripItem.Text%2A> proprietà dei pulsanti per **Load**, **salvare**, e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="92ed3-118">Set the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property of the buttons to **Load**, **Save**, and **Cancel**.</span></span>  
  
    4.  <span data-ttu-id="92ed3-119">Impostare il <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> proprietà per ognuno dei pulsanti per **testo**.</span><span class="sxs-lookup"><span data-stu-id="92ed3-119">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property for each of the buttons to **Text**.</span></span> <span data-ttu-id="92ed3-120">In alternativa, è possibile impostare questa proprietà **immagine** oppure **ImageAndText**e impostare l'immagine da visualizzare nel <xref:System.Windows.Forms.ToolStripItem.Image%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="92ed3-120">Alternatively, you can set this property to **Image** or **ImageAndText**, and set the image to be displayed in the <xref:System.Windows.Forms.ToolStripItem.Image%2A> property.</span></span>  
  
    5.  <span data-ttu-id="92ed3-121">Fare clic su **OK** per chiudere la finestra di dialogo. Vengono aggiunti i pulsanti per il <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="92ed3-121">Click **OK** to close the dialog box.The buttons are added to the <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
8.  <span data-ttu-id="92ed3-122">Fare clic sulla forma e scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="92ed3-122">Right-click the form and choose **View Code**.</span></span>  
  
9. <span data-ttu-id="92ed3-123">Nell'Editor di codice, trovare la riga di codice che carica i dati nell'adattatore di tabella.</span><span class="sxs-lookup"><span data-stu-id="92ed3-123">In the Code Editor, find the line of code that loads data into the table adapter.</span></span> <span data-ttu-id="92ed3-124">Questo codice è stato generato quando si configura il data binding nel passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="92ed3-124">This code was generated when you set up the data binding in step 2.</span></span> <span data-ttu-id="92ed3-125">Il codice dovrebbe essere simile al seguente: `TableAdapterName.Fill(DataSetName.TableName)`.</span><span class="sxs-lookup"><span data-stu-id="92ed3-125">The code should be similar to the following: `TableAdapterName.Fill(DataSetName.TableName)`.</span></span> <span data-ttu-id="92ed3-126">Si verifica più probabilmente avere il formato <xref:System.Windows.Forms.Form.Load> evento.</span><span class="sxs-lookup"><span data-stu-id="92ed3-126">It will most likely be in the form's <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
10. <span data-ttu-id="92ed3-127">Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> eventi del **Load** <xref:System.Windows.Forms.ToolStripButton> è creato in precedenza e spostare il codice di caricamento dei dati al suo interno.</span><span class="sxs-lookup"><span data-stu-id="92ed3-127">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Load** <xref:System.Windows.Forms.ToolStripButton> you created earlier and move this data-loading code into it.</span></span>  
  
     <span data-ttu-id="92ed3-128">Il codice dovrebbe ora essere simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="92ed3-128">Your code should now look similar to the following:</span></span>  
  
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
  
11. <span data-ttu-id="92ed3-129">Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> eventi del **salvare** <xref:System.Windows.Forms.ToolStripButton> creato in precedenza e scrivere il codice per aggiornare i dati all'interno della tabella del controllo associato a.</span><span class="sxs-lookup"><span data-stu-id="92ed3-129">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Save**<xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to update the data within the table the control is bound to.</span></span>  
  
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
    > <span data-ttu-id="92ed3-130">In alcuni casi, il <xref:System.Windows.Forms.BindingNavigator> componente avrà già una **salvare** pulsante, ma nessun codice verrà sono stati generati da Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="92ed3-130">In some cases, the <xref:System.Windows.Forms.BindingNavigator> component will already have a **Save** button, but no code will have been generated by the Windows Forms Designer.</span></span> <span data-ttu-id="92ed3-131">In questo caso, è possibile inserire il codice precedente nel <xref:System.Windows.Forms.ToolStripItem.Click> gestore eventi per tale pulsante, anziché creare un pulsante completamente nuovo nel <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="92ed3-131">In this case, you can place the preceding code in the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for that button, rather than creating an entirely new button on the <xref:System.Windows.Forms.ToolStrip>.</span></span> <span data-ttu-id="92ed3-132">Tuttavia, il pulsante è disabilitato per impostazione predefinita, pertanto è necessario impostare il <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> proprietà del pulsante su `true` affinché funzioni correttamente.</span><span class="sxs-lookup"><span data-stu-id="92ed3-132">However, the button is disabled by default, so you must set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property of the button to `true` to have the button function correctly.</span></span>
  
12. <span data-ttu-id="92ed3-133">Creare un gestore eventi per il <xref:System.Windows.Forms.ToolStripItem.Click> eventi del **annullare** <xref:System.Windows.Forms.ToolStripButton> è creato in precedenza e scrivere codice per annullare le modifiche al record di dati che viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="92ed3-133">Create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event of the **Cancel** <xref:System.Windows.Forms.ToolStripButton> you created earlier and write code to cancel any changes to the data record that is displayed.</span></span>  
  
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
    >  <span data-ttu-id="92ed3-134">Il <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> metodo ha come ambito la riga di dati.</span><span class="sxs-lookup"><span data-stu-id="92ed3-134">The <xref:System.Windows.Forms.BindingSource.CancelEdit%2A> method is scoped to the row of data.</span></span> <span data-ttu-id="92ed3-135">Salvare le modifiche apportate durante la visualizzazione dei singoli record prima di passare al record successivo.</span><span class="sxs-lookup"><span data-stu-id="92ed3-135">Save any changes you make while viewing that individual record before navigating to the next record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ed3-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92ed3-136">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.ToolStrip>  
 [<span data-ttu-id="92ed3-137">Controllo BindingNavigator</span><span class="sxs-lookup"><span data-stu-id="92ed3-137">BindingNavigator Control</span></span>](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [<span data-ttu-id="92ed3-138">Cenni preliminari sul componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="92ed3-138">BindingSource Component Overview</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)
