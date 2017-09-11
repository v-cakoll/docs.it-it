---
title: "Procedura dettagliata: Implementazione dell&quot;ereditarietà con gli oggetti COM (Visual Basic) | Documenti di Microsoft"
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
- inheritance, COM reusability
- base classes, COM reusability
- inheritance, walkthroughs
- derived classes, COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
caps.latest.revision: 16
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
ms.openlocfilehash: 0e816d1728678467d930de524b894d175f9b0c0a
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="5e0cf-102">Procedura dettagliata: implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5e0cf-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>
<span data-ttu-id="5e0cf-103">È possibile derivare classi di Visual Basic da `Public` classi di oggetti COM, anche quelli creati in versioni precedenti di [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e0cf-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="5e0cf-104">Le proprietà e metodi delle classi ereditate da oggetti COM possono essere sottoposto a override o sottoposto a overload solo come proprietà e metodi di qualsiasi altra classe di base possono essere sottoposto a override o di overload.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="5e0cf-105">Ereditarietà da oggetti COM è utile quando si dispone di una libreria di classi esistenti che non si desidera ricompilare.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>  
  
 <span data-ttu-id="5e0cf-106">La procedura seguente viene illustrato come utilizzare Visual Basic 6.0 per creare un oggetto COM che contiene una classe e quindi utilizzarlo come classe base.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="5e0cf-107">Per creare l'oggetto COM che viene utilizzato in questa procedura dettagliata</span><span class="sxs-lookup"><span data-stu-id="5e0cf-107">To build the COM object that is used in this walkthrough</span></span>  
  
1.  <span data-ttu-id="5e0cf-108">In Visual Basic 6.0, aprire un nuovo progetto DLL ActiveX.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="5e0cf-109">Un progetto denominato `Project1` viene creato.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-109">A project named `Project1` is created.</span></span> <span data-ttu-id="5e0cf-110">Dispone di una classe denominata `Class1`.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-110">It has a class named `Class1`.</span></span>  
  
2.  <span data-ttu-id="5e0cf-111">Nel **Project Explorer**, fare doppio clic su **Project1**, quindi fare clic su **proprietà Project1**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="5e0cf-112">Il **le proprietà del progetto** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-112">The **Project Properties** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="5e0cf-113">Nel **generale** scheda della finestra il **le proprietà del progetto** finestra di dialogo, modificare il nome del progetto digitando `ComObject1` nel **nome progetto** campo.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>  
  
4.  <span data-ttu-id="5e0cf-114">Nel **Project Explorer**, fare doppio clic su `Class1`, quindi fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="5e0cf-115">Il **proprietà** verrà visualizzata la finestra per la classe.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-115">The **Properties** window for the class is displayed.</span></span>  
  
5.  <span data-ttu-id="5e0cf-116">Modifica il `Name` proprietà `MathFunctions`.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-116">Change the `Name` property to `MathFunctions`.</span></span>  
  
6.  <span data-ttu-id="5e0cf-117">Nel **Project Explorer**, fare doppio clic su `MathFunctions`, quindi fare clic su **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="5e0cf-118">Il **Editor di codice** viene visualizzato.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-118">The **Code Editor** is displayed.</span></span>  
  
7.  <span data-ttu-id="5e0cf-119">Aggiungere una variabile locale per contenere il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="5e0cf-119">Add a local variable to hold the property value:</span></span>  
  
    ```  
    ' Local variable to hold property value  
    Private mvarProp1 As Integer  
    ```  
  
8.  <span data-ttu-id="5e0cf-120">Aggiungere proprietà `Let` e proprietà `Get` le routine di proprietà:</span><span class="sxs-lookup"><span data-stu-id="5e0cf-120">Add Property `Let` and Property `Get` property procedures:</span></span>  
  
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
  
9. <span data-ttu-id="5e0cf-121">Aggiungere una funzione:</span><span class="sxs-lookup"><span data-stu-id="5e0cf-121">Add a function:</span></span>  
  
    ```  
    Function AddNumbers(   
       ByVal SomeNumber As Integer,   
       ByVal AnotherNumber As Integer) As Integer  
  
       AddNumbers = SomeNumber + AnotherNumber  
    End Function  
    ```  
  
10. <span data-ttu-id="5e0cf-122">Creare e registrare l'oggetto COM scegliendo **Crea ComObject1. dll** sul **File** menu.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e0cf-123">Sebbene sia possibile esporre anche una classe creata con [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] come oggetto COM non è un vero oggetto COM e non può essere utilizzato in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-123">Although you can also expose a class created with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="5e0cf-124">Per informazioni dettagliate, vedere [l'interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="5e0cf-124">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="interop-assemblies"></a><span data-ttu-id="5e0cf-125">Assembly di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="5e0cf-125">Interop Assemblies</span></span>  
 <span data-ttu-id="5e0cf-126">Nella procedura seguente, si creerà un assembly di interoperabilità, che funge da ponte tra codice non gestito (ad esempio un oggetto COM) e il codice gestito [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] utilizza.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] uses.</span></span> <span data-ttu-id="5e0cf-127">L'assembly di interoperabilità che [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] crea gestisce molti dei dettagli relativi all'utilizzo con COM oggetti, ad esempio *il marshalling di interoperabilità*, il processo di creazione dei pacchetti parametri e valori restituiti in dati equivalenti tipi durante lo spostamento da e verso oggetti COM.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-127">The interop assembly that [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="5e0cf-128">Il riferimento nel [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] punti dell'applicazione per l'assembly di interoperabilità, non all'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-128">The reference in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] application points to the interop assembly, not the actual COM object.</span></span>  
  
#### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="5e0cf-129">Per utilizzare un oggetto COM con Visual Basic 2005 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="5e0cf-129">To use a COM object with Visual Basic 2005 and later versions</span></span>  
  
1.  <span data-ttu-id="5e0cf-130">Aprire un nuovo [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] progetto applicazione Windows.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-130">Open a new [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Windows Application project.</span></span>  
  
2.  <span data-ttu-id="5e0cf-131">Nel **progetto** menu, fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-131">On the **Project** menu, click **Add Reference**.</span></span>  
  
     <span data-ttu-id="5e0cf-132">Il **Aggiungi riferimento** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-132">The **Add Reference** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="5e0cf-133">Nel **COM** scheda, fare doppio clic su `ComObject1` nel **nome componente** elenco e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>  
  
4.  <span data-ttu-id="5e0cf-134">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-134">On the **Project** menu, click **Add New Item**.</span></span>  
  
     <span data-ttu-id="5e0cf-135">Il **Aggiungi nuovo elemento** viene visualizzata la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-135">The **Add New Item** dialog box is displayed.</span></span>  
  
5.  <span data-ttu-id="5e0cf-136">Nel **modelli** riquadro, fare clic su **classe**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-136">In the **Templates** pane, click **Class**.</span></span>  
  
     <span data-ttu-id="5e0cf-137">Il nome file predefinito, `Class1.vb`, è presente il **nome** campo.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="5e0cf-138">Modificare questo campo per MathClass e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="5e0cf-139">Verrà creata una classe denominata `MathClass`e verrà visualizzato il codice.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-139">This creates a class named `MathClass`, and displays its code.</span></span>  
  
6.  <span data-ttu-id="5e0cf-140">Aggiungere il codice seguente all'inizio del `MathClass` per ereditare dalla classe COM.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>  
  
     <span data-ttu-id="5e0cf-141">[!code-vb[VbVbalrInterop&#31;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5e0cf-141">[!code-vb[VbVbalrInterop#31](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_1.vb)]</span></span>  
  
7.  <span data-ttu-id="5e0cf-142">Eseguire l'overload del metodo pubblico della classe di base aggiungendo il codice seguente al `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="5e0cf-142">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="5e0cf-143">[!code-vb[VbVbalrInterop n.&32;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5e0cf-143">[!code-vb[VbVbalrInterop#32](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_2.vb)]</span></span>  
  
8.  <span data-ttu-id="5e0cf-144">Estendere la classe ereditata aggiungendo il codice seguente al `MathClass`:</span><span class="sxs-lookup"><span data-stu-id="5e0cf-144">Extend the inherited class by adding the following code to `MathClass`:</span></span>  
  
     <span data-ttu-id="5e0cf-145">[!code-vb[VbVbalrInterop n.&33;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="5e0cf-145">[!code-vb[VbVbalrInterop#33](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_3.vb)]</span></span>  
  
 <span data-ttu-id="5e0cf-146">La nuova classe eredita le proprietà della classe di base dell'oggetto COM, un metodo di overload e definisce un nuovo metodo per estendere la classe.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-146">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>  
  
#### <a name="to-test-the-inherited-class"></a><span data-ttu-id="5e0cf-147">Per testare la classe ereditata</span><span class="sxs-lookup"><span data-stu-id="5e0cf-147">To test the inherited class</span></span>  
  
1.  <span data-ttu-id="5e0cf-148">Aggiungere un pulsante al form di avvio e quindi fare doppio clic per visualizzare il codice.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-148">Add a button to your startup form, and then double-click it to view its code.</span></span>  
  
2.  <span data-ttu-id="5e0cf-149">Il pulsante `Click` routine del gestore eventi, aggiungere il codice seguente per creare un'istanza di `MathClass` e chiamare i metodi di overload:</span><span class="sxs-lookup"><span data-stu-id="5e0cf-149">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>  
  
     <span data-ttu-id="5e0cf-150">[!code-vb[VbVbalrInterop&#34;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="5e0cf-150">[!code-vb[VbVbalrInterop#34](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-implementing-inheritance-with-com-objects_4.vb)]</span></span>  
  
3.  <span data-ttu-id="5e0cf-151">Eseguire il progetto premendo F5.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-151">Run the project by pressing F5.</span></span>  
  
 <span data-ttu-id="5e0cf-152">Quando si fa clic sul pulsante nel form, il `AddNumbers` prima chiamata al metodo con `Short` numeri del tipo di dati e [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sceglie il metodo appropriato dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-152">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] chooses the appropriate method from the base class.</span></span> <span data-ttu-id="5e0cf-153">La seconda chiamata a `AddNumbers` viene indirizzata al metodo di overload da `MathClass`.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-153">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="5e0cf-154">La terza chiamata richiama il `SubtractNumbers` (metodo), che estende la classe.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-154">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="5e0cf-155">La proprietà nella classe di base è impostata e viene visualizzato il valore.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-155">The property in the base class is set, and the value is displayed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="5e0cf-156">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5e0cf-156">Next Steps</span></span>  
 <span data-ttu-id="5e0cf-157">Si è notato che il metodo di overload `AddNumbers` funzione sembra avere dati dello stesso tipo del metodo ereditato dalla classe di base dell'oggetto COM.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-157">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="5e0cf-158">Questo avviene perché gli argomenti e parametri del metodo della classe base sono definiti come numeri interi a 16 bit in Visual Basic 6.0, ma sono esposti come integer a 16 bit di tipo `Short` nelle versioni successive di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-158">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="5e0cf-159">La nuova funzione accetta valori integer a 32 bit ed esegue l'overload di funzione di classe base.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-159">The new function accepts 32-bit integers, and overloads the base class function.</span></span>  
  
 <span data-ttu-id="5e0cf-160">Quando si utilizzano oggetti COM, assicurarsi di verificare le dimensioni e tipi di dati dei parametri.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-160">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="5e0cf-161">Ad esempio, quando si utilizza un oggetto COM che accetta un oggetto raccolta di Visual Basic 6.0 come argomento, è possibile fornire un insieme di una versione successiva di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-161">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>  
  
 <span data-ttu-id="5e0cf-162">Possono essere ignorati le proprietà e metodi ereditati dalle classi COM, vale a dire che è possibile dichiarare una proprietà locale o un metodo che sostituisce una proprietà o metodo ereditato da una classe COM.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-162">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="5e0cf-163">Le regole per eseguire l'override delle proprietà COM ereditate sono simili alle regole per eseguire l'override di altre proprietà e metodi con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e0cf-163">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>  
  
-   <span data-ttu-id="5e0cf-164">Se si esegue l'override di proprietà o metodi ereditati da una classe COM, è necessario sostituire tutte le altre proprietà ereditate e metodi.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-164">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>  
  
-   <span data-ttu-id="5e0cf-165">Le proprietà che utilizzano `ByRef` parametri non possono essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="5e0cf-165">Properties that use `ByRef` parameters cannot be overridden.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0cf-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e0cf-166">See Also</span></span>  
 <span data-ttu-id="5e0cf-167">[Interoperabilità COM nelle applicazioni .NET Framework](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="5e0cf-167">[COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="5e0cf-168"> [Inherits (istruzione)](../../../visual-basic/language-reference/statements/inherits-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5e0cf-168"> [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) </span></span>  
<span data-ttu-id="5e0cf-169"> [Tipo di dati Short](../../../visual-basic/language-reference/data-types/short-data-type.md)</span><span class="sxs-lookup"><span data-stu-id="5e0cf-169"> [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)</span></span>
