---
title: 'Procedura dettagliata: creazione di oggetti COM con Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff7d3868a2e3ddaba06ebc6f98c8eacfc7299366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="09c83-102">Procedura dettagliata: creazione di oggetti COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09c83-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="09c83-103">Quando si creano nuove applicazioni o componenti, è consigliabile creare gli assembly di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="09c83-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="09c83-104">Tuttavia, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] consente inoltre di esporre un componente di .NET Framework a COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-104">However, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="09c83-105">In questo modo è possibile fornire nuovi componenti per la suite di applicazioni precedenti che richiedono i componenti COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="09c83-106">Questa procedura dettagliata viene illustrato come utilizzare [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] per esporre [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] oggetti come oggetti COM, con e senza il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-106">This walkthrough demonstrates how to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="09c83-107">Il modo più semplice per esporre gli oggetti COM è tramite il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="09c83-108">Il modello di classe COM crea una nuova classe e quindi Configura il progetto per generare il livello di classe e l'interoperabilità come un oggetto COM e registrarlo con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="09c83-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09c83-109">Sebbene sia possibile esporre anche una classe creata [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] come un oggetto COM per usare il codice non gestito, non è un oggetto COM true e non può essere utilizzato da [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09c83-109">Although you can also expose a class created in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="09c83-110">Per ulteriori informazioni, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="09c83-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="09c83-111">Per creare un oggetto COM con modello di classe COM</span><span class="sxs-lookup"><span data-stu-id="09c83-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="09c83-112">Aprire un nuovo progetto applicazione Windows dal **File** menu facendo **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="09c83-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="09c83-113">Nel **nuovo progetto** nella finestra di dialogo di **tipi di progetto** campo, verificare che Windows sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="09c83-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="09c83-114">Selezionare **libreria di classi** dal **modelli** elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="09c83-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="09c83-115">Viene visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="09c83-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="09c83-116">Selezionare **Aggiungi nuovo elemento** dal **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="09c83-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="09c83-117">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="09c83-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="09c83-118">Selezionare **classe COM** dal **modelli** elenco e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="09c83-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="09c83-119">Aggiunge una nuova classe e configura il nuovo progetto per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-119"> adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="09c83-120">Aggiungere il codice, ad esempio proprietà, metodi ed eventi nella classe COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="09c83-121">Selezionare **Compila ClassLibrary1** dal **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="09c83-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="09c83-122">Compila l'assembly e registra l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="09c83-122"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="09c83-123">Creazione di oggetti COM senza il modello di classe COM</span><span class="sxs-lookup"><span data-stu-id="09c83-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="09c83-124">È anche possibile creare una classe COM manualmente, anziché utilizzare il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="09c83-125">Questa procedura è utile quando si utilizza dalla riga di comando oppure quando si desidera maggiore controllo sul modo in cui sono definiti oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="09c83-126">Per impostare il progetto per generare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="09c83-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="09c83-127">Aprire un nuovo progetto applicazione Windows dal **File** menu facendo **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="09c83-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="09c83-128">Nel **nuovo progetto** nella finestra di dialogo di **tipi di progetto** campo, verificare che Windows sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="09c83-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="09c83-129">Selezionare **libreria di classi** dal **modelli** elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="09c83-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="09c83-130">Viene visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="09c83-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="09c83-131">In **Esplora**mouse sul progetto e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="09c83-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="09c83-132">Il **progettazione** viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="09c83-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="09c83-133">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="09c83-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="09c83-134">Selezionare il **Registra per interoperabilità COM** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="09c83-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="09c83-135">Per impostare il codice nella classe per creare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="09c83-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="09c83-136">In **Esplora**, fare doppio clic su **Class1. vb** per visualizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="09c83-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="09c83-137">Rinominare la classe come `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="09c83-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="09c83-138">Aggiungere le seguenti costanti per `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="09c83-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="09c83-139">Archiviano le costanti di identificatore univoco globale (GUID) che devono disporre gli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  <span data-ttu-id="09c83-140">Scegliere **Crea GUID** dal menu **Strumenti**.</span><span class="sxs-lookup"><span data-stu-id="09c83-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="09c83-141">Nella finestra di dialogo **Crea GUID** fare clic su **Formato del Registro di sistema** e quindi fare clic su **Copia**.</span><span class="sxs-lookup"><span data-stu-id="09c83-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="09c83-142">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="09c83-142">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="09c83-143">Sostituire la stringa vuota per il `ClassId` con il GUID, rimuovendo le iniziali e finali parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="09c83-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="09c83-144">Ad esempio, se il GUID fornito da Guidgen è `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` quindi il codice deve essere visualizzata come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="09c83-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  <span data-ttu-id="09c83-145">Ripetere i passaggi precedenti per il `InterfaceId` e `EventsId` costanti, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="09c83-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="09c83-146">Assicurarsi che i GUID siano nuovi e univoci. in caso contrario, il componente COM potrebbe entrare in conflitto con altri componenti COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="09c83-147">Aggiungere il `ComClass` attributo `ComClass1`, specificando i GUID per l'ID di classe, l'ID di interfaccia e ID degli eventi, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="09c83-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  <span data-ttu-id="09c83-148">Classi COM devono avere un costruttore `Public Sub New()` costruttore o la classe non registrare correttamente.</span><span class="sxs-lookup"><span data-stu-id="09c83-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="09c83-149">Aggiungere un costruttore senza parametri per la classe:</span><span class="sxs-lookup"><span data-stu-id="09c83-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. <span data-ttu-id="09c83-150">Aggiungere una proprietà, metodi ed eventi alla classe, che termina con un `End Class` istruzione.</span><span class="sxs-lookup"><span data-stu-id="09c83-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="09c83-151">Selezionare **Compila soluzione** dal **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="09c83-151">Select **Build Solution** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="09c83-152">Compila l'assembly e registra l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="09c83-152"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="09c83-153">Gli oggetti COM è generare con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] non può essere utilizzato da altri [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] applicazioni perché non sono veri oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="09c83-153">The COM objects you generate with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot be used by other [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] applications because they are not true COM objects.</span></span> <span data-ttu-id="09c83-154">Tenta di aggiungere riferimenti a tali oggetti COM genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="09c83-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="09c83-155">Per informazioni dettagliate, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="09c83-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c83-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09c83-156">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [<span data-ttu-id="09c83-157">Interoperabilità COM</span><span class="sxs-lookup"><span data-stu-id="09c83-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="09c83-158">Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM</span><span class="sxs-lookup"><span data-stu-id="09c83-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="09c83-159">Direttiva #Region</span><span class="sxs-lookup"><span data-stu-id="09c83-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="09c83-160">Interoperabilità COM nelle applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="09c83-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="09c83-161">Risoluzione dei problemi relativi all'interoperabilità</span><span class="sxs-lookup"><span data-stu-id="09c83-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)
