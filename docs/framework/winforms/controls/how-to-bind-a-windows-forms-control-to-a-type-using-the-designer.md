---
title: 'Procedura: associare un controllo Windows Form a un tipo mediante la finestra di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 5ab984b5-c2d0-4638-a572-1c84013e8746
ms.openlocfilehash: 33df9e050dd8c2b3ace8ff89cbd5939b538fcd95
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969444"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type-using-the-designer"></a><span data-ttu-id="38577-102">Procedura: associare un controllo Windows Form a un tipo mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="38577-102">How to: Bind a Windows Forms Control to a Type Using the Designer</span></span>
<span data-ttu-id="38577-103">Quando si compilano controlli che interagiscono con i dati, a volte è necessario associare un controllo a un tipo anziché a un oggetto.</span><span class="sxs-lookup"><span data-stu-id="38577-103">When you are building controls that interact with data, you sometimes need to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="38577-104">Di solito è necessario associare un controllo a un tipo in fase di progettazione, quando i dati potrebbero non essere disponibili, ma i controlli associati ai dati devono comunque visualizzare i dati provenienti dall'interfaccia pubblica di un tipo.</span><span class="sxs-lookup"><span data-stu-id="38577-104">You typically need to bind a control to a type at design time, when data may not be available, but you still want your data-bound controls to display data from a type's public interface.</span></span> <span data-ttu-id="38577-105">Le procedure seguenti viene illustrato come creare una nuova <xref:System.Windows.Forms.BindingSource> che è associato a un tipo e quindi come associare una delle proprietà del tipo per il <xref:System.Windows.Forms.TextBox.Text%2A> proprietà di un <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="38577-105">The following procedures demonstrate how to create a new <xref:System.Windows.Forms.BindingSource> that is bound to a type, and then how to bind one of the type's properties to the <xref:System.Windows.Forms.TextBox.Text%2A> property of a <xref:System.Windows.Forms.TextBox>.</span></span>  
  
### <a name="to-bind-the-bindingsource-to-a-type"></a><span data-ttu-id="38577-106">Per associare BindingSource a un tipo</span><span class="sxs-lookup"><span data-stu-id="38577-106">To bind the BindingSource to a type</span></span>  
  
1.  <span data-ttu-id="38577-107">Creare un progetto Windows Form (**File** > **New** > **progetto** > **Visual C#** o **Visual Basic** > **Desktop classico** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="38577-107">Create a Windows Forms project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="38577-108">Nelle **Design** visualizzazione, trascinare un <xref:System.Windows.Forms.BindingSource> componente al form.</span><span class="sxs-lookup"><span data-stu-id="38577-108">In **Design** view, drag a <xref:System.Windows.Forms.BindingSource> component onto the form.</span></span>  
  
3.  <span data-ttu-id="38577-109">Nel **delle proprietà** finestra, fare clic sulla freccia per il <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="38577-109">In the **Properties** window, click the arrow for the <xref:System.Windows.Forms.BindingSource.DataSource%2A> property.</span></span>  
  
4.  <span data-ttu-id="38577-110">Nell'**editor di tipo con interfaccia utente DataSource** fare clic su **Aggiungi origine dati progetto**.</span><span class="sxs-lookup"><span data-stu-id="38577-110">In the **DataSource UI Type Editor**, click **Add Project Data Source**.</span></span>  
  
5.  <span data-ttu-id="38577-111">Nella pagina **Selezionare un tipo di origine dati** selezionare **Oggetto** e fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="38577-111">On the **Choose a Data Source Type** page, select **Object** and click **Next**.</span></span>  
  
6.  <span data-ttu-id="38577-112">Selezionare il tipo da associare:</span><span class="sxs-lookup"><span data-stu-id="38577-112">Select the type to bind to:</span></span>  
  
    -   <span data-ttu-id="38577-113">Se il tipo da associare è nel progetto corrente o l'assembly che contiene il tipo è già stato aggiunto come riferimento, espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="38577-113">If the type you want to bind to is in the current project, or the assembly that contains the type is already added as a reference, expand the nodes to find the type you want, and then select it.</span></span>  
  
         <span data-ttu-id="38577-114">oppure</span><span class="sxs-lookup"><span data-stu-id="38577-114">-or-</span></span>  
  
    -   <span data-ttu-id="38577-115">Se il tipo da associare è in un altro assembly, attualmente non presente nell'elenco di riferimenti, fare clic su **Aggiungi riferimento**, quindi fare clic sulla scheda **Progetti**. Selezionare il progetto che contiene l'oggetto business desiderato e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="38577-115">If the type you want to bind to is in another assembly, not currently in the list of references, click **Add Reference**, and then click the **Projects** tab. Select the project that contains the business object you want and click **OK**.</span></span> <span data-ttu-id="38577-116">Il progetto verrà visualizzato nell'elenco di assembly e sarà possibile espandere i nodi per trovare il tipo desiderato e quindi selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="38577-116">This project will appear in the list of assemblies, so you can expand the nodes to find the type you want, and then select it.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="38577-117">Se si vuole associare un tipo in un framework o assembly Microsoft, deselezionare la casella di controllo **Nascondi assembly che iniziano con Microsoft o System**.</span><span class="sxs-lookup"><span data-stu-id="38577-117">If you want to bind to a type in a framework or Microsoft assembly, clear the **Hide assemblies that begin with Microsoft or System** check box.</span></span>  
  
7.  <span data-ttu-id="38577-118">Scegliere **Avanti**e quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="38577-118">Click **Next**, and then click **Finish**.</span></span>  
  
### <a name="to-bind-the-control-to-the-bindingsource"></a><span data-ttu-id="38577-119">Per associare il controllo a BindingSource</span><span class="sxs-lookup"><span data-stu-id="38577-119">To bind the control to the BindingSource</span></span>  
  
1.  <span data-ttu-id="38577-120">Aggiungere un tipo <xref:System.Windows.Forms.TextBox> al form.</span><span class="sxs-lookup"><span data-stu-id="38577-120">Add a <xref:System.Windows.Forms.TextBox> to the form.</span></span>  
  
2.  <span data-ttu-id="38577-121">Nella finestra **Proprietà** espandere il nodo **(DataBindings)** .</span><span class="sxs-lookup"><span data-stu-id="38577-121">In the **Properties** window, expand the **(DataBindings)** node.</span></span>  
  
3.  <span data-ttu-id="38577-122">Fare clic sulla freccia accanto al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="38577-122">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
4.  <span data-ttu-id="38577-123">Nel **Editor di tipo dell'interfaccia utente DataSource**, espandere il nodo per il <xref:System.Windows.Forms.BindingSource> aggiunto in precedenza e selezionare la proprietà del tipo associato che si desidera associare al <xref:System.Windows.Forms.TextBox.Text%2A> proprietà del <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="38577-123">In the **DataSource UI Type Editor**, expand the node for the <xref:System.Windows.Forms.BindingSource> added previously, and select the property of the bound type you want to bind to the <xref:System.Windows.Forms.TextBox.Text%2A> property of the <xref:System.Windows.Forms.TextBox>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38577-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38577-124">See Also</span></span>  
 [<span data-ttu-id="38577-125">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="38577-125">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="38577-126">Procedura: Associare un controllo di Windows Form a un tipo</span><span class="sxs-lookup"><span data-stu-id="38577-126">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [<span data-ttu-id="38577-127">Associare controlli ai dati in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="38577-127">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
