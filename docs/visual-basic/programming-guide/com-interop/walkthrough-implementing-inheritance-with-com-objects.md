---
title: "Procedura dettagliata: implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8d6906c58431a0e844e8f430ade10ae819e77ff2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="6939f-102">Procedura dettagliata: implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6939f-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="6939f-103">È possibile derivare classi Visual Basic da `Public` classi di oggetti COM, anche quelli creati nelle versioni precedenti di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6939f-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="6939f-104">Le proprietà e metodi delle classi ereditate da oggetti COM possono essere sottoposto a override o sottoposti a overload solo come proprietà e metodi di qualsiasi altra classe di base possono essere sottoposto a override o di overload.</span><span class="sxs-lookup"><span data-stu-id="6939f-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="6939f-105">Ereditarietà dagli oggetti COM è utile quando si dispone di una libreria di classe esistente che non si desidera ricompilare.</span><span class="sxs-lookup"><span data-stu-id="6939f-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="6939f-106">La procedura seguente viene illustrato come utilizzare Visual Basic 6.0 per creare un oggetto COM che contiene una classe e quindi utilizzarlo come classe base.</span><span class="sxs-lookup"><span data-stu-id="6939f-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="6939f-107">Per compilare l'oggetto COM che è utilizzato in questa procedura dettagliata</span><span class="sxs-lookup"><span data-stu-id="6939f-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="6939f-108">In Visual Basic 6.0, aprire un nuovo progetto ActiveX DLL.</span><span class="sxs-lookup"><span data-stu-id="6939f-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="6939f-109">Un progetto denominato `Project1` viene creato.</span><span class="sxs-lookup"><span data-stu-id="6939f-109">A project named `Project1` is created.</span></span> <span data-ttu-id="6939f-110">Dispone di una classe denominata `Class1`.</span><span class="sxs-lookup"><span data-stu-id="6939f-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="6939f-111">Nel **Esplora progetti**, fare doppio clic su **Project1**, quindi fare clic su **proprietà Project1**.</span><span class="sxs-lookup"><span data-stu-id="6939f-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="6939f-112">Il **le proprietà del progetto** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6939f-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="6939f-113">Nel **generale** scheda della finestra il **le proprietà del progetto** finestra di dialogo, modificare il nome del progetto digitando `ComObject1` nel **nome progetto** campo.</span><span class="sxs-lookup"><span data-stu-id="6939f-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="6939f-114">Nel **Esplora progetti**, fare doppio clic su `Class1`, quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="6939f-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="6939f-115">Il **proprietà** verrà visualizzata la finestra per la classe.</span><span class="sxs-lookup"><span data-stu-id="6939f-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="6939f-116">Modifica il `Name` proprietà `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="6939f-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="6939f-117">Nel **Esplora progetti**, fare doppio clic su `MathFunctions`, quindi fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="6939f-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="6939f-118">Il **Editor di codice** viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="6939f-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="6939f-119">Aggiungere una variabile locale per contenere il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="6939f-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="6939f-120">Aggiungere proprietà `Let` e proprietà `Get` le routine della proprietà:</span><span class="sxs-lookup"><span data-stu-id="6939f-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
    ```  
    Public Property Let Prop1(ByVal vData As Integer)  
       'Used when assigning a value to the property.  
       mvarProp1 = vData  
    End Property  
    Public Property Get Prop1() As Integer  
       'Used when retrieving a property's value.  
       Prop1 = mvarProp1  
    End Property  
    ```  
  
9. <span data-ttu-id="6939f-121">Aggiungere una funzione:</span><span class="sxs-lookup"><span data-stu-id="6939f-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="6939f-122">Creare e registrare l'oggetto COM, fare clic su **Crea ComObject1. dll** sul **File** menu.</span><span class="sxs-lookup"><span data-stu-id="6939f-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6939f-123">Sebbene sia possibile esporre anche una classe creata con [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] come oggetto COM non è un oggetto COM true e non può essere utilizzato in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="6939f-123">Although you can also expose a class created with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="6939f-124">Per informazioni dettagliate, vedere [interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="6939f-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="6939f-125">Assembly di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="6939f-125">Interop Assemblies</span></span>  
 <span data-ttu-id="6939f-126">Nella procedura seguente, si creerà un assembly di interoperabilità, che funge da ponte tra il codice non gestito (ad esempio un oggetto COM) e il codice gestito [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] utilizza.</span><span class="sxs-lookup"><span data-stu-id="6939f-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] uses.</span></span> <span data-ttu-id="6939f-127">L'assembly di interoperabilità che [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] crea gestisce molti dei dettagli relativi all'utilizzo con COM oggetti, ad esempio *il marshalling di interoperabilità*, il processo di parametri di creazione di pacchetti e i valori restituiti in dati equivalente tipi come su cui spostarsi e oggetti da COM.</span><span class="sxs-lookup"><span data-stu-id="6939f-127">The interop assembly that [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="6939f-128">Il riferimento nel [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] punti dell'applicazione dell'assembly di interoperabilità, non all'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="6939f-128">The reference in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="6939f-129">Per utilizzare un oggetto COM con Visual Basic 2005 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="6939f-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="6939f-130">Aprire un nuovo progetto Applicazione Windows in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6939f-130">Open a new [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="6939f-131">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="6939f-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="6939f-132">Il **Aggiungi riferimento** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="6939f-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="6939f-133">Nel **COM** scheda, fare doppio clic su `ComObject1` nel **nome componente** elenco e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="6939f-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="6939f-134">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6939f-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="6939f-135">Verrà visualizzata la finestra di dialogo **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="6939f-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="6939f-136">Nel **modelli** riquadro, fare clic su **classe**.</span><span class="sxs-lookup"><span data-stu-id="6939f-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="6939f-137">Il nome di file predefinito, `Class1.vb`, viene visualizzato nel **nome** campo.</span><span class="sxs-lookup"><span data-stu-id="6939f-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="6939f-138">Modificare questo campo MathClass e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6939f-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="6939f-139">Verrà creata una classe denominata `MathClass`e verrà visualizzato il codice.</span><span class="sxs-lookup"><span data-stu-id="6939f-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="6939f-140">Aggiungere il codice seguente all'inizio del `MathClass` per ereditare dalla classe COM.</span><span class="sxs-lookup"><span data-stu-id="6939f-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     [!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]  
  
7.  <span data-ttu-id="6939f-141">Eseguire l'overload del metodo pubblico della classe di base aggiungendo il seguente codice al `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="6939f-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]  
  
8.  <span data-ttu-id="6939f-142">Estendere la classe ereditata aggiungendo il seguente codice al `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="6939f-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     [!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]  
  
 <span data-ttu-id="6939f-143">La nuova classe eredita le proprietà della classe di base dell'oggetto COM, un metodo di overload e definisce un nuovo metodo per estendere la classe.</span><span class="sxs-lookup"><span data-stu-id="6939f-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="6939f-144">Per testare la classe ereditata</span><span class="sxs-lookup"><span data-stu-id="6939f-144">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="6939f-145">Aggiungere un pulsante al form di avvio e quindi fare doppio clic per visualizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="6939f-145">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="6939f-146">Il pulsante `Click` routine del gestore eventi, aggiungere il codice seguente per creare un'istanza di `MathClass` e chiamare i metodi di overload:</span><span class="sxs-lookup"><span data-stu-id="6939f-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     [!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]  
  
3.  <span data-ttu-id="6939f-147">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="6939f-147">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="6939f-148">Quando si fa clic sul pulsante nel form, il `AddNumbers` metodo viene chiamato con `Short` numeri, tipo di dati e [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sceglie il metodo appropriato dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="6939f-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] chooses the appropriate method from the base class.</span></span> <span data-ttu-id="6939f-149">La seconda chiamata a `AddNumbers` viene indirizzata al metodo di overload da `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="6939f-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="6939f-150">La terza chiamata richiama il `SubtractNumbers` metodo, che estende la classe.</span><span class="sxs-lookup"><span data-stu-id="6939f-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="6939f-151">La proprietà nella classe base è impostata, e viene visualizzato il valore.</span><span class="sxs-lookup"><span data-stu-id="6939f-151">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6939f-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="6939f-152">Next Steps</span></span>  
 <span data-ttu-id="6939f-153">Si può notare che il metodo di overload `AddNumbers` funzione sembra avere dati dello stesso tipo del metodo ereditato dalla classe di base dell'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="6939f-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="6939f-154">Infatti, gli argomenti e parametri del metodo della classe base sono definiti come interi a 16 bit in Visual Basic 6.0, ma sono esposti come interi a 16 bit di tipo `Short` nelle versioni successive di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6939f-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="6939f-155">La nuova funzione accetta interi a 32 bit e la funzione di classe di base di overload.</span><span class="sxs-lookup"><span data-stu-id="6939f-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="6939f-156">Quando si lavora con gli oggetti COM, verificare che le dimensioni e tipi di dati dei parametri.</span><span class="sxs-lookup"><span data-stu-id="6939f-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="6939f-157">Ad esempio, quando si utilizza un oggetto COM che accetta un oggetto raccolta di Visual Basic 6.0 come argomento, è possibile fornire una raccolta di una versione successiva di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="6939f-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="6939f-158">Proprietà e metodi ereditati dalle classi COM possono essere sottoposto a override, vale a dire che è possibile dichiarare una proprietà locale o un metodo che sostituisce una proprietà o un metodo ereditato da una classe COM di base.</span><span class="sxs-lookup"><span data-stu-id="6939f-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="6939f-159">Le regole per eseguire l'override delle proprietà ereditate COM sono simili alle regole per eseguire l'override di altre proprietà e metodi con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6939f-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="6939f-160">Se si esegue l'override di qualsiasi proprietà o un metodo ereditato da una classe COM, è necessario eseguire l'override di tutte le altre proprietà ereditate e i metodi.</span><span class="sxs-lookup"><span data-stu-id="6939f-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="6939f-161">Le proprietà che utilizzano `ByRef` parametri non possono essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="6939f-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6939f-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6939f-162">See Also</span></span>  
 [<span data-ttu-id="6939f-163">Interoperabilità COM nelle applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6939f-163">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="6939f-164">Istruzione Inherits</span><span class="sxs-lookup"><span data-stu-id="6939f-164">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [<span data-ttu-id="6939f-165">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="6939f-165">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)
