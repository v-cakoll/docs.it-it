---
title: Metodi di estensione (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ExtensionMethods
dev_langs:
- VB
helpviewer_keywords:
- extending data types
- extension methods [Visual Basic]
ms.assetid: b8020aae-374d-46a9-bcb7-8cc2390b93b6
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 0705929da72bcb3001228a90bbb9d5ba7c248bf7
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="extension-methods-visual-basic"></a><span data-ttu-id="c0183-102">Metodi di estensione (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0183-102">Extension Methods (Visual Basic)</span></span>
<span data-ttu-id="c0183-103">Metodi di estensione consentono agli sviluppatori di aggiungere funzionalità personalizzate ai tipi di dati che sono già definiti senza creare un nuovo tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="c0183-103">Extension methods enable developers to add custom functionality to data types that are already defined without creating a new derived type.</span></span> <span data-ttu-id="c0183-104">Metodi di estensione consentono di scrivere un metodo che può essere chiamato come se fosse un metodo di istanza del tipo esistente.</span><span class="sxs-lookup"><span data-stu-id="c0183-104">Extension methods make it possible to write a method that can be called as if it were an instance method of the existing type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0183-105">Note</span><span class="sxs-lookup"><span data-stu-id="c0183-105">Remarks</span></span>  
 <span data-ttu-id="c0183-106">Un metodo di estensione può essere solo un `Sub` procedura o una `Function` procedura.</span><span class="sxs-lookup"><span data-stu-id="c0183-106">An extension method can be only a `Sub` procedure or a `Function` procedure.</span></span> <span data-ttu-id="c0183-107">È possibile definire una proprietà di estensione, campo o dell'evento.</span><span class="sxs-lookup"><span data-stu-id="c0183-107">You cannot define an extension property, field, or event.</span></span> <span data-ttu-id="c0183-108">Tutti i metodi di estensione devono essere contrassegnati con l'attributo di estensione `<Extension()>` dal <xref:System.Runtime.CompilerServices?displayProperty=fullName>dello spazio dei nomi.</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c0183-108">All extension methods must be marked with the extension attribute `<Extension()>` from the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace.</span></span>  
  
 <span data-ttu-id="c0183-109">Il primo parametro in una definizione di metodo di estensione specifica quale tipo di dati si estende il metodo.</span><span class="sxs-lookup"><span data-stu-id="c0183-109">The first parameter in an extension method definition specifies which data type the method extends.</span></span> <span data-ttu-id="c0183-110">Quando viene eseguito il metodo, il primo parametro è associato all'istanza del tipo di dati che richiama il metodo.</span><span class="sxs-lookup"><span data-stu-id="c0183-110">When the method is run, the first parameter is bound to the instance of the data type that invokes the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0183-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="c0183-111">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c0183-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c0183-112">Description</span></span>  
 <span data-ttu-id="c0183-113">L'esempio seguente definisce una `Print` estensione per il <xref:System.String>tipo di dati.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="c0183-113">The following example defines a `Print` extension to the <xref:System.String> data type.</span></span> <span data-ttu-id="c0183-114">Il metodo utilizza `Console.WriteLine` per visualizzare una stringa.</span><span class="sxs-lookup"><span data-stu-id="c0183-114">The method uses `Console.WriteLine` to display a string.</span></span> <span data-ttu-id="c0183-115">Il parametro di `Print` (metodo), `aString`, stabilisce che il metodo estende la <xref:System.String>classe.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="c0183-115">The parameter of the `Print` method, `aString`, establishes that the method extends the <xref:System.String> class.</span></span>  
  
 <span data-ttu-id="c0183-116">[!code-vb[VbVbalrExtensionMethods n.&1;](./codesnippet/VisualBasic/extension-methods_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-116">[!code-vb[VbVbalrExtensionMethods#1](./codesnippet/VisualBasic/extension-methods_1.vb)]</span></span>  
  
 <span data-ttu-id="c0183-117">Si noti che la definizione di metodo di estensione è contrassegnata con l'attributo di estensione `<Extension()>`.</span><span class="sxs-lookup"><span data-stu-id="c0183-117">Notice that the extension method definition is marked with the extension attribute `<Extension()>`.</span></span> <span data-ttu-id="c0183-118">Il contrassegno del modulo in cui è definito il metodo è facoltativo, ma ogni metodo di estensione deve essere contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="c0183-118">Marking the module in which the method is defined is optional, but each extension method must be marked.</span></span> <span data-ttu-id="c0183-119"><xref:System.Runtime.CompilerServices>deve essere importato per accedere all'attributo di estensione.</xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="c0183-119"><xref:System.Runtime.CompilerServices> must be imported in order to access the extension attribute.</span></span>  
  
 <span data-ttu-id="c0183-120">Metodi di estensione possono essere dichiarati solo all'interno di moduli.</span><span class="sxs-lookup"><span data-stu-id="c0183-120">Extension methods can be declared only within modules.</span></span> <span data-ttu-id="c0183-121">Il modulo in cui è definito un metodo di estensione non è in genere, il modulo stesso di quello in cui viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="c0183-121">Typically, the module in which an extension method is defined is not the same module as the one in which it is called.</span></span> <span data-ttu-id="c0183-122">Al contrario, viene importato il modulo che contiene il metodo di estensione, se deve essere, in modo che sia nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="c0183-122">Instead, the module that contains the extension method is imported, if it needs to be, to bring it into scope.</span></span> <span data-ttu-id="c0183-123">Dopo il modulo che contiene `Print` è nell'ambito, il metodo può essere chiamato come se fosse un metodo di istanza comune che non accetta argomenti, ad esempio `ToUpper`:</span><span class="sxs-lookup"><span data-stu-id="c0183-123">After the module that contains `Print` is in scope, the method can be called as if it were an ordinary instance method that takes no arguments, such as `ToUpper`:</span></span>  
  
 <span data-ttu-id="c0183-124">[!code-vb[VbVbalrExtensionMethods n.&2;](./codesnippet/VisualBasic/extension-methods_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-124">[!code-vb[VbVbalrExtensionMethods#2](./codesnippet/VisualBasic/extension-methods_2.vb)]</span></span>  
  
 <span data-ttu-id="c0183-125">Nell'esempio successivo viene `PrintAndPunctuate`, è anche un'estensione di <xref:System.String>, in questo caso definito con due parametri.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="c0183-125">The next example, `PrintAndPunctuate`, is also an extension to <xref:System.String>, this time defined with two parameters.</span></span> <span data-ttu-id="c0183-126">Il primo parametro, `aString`, stabilisce che il metodo di estensione estende <xref:System.String>.</xref:System.String></span><span class="sxs-lookup"><span data-stu-id="c0183-126">The first parameter, `aString`, establishes that the extension method extends <xref:System.String>.</span></span> <span data-ttu-id="c0183-127">Il secondo parametro, `punc`, deve essere una stringa di segni di punteggiatura che viene passata come argomento quando viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="c0183-127">The second parameter, `punc`, is intended to be a string of punctuation marks that is passed in as an argument when the method is called.</span></span> <span data-ttu-id="c0183-128">Il metodo visualizza la stringa seguita da segni di punteggiatura.</span><span class="sxs-lookup"><span data-stu-id="c0183-128">The method displays the string followed by the punctuation marks.</span></span>  
  
 <span data-ttu-id="c0183-129">[!code-vb[VbVbalrExtensionMethods n.&3;](./codesnippet/VisualBasic/extension-methods_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-129">[!code-vb[VbVbalrExtensionMethods#3](./codesnippet/VisualBasic/extension-methods_3.vb)]</span></span>  
  
 <span data-ttu-id="c0183-130">Viene chiamato il metodo mediante l'invio di un argomento di stringa per `punc`:`example.PrintAndPunctuate(".")`</span><span class="sxs-lookup"><span data-stu-id="c0183-130">The method is called by sending in a string argument for `punc`: `example.PrintAndPunctuate(".")`</span></span>  
  
 <span data-ttu-id="c0183-131">Nell'esempio seguente `Print` e `PrintAndPunctuate` definito e chiamato.</span><span class="sxs-lookup"><span data-stu-id="c0183-131">The following example shows `Print` and `PrintAndPunctuate` defined and called.</span></span> <span data-ttu-id="c0183-132"><xref:System.Runtime.CompilerServices>viene importato nel modulo della definizione per consentire l'accesso all'attributo di estensione.</xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="c0183-132"><xref:System.Runtime.CompilerServices> is imported in the definition module in order to enable access to the extension attribute.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c0183-133">Codice</span><span class="sxs-lookup"><span data-stu-id="c0183-133">Code</span></span>  
  
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
  
 <span data-ttu-id="c0183-134">Successivamente, i metodi di estensione vengono inseriti nell'ambito e chiamati.</span><span class="sxs-lookup"><span data-stu-id="c0183-134">Next, the extension methods are brought into scope and called.</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="c0183-135">Commenti</span><span class="sxs-lookup"><span data-stu-id="c0183-135">Comments</span></span>  
 <span data-ttu-id="c0183-136">Tutto ciò che è necessario essere in grado di eseguire questi o metodi di estensione simili è che si trovino nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="c0183-136">All that is required to be able to run these or similar extension methods is that they be in scope.</span></span> <span data-ttu-id="c0183-137">Se il modulo che contiene un metodo di estensione è nell'ambito, è visibile in IntelliSense e può essere chiamato come se fosse un metodo di istanza comune.</span><span class="sxs-lookup"><span data-stu-id="c0183-137">If the module that contains an extension method is in scope, it is visible in IntelliSense and can be called as if it were an ordinary instance method.</span></span>  
  
 <span data-ttu-id="c0183-138">Si noti che, quando vengono richiamati i metodi, nessun argomento viene inviato per il primo parametro.</span><span class="sxs-lookup"><span data-stu-id="c0183-138">Notice that when the methods are invoked, no argument is sent in for the first parameter.</span></span> <span data-ttu-id="c0183-139">Parametro `aString` nel precedente metodo definizioni è associato a `example`, l'istanza di `String` che le chiama.</span><span class="sxs-lookup"><span data-stu-id="c0183-139">Parameter `aString` in the previous method definitions is bound to `example`, the instance of `String` that calls them.</span></span> <span data-ttu-id="c0183-140">Il compilatore utilizzerà `example` come argomento inviato al primo parametro.</span><span class="sxs-lookup"><span data-stu-id="c0183-140">The compiler will use `example` as the argument sent to the first parameter.</span></span>  
  
 <span data-ttu-id="c0183-141">Se viene chiamato un metodo di estensione per un oggetto che è impostato su `Nothing`, viene eseguito il metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="c0183-141">If an extension method is called for an object that is set to `Nothing`, the extension method executes.</span></span> <span data-ttu-id="c0183-142">Questo non è applicabile ai metodi di istanza comune.</span><span class="sxs-lookup"><span data-stu-id="c0183-142">This does not apply to ordinary instance methods.</span></span> <span data-ttu-id="c0183-143">È possibile controllare in modo esplicito di `Nothing` nel metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="c0183-143">You can explicitly check for `Nothing` in the extension method.</span></span>  
  
## <a name="types-that-can-be-extended"></a><span data-ttu-id="c0183-144">Tipi che possono essere estesi</span><span class="sxs-lookup"><span data-stu-id="c0183-144">Types That Can Be Extended</span></span>  
 <span data-ttu-id="c0183-145">È possibile definire un metodo di estensione nella maggior parte dei tipi che possono essere rappresentati in un elenco di parametri di Visual Basic, inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0183-145">You can define an extension method on most types that can be represented in a Visual Basic parameter list, including the following:</span></span>  
  
-   <span data-ttu-id="c0183-146">Classi (tipi di riferimento)</span><span class="sxs-lookup"><span data-stu-id="c0183-146">Classes (reference types)</span></span>  
  
-   <span data-ttu-id="c0183-147">Strutture (tipi valore)</span><span class="sxs-lookup"><span data-stu-id="c0183-147">Structures (value types)</span></span>  
  
-   <span data-ttu-id="c0183-148">Interfacce</span><span class="sxs-lookup"><span data-stu-id="c0183-148">Interfaces</span></span>  
  
-   <span data-ttu-id="c0183-149">Delegati</span><span class="sxs-lookup"><span data-stu-id="c0183-149">Delegates</span></span>  
  
-   <span data-ttu-id="c0183-150">Argomenti ByRef e ByVal</span><span class="sxs-lookup"><span data-stu-id="c0183-150">ByRef and ByVal arguments</span></span>  
  
-   <span data-ttu-id="c0183-151">Parametri di metodo generico</span><span class="sxs-lookup"><span data-stu-id="c0183-151">Generic method parameters</span></span>  
  
-   <span data-ttu-id="c0183-152">Matrici</span><span class="sxs-lookup"><span data-stu-id="c0183-152">Arrays</span></span>  
  
 <span data-ttu-id="c0183-153">Poiché il primo parametro specifica il tipo di dati che estende il metodo di estensione, è obbligatorio e non può essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c0183-153">Because the first parameter specifies the data type that the extension method extends, it is required and cannot be optional.</span></span> <span data-ttu-id="c0183-154">Per questo motivo, `Optional` parametri e `ParamArray` i parametri non possono essere il primo parametro nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="c0183-154">For that reason, `Optional` parameters and `ParamArray` parameters cannot be the first parameter in the parameter list.</span></span>  
  
 <span data-ttu-id="c0183-155">Metodi di estensione non sono considerati in associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="c0183-155">Extension methods are not considered in late binding.</span></span> <span data-ttu-id="c0183-156">Nell'esempio seguente, l'istruzione `anObject.PrintMe()` genera un <xref:System.MissingMemberException>eccezione, la stessa eccezione verrà visualizzato se il secondo `PrintMe` definizione di metodo di estensione sono stati eliminati.</xref:System.MissingMemberException></span><span class="sxs-lookup"><span data-stu-id="c0183-156">In the following example, the statement `anObject.PrintMe()` raises a <xref:System.MissingMemberException> exception, the same exception you would see if the second `PrintMe` extension method definition were deleted.</span></span>  
  
 <span data-ttu-id="c0183-157">[!code-vb[9 VbVbalrExtensionMethods](./codesnippet/VisualBasic/extension-methods_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-157">[!code-vb[VbVbalrExtensionMethods#9](./codesnippet/VisualBasic/extension-methods_4.vb)]</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="c0183-158">Suggerimenti</span><span class="sxs-lookup"><span data-stu-id="c0183-158">Best Practices</span></span>  
 <span data-ttu-id="c0183-159">Metodi di estensione forniscono un modo pratico e potente per estendere un tipo esistente.</span><span class="sxs-lookup"><span data-stu-id="c0183-159">Extension methods provide a convenient and powerful way to extend an existing type.</span></span> <span data-ttu-id="c0183-160">Tuttavia, per poterli utilizzare correttamente, esistono alcuni punti da considerare.</span><span class="sxs-lookup"><span data-stu-id="c0183-160">However, to use them successfully, there are some points to consider.</span></span> <span data-ttu-id="c0183-161">Queste considerazioni si applicano principalmente per gli autori di librerie di classi, ma che potrebbero influire su qualsiasi applicazione che utilizza i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="c0183-161">These considerations apply mainly to authors of class libraries, but they might affect any application that uses extension methods.</span></span>  
  
 <span data-ttu-id="c0183-162">In generale, i metodi di estensione che aggiungono ai tipi che non si è proprietari sono più vulnerabili rispetto ai metodi di estensione aggiunti ai tipi che è possibile controllare.</span><span class="sxs-lookup"><span data-stu-id="c0183-162">Most generally, extension methods that you add to types that you do not own are more vulnerable than extension methods added to types that you control.</span></span> <span data-ttu-id="c0183-163">Può verificarsi una serie di operazioni nelle classi non si è proprietari che possono interferire con i metodi di estensione.</span><span class="sxs-lookup"><span data-stu-id="c0183-163">A number of things can occur in classes you do not own that can interfere with your extension methods.</span></span>  
  
-   <span data-ttu-id="c0183-164">Se un membro di istanza accessibile con una firma compatibile con gli argomenti nell'istruzione di chiamata, non le conversioni necessarie dall'argomento al parametro, verrà utilizzato il metodo di istanza a qualsiasi metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="c0183-164">If any accessible instance member exists that has a signature that is compatible with the arguments in the calling statement, with no narrowing conversions required from argument to parameter, the instance method will be used in preference to any extension method.</span></span> <span data-ttu-id="c0183-165">Pertanto, se un metodo di istanza appropriato viene aggiunto a una classe a un certo punto, un membro esistente di estensione che affidano potrebbe diventare inaccessibile.</span><span class="sxs-lookup"><span data-stu-id="c0183-165">Therefore, if an appropriate instance method is added to a class at some point, an existing extension member that you rely on may become inaccessible.</span></span>  
  
-   <span data-ttu-id="c0183-166">L'autore di un metodo di estensione non può impedire agli altri programmatori di scrivere i metodi di estensione in conflitto che possono avere la precedenza sull'estensione originale.</span><span class="sxs-lookup"><span data-stu-id="c0183-166">The author of an extension method cannot prevent other programmers from writing conflicting extension methods that may have precedence over the original extension.</span></span>  
  
-   <span data-ttu-id="c0183-167">È possibile migliorare la robustezza inserendo i metodi di estensione nel proprio spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="c0183-167">You can improve robustness by putting extension methods in their own namespace.</span></span> <span data-ttu-id="c0183-168">I consumer della libreria possono includere uno spazio dei nomi o escluderlo o selezionare tra gli spazi dei nomi, separatamente dal resto della libreria.</span><span class="sxs-lookup"><span data-stu-id="c0183-168">Consumers of your library can then include a namespace or exclude it, or select among namespaces, separately from the rest of the library.</span></span>  
  
-   <span data-ttu-id="c0183-169">Potrebbe essere preferibile estendere interfacce piuttosto che di estendere le classi, soprattutto se non si dispone di interfaccia o classe.</span><span class="sxs-lookup"><span data-stu-id="c0183-169">It may be safer to extend interfaces than it is to extend classes, especially if you do not own the interface or class.</span></span> <span data-ttu-id="c0183-170">Una modifica in un'interfaccia influisce su ogni classe che lo implementa.</span><span class="sxs-lookup"><span data-stu-id="c0183-170">A change in an interface affects every class that implements it.</span></span> <span data-ttu-id="c0183-171">Pertanto, l'autore potrebbe essere meno probabile che aggiungere o modificare i metodi in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="c0183-171">Therefore, the author may be less likely to add or change methods in an interface.</span></span> <span data-ttu-id="c0183-172">Tuttavia, se una classe implementa due interfacce che dispongono di metodi di estensione con la stessa firma, nessuno dei due metodi di estensione sono visibili.</span><span class="sxs-lookup"><span data-stu-id="c0183-172">However, if a class implements two interfaces that have extension methods with the same signature, neither extension method is visible.</span></span>  
  
-   <span data-ttu-id="c0183-173">Estendere il tipo più specifico che possibile.</span><span class="sxs-lookup"><span data-stu-id="c0183-173">Extend the most specific type you can.</span></span> <span data-ttu-id="c0183-174">In una gerarchia di tipi, se si seleziona un tipo da cui derivano molti altri tipi, sono disponibili livelli di possibilità per l'introduzione di metodi di istanza o altri metodi di estensione che potrebbero interferire con i propri.</span><span class="sxs-lookup"><span data-stu-id="c0183-174">In a hierarchy of types, if you select a type from which many other types are derived, there are layers of possibilities for the introduction of instance methods or other extension methods that might interfere with yours.</span></span>  
  
## <a name="extension-methods-instance-methods-and-properties"></a><span data-ttu-id="c0183-175">Proprietà, metodi di istanza e metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="c0183-175">Extension Methods, Instance Methods, and Properties</span></span>  
 <span data-ttu-id="c0183-176">Quando un metodo di istanza nell'ambito ha una firma compatibile con gli argomenti di un'istruzione di chiamata, viene scelto il metodo di istanza a qualsiasi metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="c0183-176">When an in-scope instance method has a signature that is compatible with the arguments of a calling statement, the instance method is chosen in preference to any extension method.</span></span> <span data-ttu-id="c0183-177">Il metodo di istanza ha la precedenza anche se il metodo di estensione è una corrispondenza migliore.</span><span class="sxs-lookup"><span data-stu-id="c0183-177">The instance method has precedence even if the extension method is a better match.</span></span> <span data-ttu-id="c0183-178">Nell'esempio seguente, `ExampleClass` contiene un metodo di istanza denominato `ExampleMethod` che ha un parametro di tipo `Integer`.</span><span class="sxs-lookup"><span data-stu-id="c0183-178">In the following example, `ExampleClass` contains an instance method named `ExampleMethod` that has one parameter of type `Integer`.</span></span> <span data-ttu-id="c0183-179">Metodo di estensione `ExampleMethod` estende `ExampleClass`, e ha un parametro di tipo `Long`.</span><span class="sxs-lookup"><span data-stu-id="c0183-179">Extension method `ExampleMethod` extends `ExampleClass`, and has one parameter of type `Long`.</span></span>  
  
 <span data-ttu-id="c0183-180">[!code-vb[VbVbalrExtensionMethods n.&4;](./codesnippet/VisualBasic/extension-methods_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-180">[!code-vb[VbVbalrExtensionMethods#4](./codesnippet/VisualBasic/extension-methods_5.vb)]</span></span>  
  
 <span data-ttu-id="c0183-181">La prima chiamata a `ExampleMethod` nel codice seguente chiama il metodo di estensione, poiché `arg1` è `Long` ed è compatibile solo con il `Long` parametro nel metodo di estensione.</span><span class="sxs-lookup"><span data-stu-id="c0183-181">The first call to `ExampleMethod` in the following code calls the extension method, because `arg1` is `Long` and is compatible only with the `Long` parameter in the extension method.</span></span> <span data-ttu-id="c0183-182">La seconda chiamata a `ExampleMethod` ha un `Integer` argomento, `arg2`, e chiama il metodo di istanza.</span><span class="sxs-lookup"><span data-stu-id="c0183-182">The second call to `ExampleMethod` has an `Integer` argument, `arg2`, and it calls the instance method.</span></span>  
  
 <span data-ttu-id="c0183-183">[!code-vb[VbVbalrExtensionMethods n.&5;](./codesnippet/VisualBasic/extension-methods_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-183">[!code-vb[VbVbalrExtensionMethods#5](./codesnippet/VisualBasic/extension-methods_6.vb)]</span></span>  
  
 <span data-ttu-id="c0183-184">Invertire ora i tipi di dati dei parametri nei due metodi:</span><span class="sxs-lookup"><span data-stu-id="c0183-184">Now reverse the data types of the parameters in the two methods:</span></span>  
  
 <span data-ttu-id="c0183-185">[!code-vb[6 VbVbalrExtensionMethods](./codesnippet/VisualBasic/extension-methods_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-185">[!code-vb[VbVbalrExtensionMethods#6](./codesnippet/VisualBasic/extension-methods_7.vb)]</span></span>  
  
 <span data-ttu-id="c0183-186">Questa volta il codice in `Main` chiama il metodo di istanza due volte.</span><span class="sxs-lookup"><span data-stu-id="c0183-186">This time the code in `Main` calls the instance method both times.</span></span> <span data-ttu-id="c0183-187">Infatti, entrambi `arg1` e `arg2` dispone di una conversione di ampliamento per `Long`, e il metodo di istanza ha la precedenza sul metodo di estensione in entrambi i casi.</span><span class="sxs-lookup"><span data-stu-id="c0183-187">This is because both `arg1` and `arg2` have a widening conversion to `Long`, and the instance method takes precedence over the extension method in both cases.</span></span>  
  
 <span data-ttu-id="c0183-188">[!code-vb[VbVbalrExtensionMethods&#7;](./codesnippet/VisualBasic/extension-methods_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-188">[!code-vb[VbVbalrExtensionMethods#7](./codesnippet/VisualBasic/extension-methods_8.vb)]</span></span>  
  
 <span data-ttu-id="c0183-189">Di conseguenza, un metodo di estensione non può sostituire un metodo di istanza esistenti.</span><span class="sxs-lookup"><span data-stu-id="c0183-189">Therefore, an extension method cannot replace an existing instance method.</span></span> <span data-ttu-id="c0183-190">Tuttavia, quando un metodo di estensione ha lo stesso nome di un metodo di istanza, ma le firme non sono in conflitto, entrambi i metodi sono accessibili.</span><span class="sxs-lookup"><span data-stu-id="c0183-190">However, when an extension method has the same name as an instance method but the signatures do not conflict, both methods can be accessed.</span></span> <span data-ttu-id="c0183-191">Ad esempio, se classe `ExampleClass` contiene un metodo denominato `ExampleMethod` che non accetta argomenti, i metodi di estensione con lo stesso nome ma sono consentite firme diverse, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="c0183-191">For example, if class `ExampleClass` contains a method named `ExampleMethod` that takes no arguments, extension methods with the same name but different signatures are permitted, as shown in the following code.</span></span>  
  
 <span data-ttu-id="c0183-192">[!code-vb[VbVbalrExtensionMethods n.&8;](./codesnippet/VisualBasic/extension-methods_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="c0183-192">[!code-vb[VbVbalrExtensionMethods#8](./codesnippet/VisualBasic/extension-methods_9.vb)]</span></span>  
  
 <span data-ttu-id="c0183-193">L'output da questo codice è come segue:</span><span class="sxs-lookup"><span data-stu-id="c0183-193">The output from this code is as follows:</span></span>  
  
 `Extension method`  
  
 `Instance method`  
  
 <span data-ttu-id="c0183-194">La situazione è più semplice con le proprietà: se un metodo di estensione ha lo stesso nome di una proprietà della classe che estende, il metodo di estensione non è visibile e non è accessibile.</span><span class="sxs-lookup"><span data-stu-id="c0183-194">The situation is simpler with properties: if an extension method has the same name as a property of the class it extends, the extension method is not visible and cannot be accessed.</span></span>  
  
## <a name="extension-method-precedence"></a><span data-ttu-id="c0183-195">Precedenza nei metodi di estensione</span><span class="sxs-lookup"><span data-stu-id="c0183-195">Extension Method Precedence</span></span>  
 <span data-ttu-id="c0183-196">Quando due metodi di estensione che presentano firme identiche incluse nell'ambito e accessibile, verrà richiamato quello con priorità più alta.</span><span class="sxs-lookup"><span data-stu-id="c0183-196">When two extension methods that have identical signatures are in scope and accessible, the one with higher precedence will be invoked.</span></span> <span data-ttu-id="c0183-197">La priorità di un metodo di estensione è basata sul meccanismo utilizzato per portare il metodo nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="c0183-197">An extension method's precedence is based on the mechanism used to bring the method into scope.</span></span> <span data-ttu-id="c0183-198">Nell'elenco seguente viene illustrata la gerarchia di precedenza, dal più alto al più basso.</span><span class="sxs-lookup"><span data-stu-id="c0183-198">The following list shows the precedence hierarchy, from highest to lowest.</span></span>  
  
1.  <span data-ttu-id="c0183-199">Metodi di estensione definiti all'interno del modulo corrente.</span><span class="sxs-lookup"><span data-stu-id="c0183-199">Extension methods defined inside the current module.</span></span>  
  
2.  <span data-ttu-id="c0183-200">Metodi di estensione definiti all'interno di dati tipi di spazio dei nomi corrente o uno qualsiasi dei relativi elementi padre, con spazi dei nomi figlio con precedenza maggiore rispetto a spazi dei nomi padre.</span><span class="sxs-lookup"><span data-stu-id="c0183-200">Extension methods defined inside data types in the current namespace or any one of its parents, with child namespaces having higher precedence than parent namespaces.</span></span>  
  
3.  <span data-ttu-id="c0183-201">Metodi di estensione definiti in qualsiasi tipo di importazione del file corrente.</span><span class="sxs-lookup"><span data-stu-id="c0183-201">Extension methods defined inside any type imports in the current file.</span></span>  
  
4.  <span data-ttu-id="c0183-202">Metodi di estensione definiti in qualsiasi importazione dello spazio dei nomi nel file corrente.</span><span class="sxs-lookup"><span data-stu-id="c0183-202">Extension methods defined inside any namespace imports in the current file.</span></span>  
  
5.  <span data-ttu-id="c0183-203">Metodi di estensione definiti in qualsiasi tipo di progetto a livello di importazione.</span><span class="sxs-lookup"><span data-stu-id="c0183-203">Extension methods defined inside any project-level type imports.</span></span>  
  
6.  <span data-ttu-id="c0183-204">Metodi di estensione definiti in qualsiasi importazione dello spazio dei nomi a livello di progetto.</span><span class="sxs-lookup"><span data-stu-id="c0183-204">Extension methods defined inside any project-level namespace imports.</span></span>  
  
 <span data-ttu-id="c0183-205">Se la priorità non consente di risolvere l'ambiguità, è possibile utilizzare il nome completo per specificare il metodo che si sta chiamando.</span><span class="sxs-lookup"><span data-stu-id="c0183-205">If precedence does not resolve the ambiguity, you can use the fully qualified name to specify the method that you are calling.</span></span> <span data-ttu-id="c0183-206">Se il `Print` metodo nell'esempio precedente viene definito in un modulo denominato `StringExtensions`, il nome completo è `StringExtensions.Print(example)` invece di `example.Print()`.</span><span class="sxs-lookup"><span data-stu-id="c0183-206">If the `Print` method in the earlier example is defined in a module named `StringExtensions`, the fully qualified name is `StringExtensions.Print(example)` instead of `example.Print()`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0183-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c0183-207">See Also</span></span>  
 <span data-ttu-id="c0183-208"><xref:System.Runtime.CompilerServices></xref:System.Runtime.CompilerServices></span><span class="sxs-lookup"><span data-stu-id="c0183-208"><xref:System.Runtime.CompilerServices></span></span>   
 <span data-ttu-id="c0183-209"><xref:System.Runtime.CompilerServices.ExtensionAttribute></xref:System.Runtime.CompilerServices.ExtensionAttribute></span><span class="sxs-lookup"><span data-stu-id="c0183-209"><xref:System.Runtime.CompilerServices.ExtensionAttribute></span></span>   
<span data-ttu-id="c0183-210"> [Metodi di estensione](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="c0183-210"> [Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
<span data-ttu-id="c0183-211"> [Module (istruzione)](../../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c0183-211"> [Module Statement](../../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="c0183-212"> [Gli argomenti e parametri di routine](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="c0183-212"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="c0183-213"> [Parametri facoltativi](./optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="c0183-213"> [Optional Parameters](./optional-parameters.md) </span></span>  
<span data-ttu-id="c0183-214"> [Matrici di parametri](./parameter-arrays.md) </span><span class="sxs-lookup"><span data-stu-id="c0183-214"> [Parameter Arrays](./parameter-arrays.md) </span></span>  
<span data-ttu-id="c0183-215"> [Cenni preliminari sugli attributi](../../../../visual-basic/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0183-215"> [Attributes overview](../../../../visual-basic/programming-guide/concepts/attributes/index.md) </span></span>  
<span data-ttu-id="c0183-216"> [Ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span><span class="sxs-lookup"><span data-stu-id="c0183-216"> [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)</span></span>
