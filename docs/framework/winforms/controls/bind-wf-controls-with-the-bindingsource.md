---
title: Associare controlli al componente BindingSource utilizzando la finestra di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 35b3fb7b9884f07dd6e2aef311a01d3090c44227
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744387"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="1d903-102">Procedura: associare controlli Windows Form al componente BindingSource utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1d903-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="1d903-103">Dopo aver aggiunto i controlli al modulo e aver determinato l'interfaccia utente per l'applicazione, è possibile associare i controlli a un'origine dati, in modo che, in fase di esecuzione, gli utenti possano modificare e salvare i dati correlati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d903-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>

 <span data-ttu-id="1d903-104">L'associazione di un controllo o di una serie di controlli in Windows Forms viene eseguita più facilmente utilizzando il controllo <xref:System.Windows.Forms.BindingSource> come ponte tra i controlli nel form e l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1d903-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>

 <span data-ttu-id="1d903-105">Uno o più controlli in un modulo possono essere associati ai dati; nella procedura seguente un controllo <xref:System.Windows.Forms.TextBox> viene associato a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1d903-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>

 <span data-ttu-id="1d903-106">Per completare la procedura, si presuppone che si eseguirà l'associazione a un'origine dati derivata da un database.</span><span class="sxs-lookup"><span data-stu-id="1d903-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="1d903-107">Per altre informazioni sulla creazione di origini dati da altri archivi di dati, vedere [aggiungere nuove origini dati](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="1d903-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>

## <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="1d903-108">Per associare un controllo in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="1d903-108">To bind a control at design time</span></span>

1. <span data-ttu-id="1d903-109">Trascinare un controllo <xref:System.Windows.Forms.TextBox> sul form.</span><span class="sxs-lookup"><span data-stu-id="1d903-109">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>

2. <span data-ttu-id="1d903-110">Nella finestra **Proprietà** :</span><span class="sxs-lookup"><span data-stu-id="1d903-110">In the **Properties** window:</span></span>

    1. <span data-ttu-id="1d903-111">Espandere il nodo **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="1d903-111">Expand the **(DataBindings)** node.</span></span>

    2. <span data-ttu-id="1d903-112">Fare clic sulla freccia accanto alla proprietà <xref:System.Windows.Forms.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d903-112">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

         <span data-ttu-id="1d903-113">Si apre l'editor di tipo dell'interfaccia utente **DataSource** .</span><span class="sxs-lookup"><span data-stu-id="1d903-113">The **DataSource** UI type editor opens.</span></span>

         <span data-ttu-id="1d903-114">Se un'origine dati è stata configurata in precedenza per il progetto o il form, verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="1d903-114">If a data source has previously been configured for the project or form, it will appear.</span></span>

3. <span data-ttu-id="1d903-115">Fare clic su **Aggiungi origine dati progetto** per connettersi ai dati e creare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1d903-115">Click **Add Project Data Source** to connect to data and create a data source.</span></span>

4. <span data-ttu-id="1d903-116">Nella pagina iniziale della **Configurazione guidata origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1d903-116">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>

5. <span data-ttu-id="1d903-117">Nella pagina **scegliere un tipo di origine dati** selezionare **database**.</span><span class="sxs-lookup"><span data-stu-id="1d903-117">On the **Choose a Data Source Type** page, select **Database**.</span></span>

6. <span data-ttu-id="1d903-118">Nella pagina **Seleziona connessione dati** selezionare una connessione dati nell'elenco delle connessioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="1d903-118">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="1d903-119">Se la connessione dati desiderata non è disponibile, selezionare **nuova connessione** per creare una nuova connessione dati.</span><span class="sxs-lookup"><span data-stu-id="1d903-119">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>

7. <span data-ttu-id="1d903-120">Selezionare **Sì, salva la connessione** per salvare la stringa di connessione nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d903-120">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>

8. <span data-ttu-id="1d903-121">Selezionare gli oggetti database da inserire nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d903-121">Select the database objects to bring into your application.</span></span> <span data-ttu-id="1d903-122">In questo caso, selezionare un campo in una tabella che si desidera visualizzare nel <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1d903-122">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>

9. <span data-ttu-id="1d903-123">Se si vuole, sostituire il nome predefinito del set di dati.</span><span class="sxs-lookup"><span data-stu-id="1d903-123">Replace the default dataset name if you want.</span></span>

10. <span data-ttu-id="1d903-124">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="1d903-124">Click **Finish**.</span></span>

11. <span data-ttu-id="1d903-125">Nella finestra **Proprietà** fare clic sulla freccia accanto alla proprietà <xref:System.Windows.Forms.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="1d903-125">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="1d903-126">Nell'editor di tipo dell'interfaccia utente **DataSource** selezionare il nome del campo a cui associare il <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="1d903-126">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>

     <span data-ttu-id="1d903-127">L'editor di tipo dell'interfaccia utente **DataSource** si chiude e il set di dati, la <xref:System.Windows.Forms.BindingSource> e l'adattatore tabella specifici della connessione dati vengono aggiunti al form.</span><span class="sxs-lookup"><span data-stu-id="1d903-127">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d903-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d903-128">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="1d903-129">Aggiungi nuova origine dati</span><span class="sxs-lookup"><span data-stu-id="1d903-129">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="1d903-130">[Finestra Origini dati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="1d903-130">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
