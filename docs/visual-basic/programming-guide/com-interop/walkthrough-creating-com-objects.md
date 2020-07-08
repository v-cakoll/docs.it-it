---
title: 'Procedura dettagliata: Creazione di oggetti COM'
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
ms.openlocfilehash: 6ff23f73af384a1440bcebd4b6bac21714e01756
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051480"
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="7920e-102">Procedura dettagliata: creazione di oggetti COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7920e-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="7920e-103">Quando si creano nuovi componenti o applicazioni, è consigliabile creare .NET Framework assembly.</span><span class="sxs-lookup"><span data-stu-id="7920e-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="7920e-104">Tuttavia, Visual Basic facilita anche l'esposizione di un componente .NET Framework a COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-104">However, Visual Basic also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="7920e-105">In questo modo è possibile fornire nuovi componenti per i gruppi di applicazioni precedenti che richiedono componenti COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="7920e-106">In questa procedura dettagliata viene illustrato come utilizzare Visual Basic per esporre .NET Framework oggetti come oggetti COM, sia con sia senza il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-106">This walkthrough demonstrates how to use Visual Basic to expose .NET Framework objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="7920e-107">Il modo più semplice per esporre oggetti COM consiste nell'usare il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="7920e-108">Questo modello crea una nuova classe, quindi configura il progetto per generare la classe con un livello di interoperabilità come oggetto COM e la registra con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7920e-108">This template creates a new class, then configures your project to generate the class with an interoperability layer as a COM object, and register it with the operating system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7920e-109">Sebbene sia anche possibile esporre una classe creata in Visual Basic come oggetto COM per il codice non gestito da usare, non è un vero oggetto COM e non può essere usata da Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7920e-109">Although you can also expose a class created in Visual Basic as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by Visual Basic.</span></span> <span data-ttu-id="7920e-110">Per ulteriori informazioni, vedere [interoperabilità com nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="7920e-110">For more information, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="7920e-111">Per creare un oggetto COM utilizzando il modello di classe COM</span><span class="sxs-lookup"><span data-stu-id="7920e-111">To create a COM object by using the COM class template</span></span>  
  
1. <span data-ttu-id="7920e-112">Aprire un nuovo progetto di applicazione Windows dal menu **file** facendo clic su **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="7920e-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2. <span data-ttu-id="7920e-113">Nella finestra di dialogo **nuovo progetto** , sotto il campo **Tipi progetto** , verificare che sia selezionata l'opzione Windows.</span><span class="sxs-lookup"><span data-stu-id="7920e-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="7920e-114">Selezionare **libreria di classi** dall'elenco **modelli** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7920e-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="7920e-115">Verrà visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="7920e-115">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="7920e-116">Scegliere **Aggiungi nuovo elemento** dal menu **progetto** .</span><span class="sxs-lookup"><span data-stu-id="7920e-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="7920e-117">La finestra di dialogo **Aggiungi nuovo elemento** viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="7920e-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4. <span data-ttu-id="7920e-118">Selezionare **classe com** dall'elenco **modelli** , quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7920e-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> <span data-ttu-id="7920e-119">Visual Basic aggiunge una nuova classe e configura il nuovo progetto per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-119">Visual Basic adds a new class and configures the new project for COM interop.</span></span>  
  
5. <span data-ttu-id="7920e-120">Aggiungere codice come proprietà, metodi ed eventi alla classe COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6. <span data-ttu-id="7920e-121">Scegliere **Compila ClassLibrary1** dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="7920e-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> <span data-ttu-id="7920e-122">Visual Basic compila l'assembly e registra l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7920e-122">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="7920e-123">Creazione di oggetti COM senza il modello di classe COM</span><span class="sxs-lookup"><span data-stu-id="7920e-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="7920e-124">È inoltre possibile creare manualmente una classe COM anziché utilizzare il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="7920e-125">Questa procedura è utile quando si utilizza la riga di comando o quando si desidera un maggiore controllo sulla modalità di definizione degli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="7920e-126">Per configurare il progetto per generare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="7920e-126">To set up your project to generate a COM object</span></span>  
  
1. <span data-ttu-id="7920e-127">Aprire un nuovo progetto di applicazione Windows dal menu **file** facendo clic su **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="7920e-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2. <span data-ttu-id="7920e-128">Nella finestra di dialogo **nuovo progetto** , sotto il campo **Tipi progetto** , verificare che sia selezionata l'opzione Windows.</span><span class="sxs-lookup"><span data-stu-id="7920e-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="7920e-129">Selezionare **libreria di classi** dall'elenco **modelli** , quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7920e-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="7920e-130">Verrà visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="7920e-130">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="7920e-131">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="7920e-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="7920e-132">Verrà visualizzato **Progettazione progetti** .</span><span class="sxs-lookup"><span data-stu-id="7920e-132">The **Project Designer** is displayed.</span></span>  
  
4. <span data-ttu-id="7920e-133">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="7920e-133">Click the **Compile** tab.</span></span>  
  
5. <span data-ttu-id="7920e-134">Selezionare la casella **di controllo registra per interoperabilità COM** .</span><span class="sxs-lookup"><span data-stu-id="7920e-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="7920e-135">Per configurare il codice nella classe per creare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="7920e-135">To set up the code in your class to create a COM object</span></span>  
  
1. <span data-ttu-id="7920e-136">In **Esplora soluzioni**fare doppio clic su **Class1. vb** per visualizzarne il codice.</span><span class="sxs-lookup"><span data-stu-id="7920e-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2. <span data-ttu-id="7920e-137">Rinominare la classe in `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="7920e-137">Rename the class to `ComClass1`.</span></span>  
  
3. <span data-ttu-id="7920e-138">Aggiungere le costanti seguenti a `ComClass1` .</span><span class="sxs-lookup"><span data-stu-id="7920e-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="7920e-139">Verranno archiviate le costanti identificatore univoco globale (GUID) che devono essere presenti negli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="7920e-140">Scegliere **Crea GUID** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="7920e-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="7920e-141">Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="7920e-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="7920e-142">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="7920e-142">Click **Exit**.</span></span>  
  
5. <span data-ttu-id="7920e-143">Sostituire la stringa vuota per `ClassId` con il GUID, rimuovendo le parentesi graffe iniziali e finali.</span><span class="sxs-lookup"><span data-stu-id="7920e-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="7920e-144">Se, ad esempio, il GUID fornito da GUIDGEN è `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` , il codice dovrebbe essere simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="7920e-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#3)]  
  
6. <span data-ttu-id="7920e-145">Ripetere i passaggi precedenti per le `InterfaceId` `EventsId` costanti e, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7920e-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#4)]  
  
    > [!NOTE]
    > <span data-ttu-id="7920e-146">Verificare che i GUID siano nuovi e univoci. in caso contrario, il componente COM potrebbe essere in conflitto con altri componenti COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7. <span data-ttu-id="7920e-147">Aggiungere l' `ComClass` attributo a `ComClass1` , specificando i GUID per l'ID di classe, l'ID di interfaccia e l'ID degli eventi come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="7920e-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#5)]  
  
8. <span data-ttu-id="7920e-148">Le classi COM devono avere un `Public Sub New()` costruttore senza parametri o la classe non sarà registrata correttamente.</span><span class="sxs-lookup"><span data-stu-id="7920e-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="7920e-149">Aggiungere un costruttore senza parametri alla classe:</span><span class="sxs-lookup"><span data-stu-id="7920e-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#6)]  
  
9. <span data-ttu-id="7920e-150">Aggiungere proprietà, metodi ed eventi alla classe, terminando con un' `End Class` istruzione.</span><span class="sxs-lookup"><span data-stu-id="7920e-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="7920e-151">Scegliere **Compila soluzione** dal menu **Compila** .</span><span class="sxs-lookup"><span data-stu-id="7920e-151">Select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="7920e-152">Visual Basic compila l'assembly e registra l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7920e-152">Visual Basic builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7920e-153">Gli oggetti COM generati con Visual Basic non possono essere utilizzati da altre applicazioni Visual Basic perché non sono veri oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="7920e-153">The COM objects you generate with Visual Basic cannot be used by other Visual Basic applications because they are not true COM objects.</span></span> <span data-ttu-id="7920e-154">I tentativi di aggiungere riferimenti a tali oggetti COM genereranno un errore.</span><span class="sxs-lookup"><span data-stu-id="7920e-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="7920e-155">Per informazioni dettagliate, vedere [interoperabilità com nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="7920e-155">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7920e-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7920e-156">See also</span></span>

- <xref:Microsoft.VisualBasic.ComClassAttribute>
- [<span data-ttu-id="7920e-157">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="7920e-157">COM Interop</span></span>](index.md)
- [<span data-ttu-id="7920e-158">Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="7920e-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](walkthrough-implementing-inheritance-with-com-objects.md)
- [<span data-ttu-id="7920e-159">#Region (direttiva)</span><span class="sxs-lookup"><span data-stu-id="7920e-159">#Region Directive</span></span>](../../language-reference/directives/region-directive.md)
- [<span data-ttu-id="7920e-160">Interoperabilità COM nelle applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7920e-160">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="7920e-161">Risoluzione dei problemi relativi all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="7920e-161">Troubleshooting Interoperability</span></span>](troubleshooting-interoperability.md)
