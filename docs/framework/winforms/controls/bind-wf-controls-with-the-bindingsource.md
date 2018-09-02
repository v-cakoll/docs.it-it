---
title: 'Procedura: associare controlli Windows Form al componente BindingSource utilizzando la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 95f375d8845c60441aa5eefdd37e32541ea2d5a7
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418597"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="3ebd0-102">Procedura: associare controlli Windows Form al componente BindingSource utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="3ebd0-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="3ebd0-103">Dopo aver aggiunto i controlli al form e determinare l'interfaccia utente per l'applicazione, è possibile associare i controlli a un'origine dati, in modo che, in fase di esecuzione, gli utenti possono modificare e salvare i dati correlati all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>  
  
 <span data-ttu-id="3ebd0-104">Associazione di un controllo o una serie di controlli in Windows Form viene effettuata più facilmente usando le <xref:System.Windows.Forms.BindingSource> controllo che funge da ponte tra i controlli nel form e l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>  
  
 <span data-ttu-id="3ebd0-105">Uno o più controlli in un form possono essere associati a dati. Nella procedura seguente, un <xref:System.Windows.Forms.TextBox> è associato a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>  
  
 <span data-ttu-id="3ebd0-106">Per completare la procedura, si presuppone che verrà associato a un'origine dati derivata da un database.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="3ebd0-107">Per altre informazioni sulla creazione di origini dati da altri archivi di dati, vedere [aggiungono nuove origini dati](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="3ebd0-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ebd0-108">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3ebd0-109">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="3ebd0-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3ebd0-110">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3ebd0-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="3ebd0-111">Per associare un controllo in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="3ebd0-111">To bind a control at design time</span></span>  
  
1.  <span data-ttu-id="3ebd0-112">Trascinare un <xref:System.Windows.Forms.TextBox> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-112">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>  
  
2.  <span data-ttu-id="3ebd0-113">Nel **proprietà** finestra:</span><span class="sxs-lookup"><span data-stu-id="3ebd0-113">In the **Properties** window:</span></span>  
  
    1.  <span data-ttu-id="3ebd0-114">Espandere la **(DataBindings)** nodo.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-114">Expand the **(DataBindings)** node.</span></span>  
  
    2.  <span data-ttu-id="3ebd0-115">Fare clic sulla freccia accanto al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-115">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
         <span data-ttu-id="3ebd0-116">Il **DataSource** verrà aperto l'editor di tipo dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-116">The **DataSource** UI type editor opens.</span></span>  
  
         <span data-ttu-id="3ebd0-117">Se un'origine dati è stata configurata in precedenza per il progetto o un modulo, verrà visualizzata.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-117">If a data source has previously been configured for the project or form, it will appear.</span></span>  
  
3.  <span data-ttu-id="3ebd0-118">Fare clic su **Aggiungi origine dati progetto** per connettersi ai dati e creare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-118">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
4.  <span data-ttu-id="3ebd0-119">Nella pagina iniziale della **Configurazione guidata origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-119">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="3ebd0-120">Nel **scegliere un tipo di origine dati** pagina, selezionare **Database**.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-120">On the **Choose a Data Source Type** page, select **Database**.</span></span>  
  
6.  <span data-ttu-id="3ebd0-121">Nel **Seleziona connessione dati** pagina, selezionare una connessione dati dall'elenco delle connessioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-121">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="3ebd0-122">Se la connessione dati desiderata non è disponibile, selezionare **nuova connessione** per creare una nuova connessione dati.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-122">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>  
  
7.  <span data-ttu-id="3ebd0-123">Selezionare **Sì, Salva la connessione** per salvare la stringa di connessione nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-123">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
8.  <span data-ttu-id="3ebd0-124">Selezionare gli oggetti database da inserire nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-124">Select the database objects to bring into your application.</span></span> <span data-ttu-id="3ebd0-125">In questo caso, selezionare un campo in una tabella che si desidera il <xref:System.Windows.Forms.TextBox> da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-125">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>  
  
9. <span data-ttu-id="3ebd0-126">Se si vuole, sostituire il nome predefinito del set di dati.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-126">Replace the default dataset name if you want.</span></span>  
  
10. <span data-ttu-id="3ebd0-127">Scegliere **Fine**.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-127">Click **Finish**.</span></span>  
  
11. <span data-ttu-id="3ebd0-128">Nel **delle proprietà** finestra, fare clic sulla freccia accanto al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà nuovamente.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-128">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="3ebd0-129">Nel **DataSource** editor di tipo dell'interfaccia utente, selezionare il nome del campo a cui associare il <xref:System.Windows.Forms.TextBox> a.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-129">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>  
  
     <span data-ttu-id="3ebd0-130">Il **DataSource** verrà chiuso editor e il set di dati di tipo UI <xref:System.Windows.Forms.BindingSource> e adattatore di tabella specifico di connessione dati verranno aggiunti al form.</span><span class="sxs-lookup"><span data-stu-id="3ebd0-130">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ebd0-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ebd0-131">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [<span data-ttu-id="3ebd0-132">Aggiungi nuova origine dati</span><span class="sxs-lookup"><span data-stu-id="3ebd0-132">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)  
 [<span data-ttu-id="3ebd0-133">Finestra Origini dati</span><span class="sxs-lookup"><span data-stu-id="3ebd0-133">Data Sources Window</span></span>](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)
