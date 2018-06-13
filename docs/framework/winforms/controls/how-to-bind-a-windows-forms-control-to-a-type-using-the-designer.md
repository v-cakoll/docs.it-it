---
title: 'Procedura: associare un controllo Windows Form a un tipo mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: a58a528cd1a2246ddfdff7997b7c7cb0d8dcc6a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531053"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="5c1ea-102">Procedura: associare un controllo Windows Form a un tipo mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="5c1ea-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="5c1ea-103">Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo anziché a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="5c1ea-104">Di solito è necessario associare un controllo a un tipo in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati ai dati devono comunque visualizzare i dati provenienti dall'interfaccia pubblica di un tipo.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="5c1ea-105">Le procedure seguenti viene illustrato come creare un nuovo <xref:System.Windows.Forms.BindingSource> che è associato a un tipo e quindi come associare una delle proprietà del tipo per il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà di un <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="5c1ea-106">Per associare BindingSource a un tipo</span><span class="sxs-lookup"><span data-stu-id="5c1ea-106">To bind the BindingSource to a type</span></span>  
  
1.  <span data-ttu-id="5c1ea-107">Creare un nuovo progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-107">Create a Windows Forms project.</span></span>  
  
     <span data-ttu-id="5c1ea-108">Per altre informazioni, vedere [Procedura: Creare un nuovo progetto di applicazione Windows Form](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="5c1ea-108">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="5c1ea-109">In **progettazione** visualizzare, trascinare un <xref:System.Windows.Forms.BindingSource> componente al form.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-109">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3.  <span data-ttu-id="5c1ea-110">Nel **proprietà** finestra, fare clic sulla freccia per la <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-110">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4.  <span data-ttu-id="5c1ea-111">Nell'**editor di tipo con interfaccia utente DataSource** fare clic su **Aggiungi origine dati progetto**.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-111">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5.  <span data-ttu-id="5c1ea-112">Nella pagina **Selezionare un tipo di origine dati** selezionare **Oggetto** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-112">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6.  <span data-ttu-id="5c1ea-113">Selezionare il tipo da associare:</span><span class="sxs-lookup"><span data-stu-id="5c1ea-113">Select the type to bind to:</span></span>  
  
    -   <span data-ttu-id="5c1ea-114">Se il tipo da associare è nel progetto corrente o l'assembly che contiene il tipo è già stato aggiunto come riferimento, espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-114">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="5c1ea-115">oppure</span><span class="sxs-lookup"><span data-stu-id="5c1ea-115">-or-</span></span>  
  
    -   <span data-ttu-id="5c1ea-116">Se il tipo da associare è in un altro assembly, attualmente non presente nell'elenco di riferimenti, fare clic su **Aggiungi riferimento**, quindi fare clic sulla scheda **Progetti**. Selezionare il progetto che contiene l'oggetto business desiderato e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-116">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="5c1ea-117">Il progetto verrà visualizzato nell'elenco di assembly e sarà possibile espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-117">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5c1ea-118">Se si vuole associare un tipo in un framework o assembly Microsoft, deselezionare la casella di controllo **Nascondi assembly che iniziano con Microsoft o System**.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-118">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7.  <span data-ttu-id="5c1ea-119">Scegliere **Avanti**e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-119">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="5c1ea-120">Per associare il controllo a BindingSource</span><span class="sxs-lookup"><span data-stu-id="5c1ea-120">To bind the control to the BindingSource</span></span>  
  
1.  <span data-ttu-id="5c1ea-121">Aggiungere un tipo <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-121">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2.  <span data-ttu-id="5c1ea-122">Nella finestra **Proprietà** espandere il nodo **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="5c1ea-122">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3.  <span data-ttu-id="5c1ea-123">Fare clic sulla freccia accanto al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-123">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4.  <span data-ttu-id="5c1ea-124">Nel **editor del tipo di interfaccia utente DataSource**, espandere il nodo per il <xref:System.Windows.Forms.BindingSource> aggiunto in precedenza e selezionare la proprietà del tipo associato che si desidera associare il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="5c1ea-124">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1ea-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c1ea-125">See Also</span></span>  
 [<span data-ttu-id="5c1ea-126">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="5c1ea-126">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="5c1ea-127">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="5c1ea-127">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [<span data-ttu-id="5c1ea-128">Associare controlli ai dati in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="5c1ea-128">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
