---
title: 'Procedura dettagliata: Creazione di oggetti COM con Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 97e917d568b31860979e54598350d1ae7a6fdb25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331897"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="318b3-102">Procedura dettagliata: Creazione di oggetti COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="318b3-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="318b3-103">Quando si creano nuove applicazioni o componenti, è consigliabile creare gli assembly di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="318b3-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="318b3-104">Tuttavia, Visual Basic semplifica per esporre un componente di .NET Framework a COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="318b3-105">In questo modo è possibile fornire nuovi componenti per la suite di applicazioni precedenti che richiedono i componenti COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="318b3-106">Questa procedura dettagliata illustra come usare Visual Basic per esporre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] oggetti come oggetti COM, con e senza il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-106">This walkthrough demonstrates how to use Visual Basic to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="318b3-107">Per esporre gli oggetti COM in modo semplice consiste nell'usare il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="318b3-108">Il modello di classe COM consente di creare una nuova classe e quindi Configura il progetto per generare il livello di classe e l'interoperabilità come un oggetto COM e registrarla con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="318b3-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="318b3-109">Sebbene sia possibile esporre anche una classe creata in Visual Basic come oggetto COM per codice non gestito da usare, non è un vero oggetto COM e non può essere utilizzato da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="318b3-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="318b3-110">Per altre informazioni, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="318b3-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="318b3-111">Per creare un oggetto COM usando il modello di classe COM</span><span class="sxs-lookup"><span data-stu-id="318b3-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="318b3-112">Aprire un nuovo progetto di applicazione di Windows dal **File** menu, fare clic su **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="318b3-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="318b3-113">Nel **nuovo progetto** nella finestra di dialogo il **tipi di progetto** campo, verificare che Windows sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="318b3-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="318b3-114">Selezionare **libreria di classi** dalle **modelli** elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="318b3-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="318b3-115">Viene visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="318b3-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="318b3-116">Selezionare **Aggiungi nuovo elemento** dalle **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="318b3-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="318b3-117">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="318b3-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="318b3-118">Selezionare **classe COM** dalle **modelli** elenco e quindi fare clic su **Add**.</span><span class="sxs-lookup"><span data-stu-id="318b3-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="318b3-119">Visual Basic consente di aggiungere una nuova classe e configura il nuovo progetto per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="318b3-120">Aggiungere il codice, ad esempio proprietà, metodi ed eventi della classe COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="318b3-121">Selezionare **Compila ClassLibrary1** dalle **compilazione** menu.</span><span class="sxs-lookup"><span data-stu-id="318b3-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="318b3-122">Visual Basic compilato l'assembly e registra l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="318b3-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="318b3-123">Creazione di oggetti COM senza il modello classe COM</span><span class="sxs-lookup"><span data-stu-id="318b3-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="318b3-124">È anche possibile creare una classe COM anziché manualmente usando il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="318b3-125">Questa procedura è utile quando si lavora dalla riga di comando o se si desidera maggiore controllo sul modo in cui sono definiti gli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="318b3-126">Per configurare il progetto per generare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="318b3-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="318b3-127">Aprire un nuovo progetto di applicazione di Windows dal **File** menu, fare clic su **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="318b3-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="318b3-128">Nel **nuovo progetto** nella finestra di dialogo il **tipi di progetto** campo, verificare che Windows sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="318b3-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="318b3-129">Selezionare **libreria di classi** dalle **modelli** elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="318b3-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="318b3-130">Viene visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="318b3-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="318b3-131">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="318b3-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="318b3-132">Il **Progettazione progetti** viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="318b3-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="318b3-133">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="318b3-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="318b3-134">Selezionare il **Registra per interoperabilità COM** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="318b3-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="318b3-135">Per configurare il codice nella classe per creare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="318b3-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="318b3-136">Nelle **Esplora soluzioni**, fare doppio clic su **Class1.vb** per visualizzare il relativo codice.</span><span class="sxs-lookup"><span data-stu-id="318b3-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="318b3-137">Rinominare la classe come `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="318b3-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="318b3-138">Aggiungere le costanti seguenti al `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="318b3-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="318b3-139">Si archivierà le costanti di identificatore univoco globale (GUID) che sono necessari affinché gli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="318b3-140">Scegliere **Crea GUID** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="318b3-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="318b3-141">Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="318b3-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="318b3-142">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="318b3-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="318b3-143">Sostituire la stringa vuota per il `ClassId` con il GUID, rimuovendo le iniziali e finali dalle parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="318b3-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="318b3-144">Ad esempio, se il GUID fornito da Guidgen è `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` quindi il codice deve apparire come segue.</span><span class="sxs-lookup"><span data-stu-id="318b3-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="318b3-145">Ripetere i passaggi precedenti per il `InterfaceId` e `EventsId` costanti, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="318b3-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    >  <span data-ttu-id="318b3-146">Assicurarsi che i GUID siano nuovi e univoci. in caso contrario, il componente COM potrebbero essere in conflitto con altri componenti COM.</span><span class="sxs-lookup"><span data-stu-id="318b3-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="318b3-147">Aggiungere il `ComClass` dell'attributo `ComClass1`, che specifica il GUID per l'ID della classe, l'ID di interfaccia e gli ID di eventi come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="318b3-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="318b3-148">Classi COM devono avere un costruttore `Public Sub New()` costruttore o classe non registrerà correttamente.</span><span class="sxs-lookup"><span data-stu-id="318b3-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="318b3-149">Aggiungere un costruttore senza parametri alla classe:</span><span class="sxs-lookup"><span data-stu-id="318b3-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="318b3-150">Aggiungere le proprietà, metodi ed eventi alla classe, che termina con un `End Class` istruzione.</span><span class="sxs-lookup"><span data-stu-id="318b3-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="318b3-151">Selezionare **Compila soluzione** dalle **compilazione** menu.</span><span class="sxs-lookup"><span data-stu-id="318b3-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="318b3-152">Visual Basic compilato l'assembly e registra l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="318b3-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="318b3-153">Gli oggetti COM che è generare con Visual Basic non possono essere utilizzati da altre applicazioni Visual Basic perché non sono oggetti COM true.</span><span class="sxs-lookup"><span data-stu-id="318b3-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="318b3-154">I tentativi di aggiungere i riferimenti a tali oggetti COM genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="318b3-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="318b3-155">Per informazioni dettagliate, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="318b3-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318b3-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="318b3-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="318b3-157">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="318b3-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="318b3-158">Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="318b3-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="318b3-159">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="318b3-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
- [<span data-ttu-id="318b3-160">Interoperabilità COM nelle applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="318b3-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="318b3-161">Risoluzione dei problemi relativi all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="318b3-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
