---
title: 'Procedura dettagliata: Creazione di oggetti COM con Visual Basic | Documenti di Microsoft'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- COM interop, creating COM objects
- COM objects, creating
- COM interop, walkthroughs
- object creation, COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 859a8fc7440eecc0cadbfa8ea236dad7cae99247
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="0755a-102">Procedura dettagliata: creazione di oggetti COM con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0755a-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="0755a-103">Quando si creano nuove applicazioni o componenti, è consigliabile creare gli assembly di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0755a-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="0755a-104">Tuttavia, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] rende facile per esporre un componente di .NET Framework a COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-104">However, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="0755a-105">In questo modo è possibile fornire nuovi componenti per la suite di applicazioni precedenti che richiedono i componenti COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="0755a-106">Questa procedura dettagliata viene illustrato come utilizzare [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] per esporre [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] oggetti come oggetti COM, con e senza il modello di classe COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-106">This walkthrough demonstrates how to use [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to expose [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="0755a-107">Il modo più semplice per esporre gli oggetti COM è tramite il modello classe COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="0755a-108">Il modello di classe COM crea una nuova classe e quindi Configura il progetto per generare il livello di classe e l'interoperabilità come oggetto COM e registrarlo con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0755a-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0755a-109">Sebbene sia possibile esporre anche una classe creata [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] come oggetto COM per codice non gestito da utilizzare, non è un vero oggetto COM e non può essere utilizzato da [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="0755a-109">Although you can also expose a class created in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="0755a-110">Per ulteriori informazioni, vedere [l'interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0755a-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="0755a-111">Per creare un oggetto COM utilizzando il modello classe COM</span><span class="sxs-lookup"><span data-stu-id="0755a-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="0755a-112">Aprire un nuovo progetto applicazione Windows dal **File** menu facendo **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="0755a-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="0755a-113">Nel **nuovo progetto** della finestra di dialogo di **tipi di progetto** campo, verificare che Windows sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="0755a-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="0755a-114">Selezionare **libreria di classi** dal **modelli** elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0755a-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="0755a-115">Viene visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="0755a-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="0755a-116">Selezionare **Aggiungi nuovo elemento** dal **progetto** menu.</span><span class="sxs-lookup"><span data-stu-id="0755a-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="0755a-117">Il **Aggiungi nuovo elemento** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="0755a-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="0755a-118">Selezionare **classe COM** dal **modelli** elenco e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="0755a-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0755a-119">Aggiunge una nuova classe e configura il nuovo progetto per l'interoperabilità COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-119"> adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="0755a-120">Aggiungere il codice, ad esempio proprietà, metodi ed eventi della classe COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="0755a-121">Selezionare **Compila ClassLibrary1** dal **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="0755a-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0755a-122">compilare l'assembly e registrare l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0755a-122"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="0755a-123">Creazione di oggetti COM senza il modello classe COM</span><span class="sxs-lookup"><span data-stu-id="0755a-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="0755a-124">È inoltre possibile creare una classe COM manualmente invece di utilizzare il modello classe COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="0755a-125">Questa procedura è utile quando si utilizza dalla riga di comando o quando si desidera maggiore controllo sul modo in cui sono definiti oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="0755a-126">Per configurare il progetto per generare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="0755a-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="0755a-127">Aprire un nuovo progetto applicazione Windows dal **File** menu facendo **NewProject**.</span><span class="sxs-lookup"><span data-stu-id="0755a-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="0755a-128">Nel **nuovo progetto** della finestra di dialogo di **tipi di progetto** campo, verificare che Windows sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="0755a-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="0755a-129">Selezionare **libreria di classi** dal **modelli** elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0755a-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="0755a-130">Viene visualizzato il nuovo progetto.</span><span class="sxs-lookup"><span data-stu-id="0755a-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="0755a-131">In **Esplora**, mouse sul progetto e quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0755a-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="0755a-132">Il **progettazione** viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="0755a-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="0755a-133">Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="0755a-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="0755a-134">Selezionare il **Registra per interoperabilità COM** casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="0755a-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="0755a-135">Per impostare il codice nella classe per creare un oggetto COM</span><span class="sxs-lookup"><span data-stu-id="0755a-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="0755a-136">In **Esplora**, fare doppio clic su **Class1. vb** per visualizzare il relativo codice.</span><span class="sxs-lookup"><span data-stu-id="0755a-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="0755a-137">Rinominare la classe come `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="0755a-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="0755a-138">Aggiungere le seguenti costanti per `ComClass1`.</span><span class="sxs-lookup"><span data-stu-id="0755a-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="0755a-139">Memorizzano le costanti di identificatore univoco globale (GUID) che sono necessari per disporre gli oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     <span data-ttu-id="0755a-140">[!code-vb[VbVbalrInterop n.&2;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0755a-140">[!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span></span>  
  
4.  <span data-ttu-id="0755a-141">Nel **strumenti** menu, fare clic su **crea Guid**.</span><span class="sxs-lookup"><span data-stu-id="0755a-141">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="0755a-142">Nel **Crea GUID** la finestra di dialogo, fare clic su **il formato del Registro di sistema** e quindi fare clic su **copia**.</span><span class="sxs-lookup"><span data-stu-id="0755a-142">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="0755a-143">Fare clic su **Esci**.</span><span class="sxs-lookup"><span data-stu-id="0755a-143">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="0755a-144">Sostituire la stringa vuota per il `ClassId` con il GUID, rimuovendo le iniziali e finali parentesi graffe.</span><span class="sxs-lookup"><span data-stu-id="0755a-144">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="0755a-145">Ad esempio, se il GUID fornito da Guidgen è `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` quindi il codice dovrebbe risultare come segue.</span><span class="sxs-lookup"><span data-stu-id="0755a-145">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     <span data-ttu-id="0755a-146">[!code-vb[VbVbalrInterop n.&3;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0755a-146">[!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span></span>  
  
6.  <span data-ttu-id="0755a-147">Ripetere i passaggi precedenti per il `InterfaceId` e `EventsId` costanti, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="0755a-147">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     <span data-ttu-id="0755a-148">[!code-vb[VbVbalrInterop n.&4;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0755a-148">[!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0755a-149">Assicurarsi che i GUID siano nuovi e univoci. in caso contrario, il componente COM potrebbe entrare in conflitto con altri componenti COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-149">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="0755a-150">Aggiungere il `ComClass` attributo `ComClass1`, specificando i GUID per l'ID di classe, l'ID di interfaccia e ID degli eventi, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0755a-150">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     <span data-ttu-id="0755a-151">[!code-vb[VbVbalrInterop n.&5;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="0755a-151">[!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span></span>  
  
8.  <span data-ttu-id="0755a-152">Classi COM devono avere un costruttore `Public Sub New()` costruttore o la classe non registrare correttamente.</span><span class="sxs-lookup"><span data-stu-id="0755a-152">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="0755a-153">Aggiungere un costruttore senza parametri alla classe:</span><span class="sxs-lookup"><span data-stu-id="0755a-153">Add a parameterless constructor to the class:</span></span>  
  
     <span data-ttu-id="0755a-154">[!code-vb[6 VbVbalrInterop](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="0755a-154">[!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span></span>  
  
9. <span data-ttu-id="0755a-155">Aggiungere proprietà, metodi ed eventi alla classe, terminando con un `End Class` istruzione.</span><span class="sxs-lookup"><span data-stu-id="0755a-155">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="0755a-156">Selezionare **Compila soluzione** dal **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="0755a-156">Select **Build Solution** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="0755a-157">compilare l'assembly e registrare l'oggetto COM con il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="0755a-157"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0755a-158">Gli oggetti COM è generare con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] non può essere utilizzato da altri [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] applicazioni perché non sono veri oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="0755a-158">The COM objects you generate with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot be used by other [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] applications because they are not true COM objects.</span></span> <span data-ttu-id="0755a-159">Tenta di aggiungere riferimenti a tali oggetti COM genererà un errore.</span><span class="sxs-lookup"><span data-stu-id="0755a-159">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="0755a-160">Per informazioni dettagliate, vedere [l'interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="0755a-160">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0755a-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0755a-161">See Also</span></span>  
 <span data-ttu-id="0755a-162"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="0755a-162"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>   
<span data-ttu-id="0755a-163"> [Interoperabilità COM](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="0755a-163"> [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="0755a-164"> [Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="0755a-164"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="0755a-165"> [#Region (direttiva)](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="0755a-165"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="0755a-166"> [Interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="0755a-166"> [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="0755a-167"> [Risoluzione dei problemi relativi all'interoperabilità](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="0755a-167"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span></span>
