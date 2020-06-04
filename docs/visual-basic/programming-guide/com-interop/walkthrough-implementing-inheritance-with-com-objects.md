---
title: "Procedura dettagliata: Implementazione dell'ereditarietà con gli oggetti COM"
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], COM reusability
- base classes [Visual Basic], COM reusability
- inheritance [Visual Basic], walkthroughs
- derived classes [Visual Basic], COM reusability
ms.assetid: f8e7263a-de13-48d1-b67c-ca1adf3544d9
ms.openlocfilehash: bdb891e1a150f0d7b79aefcc3db1f18dc8e84be4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396727"
---
# <a name="walkthrough-implementing-inheritance-with-com-objects-visual-basic"></a><span data-ttu-id="2452b-102">Procedura dettagliata: implementazione dell'ereditarietà con gli oggetti COM (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2452b-102">Walkthrough: Implementing Inheritance with COM Objects (Visual Basic)</span></span>

<span data-ttu-id="2452b-103">È possibile derivare Visual Basic classi da `Public` classi negli oggetti com, anche quelle create nelle versioni precedenti di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2452b-103">You can derive Visual Basic classes from `Public` classes in COM objects, even those created in earlier versions of Visual Basic.</span></span> <span data-ttu-id="2452b-104">Le proprietà e i metodi delle classi ereditate dagli oggetti COM possono essere sottoposti a override o sottoposti a overload come le proprietà e i metodi di qualsiasi altra classe di base possono essere sostituiti o sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="2452b-104">The properties and methods of classes inherited from COM objects can be overridden or overloaded just as properties and methods of any other base class can be overridden or overloaded.</span></span> <span data-ttu-id="2452b-105">L'ereditarietà dagli oggetti COM è utile quando si dispone di una libreria di classi esistente che non si desidera ricompilare.</span><span class="sxs-lookup"><span data-stu-id="2452b-105">Inheritance from COM objects is useful when you have an existing class library that you do not want to recompile.</span></span>

<span data-ttu-id="2452b-106">Nella procedura seguente viene illustrato come utilizzare Visual Basic 6,0 per creare un oggetto COM contenente una classe e quindi utilizzarlo come classe base.</span><span class="sxs-lookup"><span data-stu-id="2452b-106">The following procedure shows how to use Visual Basic 6.0 to create a COM object that contains a class, and then use it as a base class.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-build-the-com-object-that-is-used-in-this-walkthrough"></a><span data-ttu-id="2452b-107">Per compilare l'oggetto COM utilizzato in questa procedura dettagliata</span><span class="sxs-lookup"><span data-stu-id="2452b-107">To build the COM object that is used in this walkthrough</span></span>

1. <span data-ttu-id="2452b-108">In Visual Basic 6,0 aprire un nuovo progetto di DLL ActiveX.</span><span class="sxs-lookup"><span data-stu-id="2452b-108">In Visual Basic 6.0, open a new ActiveX DLL project.</span></span> <span data-ttu-id="2452b-109">Viene creato un progetto denominato `Project1` .</span><span class="sxs-lookup"><span data-stu-id="2452b-109">A project named `Project1` is created.</span></span> <span data-ttu-id="2452b-110">Dispone di una classe denominata `Class1` .</span><span class="sxs-lookup"><span data-stu-id="2452b-110">It has a class named `Class1`.</span></span>

2. <span data-ttu-id="2452b-111">In **Esplora progetti**fare clic con il pulsante destro del mouse su **Project1**e quindi scegliere **Proprietà Project1**.</span><span class="sxs-lookup"><span data-stu-id="2452b-111">In the **Project Explorer**, right-click **Project1**, and then click **Project1 Properties**.</span></span> <span data-ttu-id="2452b-112">Verrà visualizzata la finestra di dialogo **Proprietà progetto** .</span><span class="sxs-lookup"><span data-stu-id="2452b-112">The **Project Properties** dialog box is displayed.</span></span>

3. <span data-ttu-id="2452b-113">Nella scheda **generale** della finestra di dialogo **Proprietà progetto** modificare il nome del progetto digitando `ComObject1` nel campo **nome progetto** .</span><span class="sxs-lookup"><span data-stu-id="2452b-113">On the **General** tab of the **Project Properties** dialog box, change the project name by typing `ComObject1` in the **Project Name** field.</span></span>

4. <span data-ttu-id="2452b-114">In **Esplora progetti**fare clic con il pulsante destro del mouse su `Class1` , quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="2452b-114">In the **Project Explorer**, right-click `Class1`, and then click **Properties**.</span></span> <span data-ttu-id="2452b-115">Viene visualizzata la finestra **Proprietà** per la classe.</span><span class="sxs-lookup"><span data-stu-id="2452b-115">The **Properties** window for the class is displayed.</span></span>

5. <span data-ttu-id="2452b-116">Modificare la `Name` Proprietà in `MathFunctions` .</span><span class="sxs-lookup"><span data-stu-id="2452b-116">Change the `Name` property to `MathFunctions`.</span></span>

6. <span data-ttu-id="2452b-117">In **Esplora progetti**fare clic con il pulsante destro del mouse su `MathFunctions` , quindi scegliere **Visualizza codice**.</span><span class="sxs-lookup"><span data-stu-id="2452b-117">In the **Project Explorer**, right-click `MathFunctions`, and then click **View Code**.</span></span> <span data-ttu-id="2452b-118">Viene visualizzato l' **editor di codice** .</span><span class="sxs-lookup"><span data-stu-id="2452b-118">The **Code Editor** is displayed.</span></span>

7. <span data-ttu-id="2452b-119">Aggiungere una variabile locale per conservare il valore della proprietà:</span><span class="sxs-lookup"><span data-stu-id="2452b-119">Add a local variable to hold the property value:</span></span>

    ```vb
    ' Local variable to hold property value
    Private mvarProp1 As Integer
    ```

8. <span data-ttu-id="2452b-120">Aggiungere `Let` routine di proprietà e proprietà `Get` :</span><span class="sxs-lookup"><span data-stu-id="2452b-120">Add Property `Let` and Property `Get` property procedures:</span></span>

    ```vb
    Public Property Let Prop1(ByVal vData As Integer)
       'Used when assigning a value to the property.
       mvarProp1 = vData
    End Property
    Public Property Get Prop1() As Integer
       'Used when retrieving a property's value.
       Prop1 = mvarProp1
    End Property
    ```

9. <span data-ttu-id="2452b-121">Aggiungere una funzione:</span><span class="sxs-lookup"><span data-stu-id="2452b-121">Add a function:</span></span>

    ```vb
    Function AddNumbers(
       ByVal SomeNumber As Integer,
       ByVal AnotherNumber As Integer) As Integer

       AddNumbers = SomeNumber + AnotherNumber
    End Function
    ```

10. <span data-ttu-id="2452b-122">Creare e registrare l'oggetto COM scegliendo **make ComObject1. dll** dal menu **file** .</span><span class="sxs-lookup"><span data-stu-id="2452b-122">Create and register the COM object by clicking **Make ComObject1.dll** on the **File** menu.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2452b-123">Sebbene sia anche possibile esporre una classe creata con Visual Basic come oggetto COM, non è un vero oggetto COM e non può essere utilizzata in questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="2452b-123">Although you can also expose a class created with Visual Basic as a COM object, it is not a true COM object and cannot be used in this walkthrough.</span></span> <span data-ttu-id="2452b-124">Per informazioni dettagliate, vedere [interoperabilità com nelle applicazioni .NET Framework](com-interoperability-in-net-framework-applications.md).</span><span class="sxs-lookup"><span data-stu-id="2452b-124">For details, see [COM Interoperability in .NET Framework Applications](com-interoperability-in-net-framework-applications.md).</span></span>

## <a name="interop-assemblies"></a><span data-ttu-id="2452b-125">Assembly di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="2452b-125">Interop Assemblies</span></span>

<span data-ttu-id="2452b-126">Nella procedura seguente verrà creato un assembly di interoperabilità, che funge da Bridge tra codice non gestito (ad esempio un oggetto COM) e il codice gestito utilizzato da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="2452b-126">In the following procedure, you will create an interop assembly, which acts as a bridge between unmanaged code (such as a COM object) and the managed code Visual Studio uses.</span></span> <span data-ttu-id="2452b-127">L'assembly di interoperabilità creato da Visual Basic gestisce molti dettagli sull'utilizzo di oggetti COM, ad esempio il *marshalling di interoperabilità*, il processo di creazione del pacchetto di parametri e la restituzione di valori in tipi di dati equivalenti durante il passaggio da e verso oggetti com.</span><span class="sxs-lookup"><span data-stu-id="2452b-127">The interop assembly that Visual Basic creates handles many of the details of working with COM objects, such as *interop marshaling*, the process of packaging parameters and return values into equivalent data types as they move to and from COM objects.</span></span> <span data-ttu-id="2452b-128">Il riferimento nell'applicazione Visual Basic punta all'assembly di interoperabilità, non all'oggetto COM effettivo.</span><span class="sxs-lookup"><span data-stu-id="2452b-128">The reference in the Visual Basic application points to the interop assembly, not the actual COM object.</span></span>

### <a name="to-use-a-com-object-with-visual-basic-2005-and-later-versions"></a><span data-ttu-id="2452b-129">Per usare un oggetto COM con Visual Basic 2005 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2452b-129">To use a COM object with Visual Basic 2005 and later versions</span></span>

1. <span data-ttu-id="2452b-130">Aprire un nuovo progetto Applicazione Windows in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2452b-130">Open a new Visual Basic Windows Application project.</span></span>

2. <span data-ttu-id="2452b-131">Scegliere **Aggiungi riferimento** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="2452b-131">On the **Project** menu, click **Add Reference**.</span></span>

     <span data-ttu-id="2452b-132">Viene visualizzata la finestra di dialogo **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="2452b-132">The **Add Reference** dialog box is displayed.</span></span>

3. <span data-ttu-id="2452b-133">Nella scheda **com** fare doppio clic `ComObject1` nell'elenco **nome componente** e fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2452b-133">On the **COM** tab, double-click `ComObject1` in the **Component Name** list and click **OK**.</span></span>

4. <span data-ttu-id="2452b-134">Dal menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2452b-134">On the **Project** menu, click **Add New Item**.</span></span>

     <span data-ttu-id="2452b-135">La finestra di dialogo **Aggiungi nuovo elemento** viene visualizzata.</span><span class="sxs-lookup"><span data-stu-id="2452b-135">The **Add New Item** dialog box is displayed.</span></span>

5. <span data-ttu-id="2452b-136">Nel riquadro **modelli** fare clic su **classe**.</span><span class="sxs-lookup"><span data-stu-id="2452b-136">In the **Templates** pane, click **Class**.</span></span>

     <span data-ttu-id="2452b-137">Il nome file predefinito, `Class1.vb` , viene visualizzato nel campo **nome** .</span><span class="sxs-lookup"><span data-stu-id="2452b-137">The default file name, `Class1.vb`, appears in the **Name** field.</span></span> <span data-ttu-id="2452b-138">Modificare questo campo in MathClass. vb e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="2452b-138">Change this field to MathClass.vb and click **Add**.</span></span> <span data-ttu-id="2452b-139">Viene creata una classe denominata `MathClass` e viene visualizzato il relativo codice.</span><span class="sxs-lookup"><span data-stu-id="2452b-139">This creates a class named `MathClass`, and displays its code.</span></span>

6. <span data-ttu-id="2452b-140">Aggiungere il codice seguente all'inizio di `MathClass` per ereditare dalla classe com.</span><span class="sxs-lookup"><span data-stu-id="2452b-140">Add the following code to the top of `MathClass` to inherit from the COM class.</span></span>

     [!code-vb[VbVbalrInterop#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#31)]

7. <span data-ttu-id="2452b-141">Eseguire l'overload del metodo pubblico della classe base aggiungendo il codice seguente a `MathClass` :</span><span class="sxs-lookup"><span data-stu-id="2452b-141">Overload the public method of the base class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#32)]

8. <span data-ttu-id="2452b-142">Estendere la classe ereditata aggiungendo il codice seguente a `MathClass` :</span><span class="sxs-lookup"><span data-stu-id="2452b-142">Extend the inherited class by adding the following code to `MathClass`:</span></span>

     [!code-vb[VbVbalrInterop#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#33)]

<span data-ttu-id="2452b-143">La nuova classe eredita le proprietà della classe di base nell'oggetto COM, sovraccarica un metodo e definisce un nuovo metodo per estendere la classe.</span><span class="sxs-lookup"><span data-stu-id="2452b-143">The new class inherits the properties of the base class in the COM object, overloads a method, and defines a new method to extend the class.</span></span>

### <a name="to-test-the-inherited-class"></a><span data-ttu-id="2452b-144">Per testare la classe ereditata</span><span class="sxs-lookup"><span data-stu-id="2452b-144">To test the inherited class</span></span>

1. <span data-ttu-id="2452b-145">Aggiungere un pulsante al form di avvio e quindi fare doppio clic su di esso per visualizzarne il codice.</span><span class="sxs-lookup"><span data-stu-id="2452b-145">Add a button to your startup form, and then double-click it to view its code.</span></span>

2. <span data-ttu-id="2452b-146">Nella procedura relativa al `Click` gestore eventi del pulsante aggiungere il codice seguente per creare un'istanza di `MathClass` e chiamare i metodi di overload:</span><span class="sxs-lookup"><span data-stu-id="2452b-146">In the button's `Click` event handler procedure, add the following code to create an instance of `MathClass` and call the overloaded methods:</span></span>

     [!code-vb[VbVbalrInterop#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#34)]

3. <span data-ttu-id="2452b-147">Eseguire il progetto premendo F5.</span><span class="sxs-lookup"><span data-stu-id="2452b-147">Run the project by pressing F5.</span></span>

<span data-ttu-id="2452b-148">Quando si fa clic sul pulsante nel form, il `AddNumbers` metodo viene chiamato prima con i `Short` numeri dei tipi di dati e Visual Basic sceglie il metodo appropriato dalla classe di base.</span><span class="sxs-lookup"><span data-stu-id="2452b-148">When you click the button on the form, the `AddNumbers` method is first called with `Short` data type numbers, and Visual Basic chooses the appropriate method from the base class.</span></span> <span data-ttu-id="2452b-149">La seconda chiamata a `AddNumbers` viene indirizzata al metodo di overload da `MathClass` .</span><span class="sxs-lookup"><span data-stu-id="2452b-149">The second call to `AddNumbers` is directed to the overload method from `MathClass`.</span></span> <span data-ttu-id="2452b-150">La terza chiamata chiama il `SubtractNumbers` metodo, che estende la classe.</span><span class="sxs-lookup"><span data-stu-id="2452b-150">The third call calls the `SubtractNumbers` method, which extends the class.</span></span> <span data-ttu-id="2452b-151">Viene impostata la proprietà nella classe di base e viene visualizzato il valore.</span><span class="sxs-lookup"><span data-stu-id="2452b-151">The property in the base class is set, and the value is displayed.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2452b-152">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2452b-152">Next Steps</span></span>

<span data-ttu-id="2452b-153">Si può notare che la `AddNumbers` funzione in overload sembra avere lo stesso tipo di dati del metodo ereditato dalla classe di base dell'oggetto com.</span><span class="sxs-lookup"><span data-stu-id="2452b-153">You may have noticed that the overloaded `AddNumbers` function appears to have the same data type as the method inherited from the base class of the COM object.</span></span> <span data-ttu-id="2452b-154">Ciò è dovuto al fatto che gli argomenti e i parametri del metodo della classe base sono definiti come interi a 16 bit in Visual Basic 6,0, ma vengono esposti come interi a 16 bit di tipo `Short` nelle versioni successive di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2452b-154">This is because the arguments and parameters of the base class method are defined as 16-bit integers in Visual Basic 6.0, but they are exposed as 16-bit integers of type `Short` in later versions of Visual Basic.</span></span> <span data-ttu-id="2452b-155">La nuova funzione accetta interi a 32 bit e sovraccarica la funzione della classe di base.</span><span class="sxs-lookup"><span data-stu-id="2452b-155">The new function accepts 32-bit integers, and overloads the base class function.</span></span>

<span data-ttu-id="2452b-156">Quando si utilizzano gli oggetti COM, assicurarsi di verificare le dimensioni e i tipi di dati dei parametri.</span><span class="sxs-lookup"><span data-stu-id="2452b-156">When working with COM objects, make sure that you verify the size and data types of parameters.</span></span> <span data-ttu-id="2452b-157">Ad esempio, quando si usa un oggetto COM che accetta un oggetto raccolta Visual Basic 6,0 come argomento, non è possibile fornire una raccolta da una versione successiva di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="2452b-157">For example, when you are using a COM object that accepts a Visual Basic 6.0 collection object as an argument, you cannot provide a collection from a later version of Visual Basic.</span></span>

<span data-ttu-id="2452b-158">È possibile eseguire l'override delle proprietà e dei metodi ereditati dalle classi COM, vale a dire che è possibile dichiarare una proprietà o un metodo locale che sostituisce una proprietà o un metodo ereditato da una classe COM di base.</span><span class="sxs-lookup"><span data-stu-id="2452b-158">Properties and methods inherited from COM classes can be overridden, meaning that you can declare a local property or method that replaces a property or method inherited from a base COM class.</span></span> <span data-ttu-id="2452b-159">Le regole per l'override delle proprietà COM ereditate sono simili a quelle per l'override di altre proprietà e metodi con le eccezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2452b-159">The rules for overriding inherited COM properties are similar to the rules for overriding other properties and methods with the following exceptions:</span></span>

- <span data-ttu-id="2452b-160">Se si esegue l'override di qualsiasi proprietà o metodo ereditato da una classe COM, è necessario eseguire l'override di tutte le altre proprietà e metodi ereditati.</span><span class="sxs-lookup"><span data-stu-id="2452b-160">If you override any property or method inherited from a COM class, you must override all the other inherited properties and methods.</span></span>

- <span data-ttu-id="2452b-161">Non è possibile eseguire l'override delle proprietà che usano `ByRef` parametri.</span><span class="sxs-lookup"><span data-stu-id="2452b-161">Properties that use `ByRef` parameters cannot be overridden.</span></span>

## <a name="see-also"></a><span data-ttu-id="2452b-162">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2452b-162">See also</span></span>

- [<span data-ttu-id="2452b-163">Interoperabilità COM nelle applicazioni .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2452b-163">COM Interoperability in .NET Framework Applications</span></span>](com-interoperability-in-net-framework-applications.md)
- [<span data-ttu-id="2452b-164">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="2452b-164">Inherits Statement</span></span>](../../language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="2452b-165">Tipo di dati Short</span><span class="sxs-lookup"><span data-stu-id="2452b-165">Short Data Type</span></span>](../../language-reference/data-types/short-data-type.md)
