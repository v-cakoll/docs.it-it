---
title: Metodi di estensione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: b5ad066fe9ec40d715702ed99537f45b21c558cf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701049"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="80150-102">Metodi di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80150-102">Extension Methods (Visual Basic)</span></span>

<span data-ttu-id="80150-103">I metodi di estensione consentono agli sviluppatori di aggiungere funzionalità personalizzate ai tipi di dati già definiti senza creare un nuovo tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="80150-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="80150-104">I metodi di estensione consentono di scrivere un metodo che può essere chiamato come se fosse un metodo di istanza del tipo esistente.</span><span class="sxs-lookup"><span data-stu-id="80150-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="80150-105">Note</span><span class="sxs-lookup"><span data-stu-id="80150-105">Remarks</span></span>

<span data-ttu-id="80150-106">Un metodo di estensione può essere solo una routine `Sub` o una procedura `Function`.</span><span class="sxs-lookup"><span data-stu-id="80150-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="80150-107">Non è possibile definire una proprietà, un campo o un evento di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="80150-108">Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension>` dallo spazio dei nomi <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> e devono essere definiti in un [modulo](../../../language-reference/statements/module-statement.md).</span><span class="sxs-lookup"><span data-stu-id="80150-108">All extension methods must be marked with the extension attribute `<Extension>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace and must be defined in a [Module](../../../language-reference/statements/module-statement.md).</span></span> <span data-ttu-id="80150-109">Se un metodo di estensione viene definito all'esterno di un modulo, il Visual Basic compilatore genera l'errore [BC36551](../../../misc/bc36551.md), "i metodi di estensione possono essere definiti solo nei moduli".</span><span class="sxs-lookup"><span data-stu-id="80150-109">If an extension method is defined outside a module, the Visual Basic compiler generates error [BC36551](../../../misc/bc36551.md), "Extension methods can be defined only in modules".</span></span>

<span data-ttu-id="80150-110">Il primo parametro di una definizione di metodo di estensione specifica il tipo di dati che il metodo estende.</span><span class="sxs-lookup"><span data-stu-id="80150-110">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="80150-111">Quando viene eseguito il metodo, il primo parametro viene associato all'istanza del tipo di dati che richiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="80150-111">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>

<span data-ttu-id="80150-112">L'attributo `Extension` può essere applicato solo a una Visual Basic [`Module`](../../../language-reference/statements/module-statement.md), [`Sub`](../../../language-reference/statements/sub-statement.md)o [`Function`](../../../language-reference/statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="80150-112">The `Extension` attribute can only be applied to a Visual Basic [`Module`](../../../language-reference/statements/module-statement.md), [`Sub`](../../../language-reference/statements/sub-statement.md), or [`Function`](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="80150-113">Se lo si applica a un `Class` o a un `Structure`, il compilatore Visual Basic genera l'errore [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md)"l'attributo" extension "può essere applicato solo alle dichiarazioni ' Module ',' Sub ' o ' Function '.</span><span class="sxs-lookup"><span data-stu-id="80150-113">If you apply it to a `Class` or a `Structure`, the Visual Basic compiler generates error [BC36550](../../../language-reference/error-messages/extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations.md), "'Extension' attribute can be applied only to 'Module', 'Sub', or 'Function' declarations".</span></span>

## <a name="example"></a><span data-ttu-id="80150-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="80150-114">Example</span></span>

<span data-ttu-id="80150-115">Nell'esempio seguente viene definita un'estensione `Print` per il tipo di dati <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="80150-115">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="80150-116">Il metodo usa `Console.WriteLine` per visualizzare una stringa.</span><span class="sxs-lookup"><span data-stu-id="80150-116">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="80150-117">Il parametro del metodo `Print`, `aString`, stabilisce che il metodo estende la classe <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="80150-117">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>
  
[!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]

<span data-ttu-id="80150-118">Si noti che la definizione del metodo di estensione è contrassegnata con l'attributo di estensione `<Extension()>`.</span><span class="sxs-lookup"><span data-stu-id="80150-118">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="80150-119">Contrassegnare il modulo in cui è definito il metodo è facoltativo, ma ogni metodo di estensione deve essere contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="80150-119">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="80150-120">per accedere all'attributo di estensione, è necessario importare <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="80150-120"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>

<span data-ttu-id="80150-121">I metodi di estensione possono essere dichiarati solo all'interno di moduli.</span><span class="sxs-lookup"><span data-stu-id="80150-121">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="80150-122">In genere, il modulo in cui è definito un metodo di estensione non corrisponde a quello in cui viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="80150-122">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="80150-123">Al contrario, il modulo che contiene il metodo di estensione viene importato, se necessario, per riportarlo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="80150-123">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="80150-124">Quando il modulo che contiene `Print` rientra nell'ambito, il metodo può essere chiamato come se fosse un metodo di istanza normale che non accetta argomenti, ad esempio `ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="80150-124">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>

[!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]

<span data-ttu-id="80150-125">L'esempio successivo, `PrintAndPunctuate`, è anche un'estensione di <xref:System.String>, questa volta definito con due parametri.</span><span class="sxs-lookup"><span data-stu-id="80150-125">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="80150-126">Il primo parametro, `aString`, stabilisce che il metodo di estensione estende <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="80150-126">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="80150-127">Il secondo parametro, `punc`, deve essere una stringa di segni di punteggiatura che viene passata come argomento quando viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="80150-127">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="80150-128">Il metodo Visualizza la stringa seguita dai segni di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="80150-128">The method displays the string followed by the punctuation marks.</span></span>

[!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]

<span data-ttu-id="80150-129">Il metodo viene chiamato inviando in un argomento stringa per `punc`: `example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="80150-129">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>

<span data-ttu-id="80150-130">Nell'esempio seguente vengono illustrati `Print` e `PrintAndPunctuate` definiti e chiamati.</span><span class="sxs-lookup"><span data-stu-id="80150-130">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="80150-131"><xref:System.Runtime.CompilerServices> viene importato nel modulo di definizione per consentire l'accesso all'attributo di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-131"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>


```vb
Imports System.Runtime.CompilerServices

Module StringExtensions

    <Extension()>
    Public Sub Print(aString As String)
        Console.WriteLine(aString)
    End Sub

    <Extension()>
    Public Sub PrintAndPunctuate(aString As String, punc As String)
        Console.WriteLine(aString & punc)
    End Sub
End Module
```

<span data-ttu-id="80150-132">Successivamente, i metodi di estensione vengono inseriti nell'ambito e chiamati:</span><span class="sxs-lookup"><span data-stu-id="80150-132">Next, the extension methods are brought into scope and called:</span></span>

```vb
Imports ConsoleApplication2.StringExtensions

Module Module1

    Sub Main()
        Dim example As String = "Example string"
        example.Print()

        example = "Hello"
        example.PrintAndPunctuate(".")
        example.PrintAndPunctuate("!!!!")
    End Sub
End Module
```

<span data-ttu-id="80150-133">Tutto ciò che è necessario per poter eseguire questi o metodi di estensione simili è che si trovino nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="80150-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="80150-134">Se il modulo che contiene un metodo di estensione è nell'ambito, è visibile in IntelliSense e può essere chiamato come se fosse un metodo di istanza comune.</span><span class="sxs-lookup"><span data-stu-id="80150-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>

<span data-ttu-id="80150-135">Si noti che quando vengono richiamati i metodi, per il primo parametro non viene inviato alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="80150-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="80150-136">Il parametro `aString` nelle definizioni di metodo precedenti è associato a `example`, l'istanza di `String` che li chiama.</span><span class="sxs-lookup"><span data-stu-id="80150-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="80150-137">Il compilatore utilizzerà `example` come argomento inviato al primo parametro.</span><span class="sxs-lookup"><span data-stu-id="80150-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>

<span data-ttu-id="80150-138">Se viene chiamato un metodo di estensione per un oggetto impostato su `Nothing`, viene eseguito il metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="80150-139">Questa operazione non si applica ai metodi di istanza ordinari.</span><span class="sxs-lookup"><span data-stu-id="80150-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="80150-140">È possibile verificare in modo esplicito `Nothing` nel metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-140">You can explicitly check for `Nothing` in the extension method.</span></span>

## <a name="types-that-can-be-extended"></a><span data-ttu-id="80150-141">Tipi che possono essere estesi</span><span class="sxs-lookup"><span data-stu-id="80150-141">Types that can be extended</span></span>

<span data-ttu-id="80150-142">È possibile definire un metodo di estensione per la maggior parte dei tipi che possono essere rappresentati in un elenco di parametri Visual Basic, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="80150-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>

- <span data-ttu-id="80150-143">Classi (tipi di riferimento)</span><span class="sxs-lookup"><span data-stu-id="80150-143">Classes (reference types)</span></span>
- <span data-ttu-id="80150-144">Strutture (tipi di valore)</span><span class="sxs-lookup"><span data-stu-id="80150-144">Structures (value types)</span></span>
- <span data-ttu-id="80150-145">Interfacce</span><span class="sxs-lookup"><span data-stu-id="80150-145">Interfaces</span></span>
- <span data-ttu-id="80150-146">Delegati</span><span class="sxs-lookup"><span data-stu-id="80150-146">Delegates</span></span>
- <span data-ttu-id="80150-147">Argomenti ByRef e ByVal</span><span class="sxs-lookup"><span data-stu-id="80150-147">ByRef and ByVal arguments</span></span>
- <span data-ttu-id="80150-148">Parametri del metodo generico</span><span class="sxs-lookup"><span data-stu-id="80150-148">Generic method parameters</span></span>
- <span data-ttu-id="80150-149">Matrici</span><span class="sxs-lookup"><span data-stu-id="80150-149">Arrays</span></span>

<span data-ttu-id="80150-150">Poiché il primo parametro specifica il tipo di dati che il metodo di estensione estende, è obbligatorio e non può essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="80150-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="80150-151">Per questo motivo, i parametri `Optional` e i parametri `ParamArray` non possono essere il primo parametro nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="80150-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>

<span data-ttu-id="80150-152">I metodi di estensione non vengono considerati nell'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="80150-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="80150-153">Nell'esempio seguente l'istruzione `anObject.PrintMe()` genera un'eccezione <xref:System.MissingMemberException>, ovvero la stessa eccezione che si verifica se è stata eliminata la seconda definizione del metodo di estensione `PrintMe`.</span><span class="sxs-lookup"><span data-stu-id="80150-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>

[!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]

## <a name="best-practices"></a><span data-ttu-id="80150-154">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="80150-154">Best practices</span></span>

<span data-ttu-id="80150-155">I metodi di estensione forniscono un metodo pratico e potente per estendere un tipo esistente.</span><span class="sxs-lookup"><span data-stu-id="80150-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="80150-156">Tuttavia, per usarli correttamente, è necessario prendere in considerazione alcuni aspetti.</span><span class="sxs-lookup"><span data-stu-id="80150-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="80150-157">Queste considerazioni si applicano principalmente agli autori di librerie di classi, ma potrebbero influire su qualsiasi applicazione che utilizza i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>

<span data-ttu-id="80150-158">In generale, i metodi di estensione aggiunti ai tipi di cui non si è proprietari sono più vulnerabili dei metodi di estensione aggiunti ai tipi che si controllano.</span><span class="sxs-lookup"><span data-stu-id="80150-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="80150-159">Nelle classi che non si possiede possono verificarsi numerose operazioni che possono interferire con i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>

- <span data-ttu-id="80150-160">Se esiste un membro di istanza accessibile che dispone di una firma compatibile con gli argomenti nell'istruzione chiamante, senza conversioni verso un tipo di argomento più piccolo richiesto dall'argomento al parametro, il metodo di istanza verrà utilizzato in modo preferenziale per qualsiasi metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="80150-161">Pertanto, se un metodo di istanza appropriato viene aggiunto a una classe in un determinato punto, un membro di estensione esistente su cui si basa la dipendenza potrebbe diventare inaccessibile.</span><span class="sxs-lookup"><span data-stu-id="80150-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>

- <span data-ttu-id="80150-162">L'autore di un metodo di estensione non può impedire ad altri programmatori di scrivere metodi di estensione in conflitto che possono avere la precedenza sull'estensione originale.</span><span class="sxs-lookup"><span data-stu-id="80150-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>

- <span data-ttu-id="80150-163">È possibile migliorare la robustezza inserendo i metodi di estensione nel relativo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="80150-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="80150-164">I consumer della libreria possono quindi includere uno spazio dei nomi o escluderlo oppure selezionare tra gli spazi dei nomi, separatamente dal resto della libreria.</span><span class="sxs-lookup"><span data-stu-id="80150-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>

- <span data-ttu-id="80150-165">Potrebbe essere più sicuro estendere le interfacce anziché estendere le classi, specialmente se non si è proprietari dell'interfaccia o della classe.</span><span class="sxs-lookup"><span data-stu-id="80150-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="80150-166">Una modifica in un'interfaccia influiscono su ogni classe che la implementa.</span><span class="sxs-lookup"><span data-stu-id="80150-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="80150-167">Pertanto, l'autore potrebbe avere meno probabilità di aggiungere o modificare i metodi in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="80150-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="80150-168">Tuttavia, se una classe implementa due interfacce con metodi di estensione con la stessa firma, il metodo di estensione non è visibile.</span><span class="sxs-lookup"><span data-stu-id="80150-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>

- <span data-ttu-id="80150-169">Estendere il tipo più specifico possibile.</span><span class="sxs-lookup"><span data-stu-id="80150-169">Extend the most specific type you can.</span></span> <span data-ttu-id="80150-170">In una gerarchia di tipi, se si seleziona un tipo da cui derivano molti altri tipi, esistono livelli di possibilità per l'introduzione di metodi di istanza o altri metodi di estensione che potrebbero interferire con l'utente.</span><span class="sxs-lookup"><span data-stu-id="80150-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>

## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="80150-171">Metodi di estensione, metodi di istanza e proprietà</span><span class="sxs-lookup"><span data-stu-id="80150-171">Extension methods, instance methods, and properties</span></span>

<span data-ttu-id="80150-172">Quando un metodo di istanza in ambito dispone di una firma compatibile con gli argomenti di un'istruzione chiamante, il metodo di istanza viene scelto in preferenza rispetto a qualsiasi metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="80150-173">Il metodo di istanza ha la precedenza anche se il metodo di estensione è una corrispondenza migliore.</span><span class="sxs-lookup"><span data-stu-id="80150-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="80150-174">Nell'esempio seguente `ExampleClass` contiene un metodo di istanza denominato `ExampleMethod` con un parametro di tipo `Integer`.</span><span class="sxs-lookup"><span data-stu-id="80150-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="80150-175">Il metodo di estensione `ExampleMethod` estende `ExampleClass` e ha un parametro di tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="80150-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>

[!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]

<span data-ttu-id="80150-176">La prima chiamata a `ExampleMethod` nel codice seguente chiama il metodo di estensione, perché `arg1` è `Long` ed è compatibile solo con il parametro `Long` nel metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="80150-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="80150-177">La seconda chiamata a `ExampleMethod` ha un argomento `Integer`, `arg2`, e chiama il metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="80150-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>

[!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]

<span data-ttu-id="80150-178">Invertire ora i tipi di dati dei parametri nei due metodi:</span><span class="sxs-lookup"><span data-stu-id="80150-178">Now reverse the data types of the parameters in the two methods:</span></span>

[!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]

<span data-ttu-id="80150-179">Questa volta il codice in `Main` chiama il metodo di istanza entrambe le volte.</span><span class="sxs-lookup"><span data-stu-id="80150-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="80150-180">Ciò è dovuto al fatto che sia `arg1` che `arg2` hanno una conversione verso un tipo di `Long` e il metodo di istanza ha la precedenza sul metodo di estensione in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="80150-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>

[!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]

<span data-ttu-id="80150-181">Pertanto, un metodo di estensione non può sostituire un metodo di istanza esistente.</span><span class="sxs-lookup"><span data-stu-id="80150-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="80150-182">Tuttavia, quando un metodo di estensione ha lo stesso nome di un metodo di istanza ma le firme non sono in conflitto, è possibile accedere a entrambi i metodi.</span><span class="sxs-lookup"><span data-stu-id="80150-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="80150-183">Se, ad esempio, la classe `ExampleClass` contiene un metodo denominato `ExampleMethod` che non accetta argomenti, sono consentiti metodi di estensione con lo stesso nome ma firme diverse, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="80150-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>

[!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]

<span data-ttu-id="80150-184">L'output di questo codice è il seguente:</span><span class="sxs-lookup"><span data-stu-id="80150-184">The output from this code is as follows:</span></span>

```console
Extension method
Instance method
```

<span data-ttu-id="80150-185">La situazione è più semplice con le proprietà: se un metodo di estensione ha lo stesso nome di una proprietà della classe che estende, il metodo di estensione non è visibile e non è possibile accedervi.</span><span class="sxs-lookup"><span data-stu-id="80150-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>

## <a name="extension-method-precedence"></a><span data-ttu-id="80150-186">Precedenza metodo di estensione</span><span class="sxs-lookup"><span data-stu-id="80150-186">Extension method precedence</span></span>

<span data-ttu-id="80150-187">Quando due metodi di estensione con firme identiche si trovano nell'ambito e sono accessibili, viene richiamato quello con precedenza più alta.</span><span class="sxs-lookup"><span data-stu-id="80150-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="80150-188">La precedenza di un metodo di estensione è basata sul meccanismo utilizzato per portare il metodo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="80150-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="80150-189">Nell'elenco seguente viene illustrata la gerarchia di precedenza, dal più alto al più basso.</span><span class="sxs-lookup"><span data-stu-id="80150-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>

1. <span data-ttu-id="80150-190">Metodi di estensione definiti all'interno del modulo corrente.</span><span class="sxs-lookup"><span data-stu-id="80150-190">Extension methods defined inside the current module.</span></span>

2. <span data-ttu-id="80150-191">I metodi di estensione definiti nei tipi di dati nello spazio dei nomi corrente o in uno qualsiasi dei relativi elementi padre, con spazi dei nomi figlio con precedenza maggiore rispetto agli spazi dei nomi padre.</span><span class="sxs-lookup"><span data-stu-id="80150-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>

3. <span data-ttu-id="80150-192">Metodi di estensione definiti in qualsiasi importazione di tipi nel file corrente.</span><span class="sxs-lookup"><span data-stu-id="80150-192">Extension methods defined inside any type imports in the current file.</span></span>

4. <span data-ttu-id="80150-193">Metodi di estensione definiti in qualsiasi importazione di spazi dei nomi nel file corrente.</span><span class="sxs-lookup"><span data-stu-id="80150-193">Extension methods defined inside any namespace imports in the current file.</span></span>

5. <span data-ttu-id="80150-194">Metodi di estensione definiti in qualsiasi importazione di tipi a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="80150-194">Extension methods defined inside any project-level type imports.</span></span>

6. <span data-ttu-id="80150-195">Metodi di estensione definiti in qualsiasi importazione di spazi dei nomi a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="80150-195">Extension methods defined inside any project-level namespace imports.</span></span>

<span data-ttu-id="80150-196">Se la precedenza non risolve l'ambiguità, è possibile usare il nome completo per specificare il metodo che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="80150-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="80150-197">Se il metodo `Print` nell'esempio precedente è definito in un modulo denominato `StringExtensions`, il nome completo è `StringExtensions.Print(example)` anziché `example.Print()`.</span><span class="sxs-lookup"><span data-stu-id="80150-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>

## <a name="see-also"></a><span data-ttu-id="80150-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80150-198">See also</span></span>

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="80150-199">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="80150-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="80150-200">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="80150-200">Module Statement</span></span>](../../../language-reference/statements/module-statement.md)
- [<span data-ttu-id="80150-201">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="80150-201">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="80150-202">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="80150-202">Optional Parameters</span></span>](optional-parameters.md)
- [<span data-ttu-id="80150-203">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="80150-203">Parameter Arrays</span></span>](parameter-arrays.md)
- [<span data-ttu-id="80150-204">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="80150-204">Attributes overview</span></span>](../../concepts/attributes/index.md)
- [<span data-ttu-id="80150-205">Ambito in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="80150-205">Scope in Visual Basic</span></span>](../declared-elements/scope.md)
