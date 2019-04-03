---
title: Metodi di estensione (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ExtensionMethods
helpviewer_keywords:
- extending data types [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
ms.openlocfilehash: aca8f18c4bc53318792a119617b1ca0d6c4cc32e
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822076"
---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="2e20d-102">Metodi di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2e20d-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="2e20d-103">I metodi di estensione consentono agli sviluppatori di aggiungere funzionalità personalizzate ai tipi di dati che sono già definiti senza creare un nuovo tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="2e20d-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="2e20d-104">I metodi di estensione consentono di scrivere un metodo che può essere chiamato come se fosse un metodo di istanza del tipo esistente.</span><span class="sxs-lookup"><span data-stu-id="2e20d-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e20d-105">Note</span><span class="sxs-lookup"><span data-stu-id="2e20d-105">Remarks</span></span>  
 <span data-ttu-id="2e20d-106">Un metodo di estensione può essere solo un `Sub` routine o un `Function` procedure.</span><span class="sxs-lookup"><span data-stu-id="2e20d-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="2e20d-107">È possibile definire una proprietà di estensione, un campo o un evento.</span><span class="sxs-lookup"><span data-stu-id="2e20d-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="2e20d-108">Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension()>` dal <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2e20d-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="2e20d-109">Il primo parametro in una definizione di metodo di estensione specifica quale tipo di dati esteso dal metodo.</span><span class="sxs-lookup"><span data-stu-id="2e20d-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="2e20d-110">Quando il metodo viene eseguito, il primo parametro è associato all'istanza del tipo di dati che richiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="2e20d-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e20d-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="2e20d-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2e20d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e20d-112">Description</span></span>  
 <span data-ttu-id="2e20d-113">L'esempio seguente definisce una `Print` estensione per il <xref:System.String> tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="2e20d-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="2e20d-114">Il metodo Usa `Console.WriteLine` per visualizzare una stringa.</span><span class="sxs-lookup"><span data-stu-id="2e20d-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="2e20d-115">Il parametro del `Print` metodo `aString`, stabilisce che il metodo estende il <xref:System.String> classe.</span><span class="sxs-lookup"><span data-stu-id="2e20d-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/StringExtensions.vb#1)]  
  
 <span data-ttu-id="2e20d-116">Si noti che la definizione di metodo di estensione è contrassegnata con l'attributo di estensione `<Extension()>`.</span><span class="sxs-lookup"><span data-stu-id="2e20d-116">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="2e20d-117">Il contrassegno del modulo in cui è definito il metodo è facoltativo, ma ogni metodo di estensione deve essere contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="2e20d-117">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="2e20d-118"><xref:System.Runtime.CompilerServices> deve essere importato per accedere all'attributo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-118"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="2e20d-119">I metodi di estensione possono essere dichiarati solo all'interno dei moduli.</span><span class="sxs-lookup"><span data-stu-id="2e20d-119">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="2e20d-120">Il modulo in cui è definito un metodo di estensione non è in genere, il modulo stesso di quello in cui viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="2e20d-120">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="2e20d-121">Al contrario, viene importato il modulo che contiene il metodo di estensione, se deve essere, per portarlo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="2e20d-121">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="2e20d-122">Dopo il modulo che contiene `Print` è incluso nell'ambito, il metodo può essere chiamato come se fosse un metodo di istanza comune che non accetta argomenti, ad esempio `ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="2e20d-122">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class1.vb#2)]  
  
 <span data-ttu-id="2e20d-123">L'esempio successivo `PrintAndPunctuate`, è anche un'estensione <xref:System.String>, questa volta definito con due parametri.</span><span class="sxs-lookup"><span data-stu-id="2e20d-123">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="2e20d-124">Il primo parametro, `aString`, stabilisce che il metodo di estensione estende <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="2e20d-124">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="2e20d-125">Il secondo parametro, `punc`, deve essere una stringa di segni di punteggiatura che viene passata come argomento quando viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="2e20d-125">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="2e20d-126">Il metodo visualizza la stringa seguita dai segni di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="2e20d-126">The method displays the string followed by the punctuation marks.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class2.vb#3)]  
  
 <span data-ttu-id="2e20d-127">Il metodo viene chiamato inviando un argomento stringa per `punc`: `example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="2e20d-127">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="2e20d-128">L'esempio seguente illustra `Print` e `PrintAndPunctuate` definizione e la chiamata.</span><span class="sxs-lookup"><span data-stu-id="2e20d-128">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="2e20d-129"><xref:System.Runtime.CompilerServices> viene importato nel modulo della definizione per consentire l'accesso all'attributo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-129"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2e20d-130">Codice</span><span class="sxs-lookup"><span data-stu-id="2e20d-130">Code</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
  
    <Extension()>   
    Public Sub Print(ByVal aString As String)  
        Console.WriteLine(aString)  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="2e20d-131">Successivamente, i metodi di estensione vengono inseriti nell'ambito e chiamati.</span><span class="sxs-lookup"><span data-stu-id="2e20d-131">Next, the extension methods are brought into scope and called.</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="2e20d-132">Commenti</span><span class="sxs-lookup"><span data-stu-id="2e20d-132">Comments</span></span>  
 <span data-ttu-id="2e20d-133">Tutto ciò che è necessario essere in grado di eseguire questi passaggi o metodi di estensione simili è che si trovino nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="2e20d-133">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="2e20d-134">Se il modulo che contiene un metodo di estensione è nell'ambito, è visibile in IntelliSense e può essere chiamato come se fosse un metodo di istanza ordinari.</span><span class="sxs-lookup"><span data-stu-id="2e20d-134">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="2e20d-135">Si noti che quando vengono richiamati i metodi, viene inviato alcun argomento per il primo parametro.</span><span class="sxs-lookup"><span data-stu-id="2e20d-135">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="2e20d-136">Parametro `aString` nel precedente metodo definizioni è associato a `example`, l'istanza di `String` che li chiama.</span><span class="sxs-lookup"><span data-stu-id="2e20d-136">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="2e20d-137">Il compilatore userà `example` come argomento inviato al primo parametro.</span><span class="sxs-lookup"><span data-stu-id="2e20d-137">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="2e20d-138">Se viene chiamato un metodo di estensione per un oggetto che è impostato su `Nothing`, viene eseguito il metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-138">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="2e20d-139">Ciò non si applica ai metodi di istanza comune.</span><span class="sxs-lookup"><span data-stu-id="2e20d-139">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="2e20d-140">È possibile controllare in modo esplicito per `Nothing` nel metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-140">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="2e20d-141">Tipi che possono essere estese</span><span class="sxs-lookup"><span data-stu-id="2e20d-141">Types That Can Be Extended</span></span>  
 <span data-ttu-id="2e20d-142">È possibile definire un metodo di estensione nella maggior parte dei tipi che possono essere rappresentati in un elenco di parametri di Visual Basic, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e20d-142">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
-   <span data-ttu-id="2e20d-143">Classi (tipi riferimento)</span><span class="sxs-lookup"><span data-stu-id="2e20d-143">Classes (reference types)</span></span>  
  
-   <span data-ttu-id="2e20d-144">Strutture (tipi di valore)</span><span class="sxs-lookup"><span data-stu-id="2e20d-144">Structures (value types)</span></span>  
  
-   <span data-ttu-id="2e20d-145">Interfacce</span><span class="sxs-lookup"><span data-stu-id="2e20d-145">Interfaces</span></span>  
  
-   <span data-ttu-id="2e20d-146">Delegati</span><span class="sxs-lookup"><span data-stu-id="2e20d-146">Delegates</span></span>  
  
-   <span data-ttu-id="2e20d-147">Argomenti ByRef e ByVal</span><span class="sxs-lookup"><span data-stu-id="2e20d-147">ByRef and ByVal arguments</span></span>  
  
-   <span data-ttu-id="2e20d-148">Parametri di metodo generico</span><span class="sxs-lookup"><span data-stu-id="2e20d-148">Generic method parameters</span></span>  
  
-   <span data-ttu-id="2e20d-149">Matrici</span><span class="sxs-lookup"><span data-stu-id="2e20d-149">Arrays</span></span>  
  
 <span data-ttu-id="2e20d-150">Poiché il primo parametro specifica il tipo di dati esteso dal metodo di estensione, è obbligatorio e non può essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="2e20d-150">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="2e20d-151">Per questo motivo `Optional` parametri e `ParamArray` parametri non possono essere il primo parametro nell'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="2e20d-151">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="2e20d-152">I metodi di estensione non sono considerati nell'associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="2e20d-152">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="2e20d-153">Nell'esempio seguente, l'istruzione `anObject.PrintMe()` genera una <xref:System.MissingMemberException> eccezione, la stessa eccezione sarebbe visualizzata se il secondo `PrintMe` definizione di metodo di estensione sono stati eliminati.</span><span class="sxs-lookup"><span data-stu-id="2e20d-153">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class6.vb#9)]  
  
## <a name="best-practices"></a><span data-ttu-id="2e20d-154">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="2e20d-154">Best Practices</span></span>  
 <span data-ttu-id="2e20d-155">I metodi di estensione forniscono un modo pratico e potente per estendere un tipo esistente.</span><span class="sxs-lookup"><span data-stu-id="2e20d-155">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="2e20d-156">Tuttavia, per poterli utilizzare correttamente, esistono alcuni aspetti da considerare.</span><span class="sxs-lookup"><span data-stu-id="2e20d-156">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="2e20d-157">Queste considerazioni si applicano principalmente gli autori delle librerie di classi, ma che potrebbero influire su qualsiasi applicazione che usa i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-157">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="2e20d-158">In generale, i metodi di estensione aggiunti ai tipi che non si possiede sono più vulnerabili dei metodi di estensione aggiunti ai tipi di cui si controllano.</span><span class="sxs-lookup"><span data-stu-id="2e20d-158">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="2e20d-159">Può verificarsi una serie di operazioni nelle classi non si è proprietari che possono interferire con i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-159">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
-   <span data-ttu-id="2e20d-160">Se è presente alcun membro di istanza accessibile ha una firma compatibile con gli argomenti dell'istruzione chiamante, con nessuna conversione narrowing richiesto dall'argomento al parametro, verrà utilizzato il metodo di istanza preferenza rispetto a qualsiasi metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-160">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="2e20d-161">Pertanto, se un metodo di istanza appropriato viene aggiunto a una classe a un certo punto, un membro di estensione esistente che affidano potrebbe diventare inaccessibile.</span><span class="sxs-lookup"><span data-stu-id="2e20d-161">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
-   <span data-ttu-id="2e20d-162">L'autore di un metodo di estensione non è possibile impedire agli altri programmatori di scrivere metodi di estensione in conflitto che possono avere la precedenza sull'estensione originale.</span><span class="sxs-lookup"><span data-stu-id="2e20d-162">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
-   <span data-ttu-id="2e20d-163">È possibile migliorare la robustezza inserendo i metodi di estensione nel rispettivo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="2e20d-163">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="2e20d-164">La libreria può quindi includere uno spazio dei nomi o escluderlo oppure effettuare una selezione tra gli spazi dei nomi, separatamente dal resto della libreria.</span><span class="sxs-lookup"><span data-stu-id="2e20d-164">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
-   <span data-ttu-id="2e20d-165">Potrebbe essere più sicuro estendere le interfacce di cui è possibile estendere le classi, soprattutto se non si possiede l'interfaccia o classe.</span><span class="sxs-lookup"><span data-stu-id="2e20d-165">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="2e20d-166">Una modifica in un'interfaccia influisce su ogni classe che lo implementa.</span><span class="sxs-lookup"><span data-stu-id="2e20d-166">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="2e20d-167">Pertanto, l'autore potrebbe essere meno probabile che aggiungere o modificare i metodi in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2e20d-167">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="2e20d-168">Tuttavia, se una classe implementa due interfacce con metodi di estensione con la stessa firma, nessuno dei due metodi di estensione sono visibili.</span><span class="sxs-lookup"><span data-stu-id="2e20d-168">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
-   <span data-ttu-id="2e20d-169">Estendere il tipo più specifico, che è possibile.</span><span class="sxs-lookup"><span data-stu-id="2e20d-169">Extend the most specific type you can.</span></span> <span data-ttu-id="2e20d-170">In una gerarchia di tipi, se si seleziona un tipo dal quale sono derivati molti altri tipi, sono presenti livelli di possibilità per l'introduzione di metodi di istanza o altri metodi di estensione che potrebbero interferire con i propri.</span><span class="sxs-lookup"><span data-stu-id="2e20d-170">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="2e20d-171">I metodi di estensione, metodi di istanza e proprietà</span><span class="sxs-lookup"><span data-stu-id="2e20d-171">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="2e20d-172">Quando un metodo di istanza inclusi nell'ambito ha una firma compatibile con gli argomenti di un'istruzione di chiamata, il metodo di istanza viene preferito a qualsiasi metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-172">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="2e20d-173">Il metodo di istanza ha la precedenza anche se il metodo di estensione è una corrispondenza migliore.</span><span class="sxs-lookup"><span data-stu-id="2e20d-173">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="2e20d-174">Nell'esempio riportato di seguito `ExampleClass` contiene un metodo di istanza denominato `ExampleMethod` che ha un parametro di tipo `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2e20d-174">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="2e20d-175">Metodo di estensione `ExampleMethod` estende `ExampleClass`, e ha un parametro di tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="2e20d-175">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#4)]  
  
 <span data-ttu-id="2e20d-176">La prima chiamata a `ExampleMethod` nel codice seguente chiama il metodo di estensione, in quanto `arg1` viene `Long` ed è compatibile solo con il `Long` parametro nel metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="2e20d-176">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="2e20d-177">La seconda chiamata a `ExampleMethod` ha un `Integer` argomento, `arg2`, e chiama il metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="2e20d-177">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class4.vb#5)]  
  
 <span data-ttu-id="2e20d-178">Invertire ora i tipi di dati dei parametri nei due metodi:</span><span class="sxs-lookup"><span data-stu-id="2e20d-178">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#6)]  
  
 <span data-ttu-id="2e20d-179">Questa volta il codice in `Main` chiama il metodo di istanza due volte.</span><span class="sxs-lookup"><span data-stu-id="2e20d-179">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="2e20d-180">Infatti, entrambi `arg1` e `arg2` hanno una conversione widening `Long`, e il metodo di istanza ha la precedenza sul metodo di estensione in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="2e20d-180">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Class5.vb#7)]  
  
 <span data-ttu-id="2e20d-181">Pertanto, un metodo di estensione non è possibile sostituire un metodo di istanza esistenti.</span><span class="sxs-lookup"><span data-stu-id="2e20d-181">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="2e20d-182">Tuttavia, quando un metodo di estensione ha lo stesso nome di un metodo di istanza ma le firme non sono in conflitto, entrambi i metodi accessibili.</span><span class="sxs-lookup"><span data-stu-id="2e20d-182">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="2e20d-183">Ad esempio, se classe `ExampleClass` contiene un metodo denominato `ExampleMethod` che non accetta argomenti, i metodi di estensione con lo stesso nome ma sono consentite firme diverse, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2e20d-183">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 [!code-vb[VbVbalrExtensionMethods#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrExtensionMethods/VB/Module3.vb#8)]  
  
 <span data-ttu-id="2e20d-184">Come indicato di seguito è riportato l'output da questo codice:</span><span class="sxs-lookup"><span data-stu-id="2e20d-184">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="2e20d-185">La situazione è più semplice con proprietà: se un metodo di estensione ha lo stesso nome come una proprietà di classe che estende, il metodo di estensione non è visibile e non è accessibile.</span><span class="sxs-lookup"><span data-stu-id="2e20d-185">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="2e20d-186">Precedenza nei metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="2e20d-186">Extension Method Precedence</span></span>  
 <span data-ttu-id="2e20d-187">Quando due metodi di estensione che hanno firme identiche sono nell'ambito e accessibili, verrà richiamato quello con priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="2e20d-187">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="2e20d-188">Precedenza di un metodo di estensione è basata sul meccanismo utilizzato per portare il metodo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="2e20d-188">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="2e20d-189">Nell'elenco seguente mostra la gerarchia di precedenza, dal maggiore al minore.</span><span class="sxs-lookup"><span data-stu-id="2e20d-189">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1.  <span data-ttu-id="2e20d-190">Metodi di estensione definiti all'interno del modulo corrente.</span><span class="sxs-lookup"><span data-stu-id="2e20d-190">Extension methods defined inside the current module.</span></span>  
  
2.  <span data-ttu-id="2e20d-191">Metodi di estensione definiti all'interno di dati tipi nella spazio dei nomi corrente o uno qualsiasi dei relativi elementi padre, gli spazi dei nomi figlio con precedenza maggiore rispetto a spazi dei nomi padre.</span><span class="sxs-lookup"><span data-stu-id="2e20d-191">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3.  <span data-ttu-id="2e20d-192">Metodi di estensione definiti in qualsiasi importazione di tipo nel file corrente.</span><span class="sxs-lookup"><span data-stu-id="2e20d-192">Extension methods defined inside any type imports in the current file.</span></span>  
  
4.  <span data-ttu-id="2e20d-193">Metodi di estensione definiti in qualsiasi importazione dello spazio dei nomi nel file corrente.</span><span class="sxs-lookup"><span data-stu-id="2e20d-193">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5.  <span data-ttu-id="2e20d-194">Metodi di estensione definiti in qualsiasi importazione di tipi a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="2e20d-194">Extension methods defined inside any project-level type imports.</span></span>  
  
6.  <span data-ttu-id="2e20d-195">Metodi di estensione definiti in qualsiasi importazione dello spazio dei nomi a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="2e20d-195">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="2e20d-196">Se la precedenza non risolve l'ambiguità, è possibile usare il nome completo per specificare il metodo che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="2e20d-196">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="2e20d-197">Se il `Print` metodo nell'esempio precedente viene definito in un modulo denominato `StringExtensions`, specificare il nome completo viene `StringExtensions.Print(example)` invece di `example.Print()`.</span><span class="sxs-lookup"><span data-stu-id="2e20d-197">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e20d-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e20d-198">See also</span></span>

- <xref:System.Runtime.CompilerServices>
- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [<span data-ttu-id="2e20d-199">Metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="2e20d-199">Extension Methods</span></span>](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [<span data-ttu-id="2e20d-200">Istruzione Module</span><span class="sxs-lookup"><span data-stu-id="2e20d-200">Module Statement</span></span>](../../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="2e20d-201">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="2e20d-201">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="2e20d-202">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="2e20d-202">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="2e20d-203">Matrici di parametri</span><span class="sxs-lookup"><span data-stu-id="2e20d-203">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="2e20d-204">Panoramica degli attributi</span><span class="sxs-lookup"><span data-stu-id="2e20d-204">Attributes overview</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [<span data-ttu-id="2e20d-205">Scope in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2e20d-205">Scope in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
