---
title: Classi e metodi parziali (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
caps.latest.revision: 35
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41b07af83faa6af23695f3719aae29183c35a417
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="cacea-102">Classi e metodi parziali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="cacea-102">Partial Classes and Methods (C# Programming Guide)</span></span>
<span data-ttu-id="cacea-103">È possibile suddividere la definizione di una [classe](../../../csharp/language-reference/keywords/class.md) o uno [struct](../../../csharp/language-reference/keywords/struct.md), di un'[interfaccia](../../../csharp/language-reference/keywords/interface.md) o un metodo tra due o più file di origine.</span><span class="sxs-lookup"><span data-stu-id="cacea-103">It is possible to split the definition of a [class](../../../csharp/language-reference/keywords/class.md) or a [struct](../../../csharp/language-reference/keywords/struct.md), an [interface](../../../csharp/language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="cacea-104">Ogni file di origine contiene una sezione della definizione di tipo o metodo e tutte le parti vengono combinate al momento della compilazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="cacea-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>  
  
## <a name="partial-classes"></a><span data-ttu-id="cacea-105">Classi parziali</span><span class="sxs-lookup"><span data-stu-id="cacea-105">Partial Classes</span></span>  
 <span data-ttu-id="cacea-106">La suddivisione della definizione di una classe è consigliabile in diverse situazioni:</span><span class="sxs-lookup"><span data-stu-id="cacea-106">There are several situations when splitting a class definition is desirable:</span></span>  
  
-   <span data-ttu-id="cacea-107">Quando si lavora su progetti di grandi dimensioni, la distribuzione di una classe in file distinti ne consente l'uso simultaneo da parte di più programmatori.</span><span class="sxs-lookup"><span data-stu-id="cacea-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>  
  
-   <span data-ttu-id="cacea-108">Quando si usa un'origine generata automaticamente, è possibile aggiungere codice alla classe senza dover ricreare il file di origine.</span><span class="sxs-lookup"><span data-stu-id="cacea-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="cacea-109">Visual Studio usa questo approccio per la creazione di Windows Form, codice wrapper di servizi Web e così via.</span><span class="sxs-lookup"><span data-stu-id="cacea-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="cacea-110">È possibile creare codice che usa queste classi senza dover modificare il file creato da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="cacea-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>  
  
-   <span data-ttu-id="cacea-111">Per suddividere la definizione di una classe, usare il modificatore della parola chiave [partial](../../../csharp/language-reference/keywords/partial-type.md), come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cacea-111">To split a class definition, use the [partial](../../../csharp/language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>  
  
 <span data-ttu-id="cacea-112">[!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-112">[!code-cs[csProgGuideObjects#26](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_1.cs)]</span></span>  
  
 <span data-ttu-id="cacea-113">La parola chiave `partial` indica che è possibile definire altre parti della classe, dello struct o dell'interfaccia nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="cacea-113">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="cacea-114">Tutte le parti devono usare la parola chiave `partial`</span><span class="sxs-lookup"><span data-stu-id="cacea-114">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="cacea-115">ed essere disponibili in fase di compilazione in modo da formare il tipo finale.</span><span class="sxs-lookup"><span data-stu-id="cacea-115">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="cacea-116">Tutte le parti devono anche avere lo stesso livello di accessibilità, ad esempio `public`, `private` e così via.</span><span class="sxs-lookup"><span data-stu-id="cacea-116">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>  
  
 <span data-ttu-id="cacea-117">Se una parte viene dichiarata come astratta, l'intero tipo verrà considerato astratto.</span><span class="sxs-lookup"><span data-stu-id="cacea-117">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="cacea-118">Se una parte viene dichiarata come sealed, l'intero tipo verrà considerato sealed.</span><span class="sxs-lookup"><span data-stu-id="cacea-118">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="cacea-119">Se una parte dichiara un tipo base, l'intero tipo eredita la classe.</span><span class="sxs-lookup"><span data-stu-id="cacea-119">If any part declares a base type, then the whole type inherits that class.</span></span>  
  
 <span data-ttu-id="cacea-120">Tutte le parti che specificano una classe base devono concordare, tuttavia le parti che omettono una classe base ereditano comunque il tipo base.</span><span class="sxs-lookup"><span data-stu-id="cacea-120">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="cacea-121">Le parti possono specificare interfacce di base differenti e il tipo finale implementa tutte le interfacce elencate da tutte le dichiarazioni parziali.</span><span class="sxs-lookup"><span data-stu-id="cacea-121">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="cacea-122">Tutti i membri di classe, struttura o interfaccia dichiarati in una definizione parziale sono disponibili per tutte le altre parti.</span><span class="sxs-lookup"><span data-stu-id="cacea-122">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="cacea-123">Il tipo finale rappresenta la combinazione di tutte le parti in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cacea-123">The final type is the combination of all the parts at compile time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cacea-124">Il modificatore `partial` non è disponibile per le dichiarazioni di delegato o di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="cacea-124">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>  
  
 <span data-ttu-id="cacea-125">L'esempio seguente illustra che i tipi annidati possono essere parziali, anche se non lo è il tipo all'interno del quale sono annidati.</span><span class="sxs-lookup"><span data-stu-id="cacea-125">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>  
  
 <span data-ttu-id="cacea-126">[!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-126">[!code-cs[csProgGuideObjects#25](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_2.cs)]</span></span>  
  
 <span data-ttu-id="cacea-127">In fase di compilazione gli attributi delle definizioni di tipi parziali vengono uniti.</span><span class="sxs-lookup"><span data-stu-id="cacea-127">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="cacea-128">Si considerino ad esempio le dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cacea-128">For example, consider the following declarations:</span></span>  
  
 <span data-ttu-id="cacea-129">[!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-129">[!code-cs[csProgGuideObjects#23](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_3.cs)]</span></span>  
  
 <span data-ttu-id="cacea-130">Sono equivalenti alle dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cacea-130">They are equivalent to the following declarations:</span></span>  
  
 <span data-ttu-id="cacea-131">[!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-131">[!code-cs[csProgGuideObjects#24](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_4.cs)]</span></span>  
  
 <span data-ttu-id="cacea-132">Gli elementi seguenti vengono uniti da tutte le definizioni di tipi parziali:</span><span class="sxs-lookup"><span data-stu-id="cacea-132">The following are merged from all the partial-type definitions:</span></span>  
  
-   <span data-ttu-id="cacea-133">XML (commenti)</span><span class="sxs-lookup"><span data-stu-id="cacea-133">XML comments</span></span>  
  
-   <span data-ttu-id="cacea-134">interfacce</span><span class="sxs-lookup"><span data-stu-id="cacea-134">interfaces</span></span>  
  
-   <span data-ttu-id="cacea-135">attributi di parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="cacea-135">generic-type parameter attributes</span></span>  
  
-   <span data-ttu-id="cacea-136">attributi class</span><span class="sxs-lookup"><span data-stu-id="cacea-136">class attributes</span></span>  
  
-   <span data-ttu-id="cacea-137">membri</span><span class="sxs-lookup"><span data-stu-id="cacea-137">members</span></span>  
  
 <span data-ttu-id="cacea-138">Si considerino ad esempio le dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cacea-138">For example, consider the following declarations:</span></span>  
  
 <span data-ttu-id="cacea-139">[!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-139">[!code-cs[csProgGuideObjects#21](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_5.cs)]</span></span>  
  
 <span data-ttu-id="cacea-140">Sono equivalenti alle dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cacea-140">They are equivalent to the following declarations:</span></span>  
  
 <span data-ttu-id="cacea-141">[!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-141">[!code-cs[csProgGuideObjects#22](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_6.cs)]</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="cacea-142">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="cacea-142">Restrictions</span></span>  
 <span data-ttu-id="cacea-143">Quando si usano le definizioni parziali di classi è necessario rispettare diverse regole:</span><span class="sxs-lookup"><span data-stu-id="cacea-143">There are several rules to follow when you are working with partial class definitions:</span></span>  
  
-   <span data-ttu-id="cacea-144">Tutte le definizioni di tipi parziali destinate a essere parti dello stesso tipo devono essere modificate con `partial`.</span><span class="sxs-lookup"><span data-stu-id="cacea-144">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="cacea-145">Ad esempio, le dichiarazioni di classe seguenti generano un errore:</span><span class="sxs-lookup"><span data-stu-id="cacea-145">For example, the following class declarations generate an error:</span></span>  
  
     <span data-ttu-id="cacea-146">[!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-146">[!code-cs[csProgGuideObjects#20](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_7.cs)]</span></span>  
  
-   <span data-ttu-id="cacea-147">Il modificatore `partial` può essere specificato solo prima delle parole chiave `class`, `struct` o `interface`.</span><span class="sxs-lookup"><span data-stu-id="cacea-147">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>  
  
-   <span data-ttu-id="cacea-148">I tipi parziali annidati sono consentiti nelle definizioni di tipi parziali, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="cacea-148">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>  
  
     <span data-ttu-id="cacea-149">[!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-149">[!code-cs[csProgGuideObjects#19](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_8.cs)]</span></span>  
  
-   <span data-ttu-id="cacea-150">Tutte le definizioni di tipi parziali destinate a essere parti dello stesso tipo devono essere definite nello stesso assembly e nello stesso modulo (file con estensione exe o dll).</span><span class="sxs-lookup"><span data-stu-id="cacea-150">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="cacea-151">Le definizioni parziali non possono estendersi su più moduli.</span><span class="sxs-lookup"><span data-stu-id="cacea-151">Partial definitions cannot span multiple modules.</span></span>  
  
-   <span data-ttu-id="cacea-152">Il nome della classe e i parametri di tipo generico devono corrispondere in tutte le definizioni di tipi parziali.</span><span class="sxs-lookup"><span data-stu-id="cacea-152">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="cacea-153">I tipi generici possono essere parziali.</span><span class="sxs-lookup"><span data-stu-id="cacea-153">Generic types can be partial.</span></span> <span data-ttu-id="cacea-154">In ogni dichiarazione parziale è necessario usare gli stessi nomi di parametri nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="cacea-154">Each partial declaration must use the same parameter names in the same order.</span></span>  
  
-   <span data-ttu-id="cacea-155">Le parole chiave riportate di seguito sono facoltative in una definizione di tipi parziali. Tuttavia, se presenti in una definizione, tali parole chiave non possono essere in conflitto con quelle specificate in un'altra definizione parziale per lo stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="cacea-155">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>  
  
    -   [<span data-ttu-id="cacea-156">public</span><span class="sxs-lookup"><span data-stu-id="cacea-156">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
    -   [<span data-ttu-id="cacea-157">private</span><span class="sxs-lookup"><span data-stu-id="cacea-157">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
    -   [<span data-ttu-id="cacea-158">protected</span><span class="sxs-lookup"><span data-stu-id="cacea-158">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
    -   [<span data-ttu-id="cacea-159">internal</span><span class="sxs-lookup"><span data-stu-id="cacea-159">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
    -   [<span data-ttu-id="cacea-160">abstract</span><span class="sxs-lookup"><span data-stu-id="cacea-160">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
  
    -   [<span data-ttu-id="cacea-161">sealed</span><span class="sxs-lookup"><span data-stu-id="cacea-161">sealed</span></span>](../../../csharp/language-reference/keywords/sealed.md)  
  
    -   <span data-ttu-id="cacea-162">classi base</span><span class="sxs-lookup"><span data-stu-id="cacea-162">base class</span></span>  
  
    -   <span data-ttu-id="cacea-163">modificatore [new](../../../csharp/language-reference/keywords/new.md) (parti annidate)</span><span class="sxs-lookup"><span data-stu-id="cacea-163">[new](../../../csharp/language-reference/keywords/new.md) modifier (nested parts)</span></span>  
  
    -   <span data-ttu-id="cacea-164">vincoli generici</span><span class="sxs-lookup"><span data-stu-id="cacea-164">generic constraints</span></span>  
  
         <span data-ttu-id="cacea-165">Per altre informazioni, vedere [Vincoli sui parametri di tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="cacea-165">For more information, see [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="cacea-166">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="cacea-166">Example 1</span></span>  
  
### <a name="description"></a><span data-ttu-id="cacea-167">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cacea-167">Description</span></span>  
 <span data-ttu-id="cacea-168">Nell'esempio seguente i campi e il costruttore della classe `CoOrds` vengono dichiarati in una definizione parziale di classe, mentre il membro `PrintCoOrds` viene dichiarato in un'altra definizione parziale di classe.</span><span class="sxs-lookup"><span data-stu-id="cacea-168">In the following example, the fields and the constructor of the class, `CoOrds`, are declared in one partial class definition, and the member, `PrintCoOrds`, is declared in another partial class definition.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cacea-169">Codice</span><span class="sxs-lookup"><span data-stu-id="cacea-169">Code</span></span>  
 <span data-ttu-id="cacea-170">[!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-170">[!code-cs[csProgGuideObjects#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_9.cs)]</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="cacea-171">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="cacea-171">Example 2</span></span>  
  
### <a name="description"></a><span data-ttu-id="cacea-172">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cacea-172">Description</span></span>  
 <span data-ttu-id="cacea-173">L'esempio seguente dimostra che è anche possibile sviluppare struct e interfacce parziali.</span><span class="sxs-lookup"><span data-stu-id="cacea-173">The following example shows that you can also develop partial structs and interfaces.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cacea-174">Codice</span><span class="sxs-lookup"><span data-stu-id="cacea-174">Code</span></span>  
 <span data-ttu-id="cacea-175">[!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="cacea-175">[!code-cs[csProgGuideObjects#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/partial-classes-and-methods_10.cs)]</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="cacea-176">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="cacea-176">Partial Methods</span></span>  
 <span data-ttu-id="cacea-177">Una classe o uno struct parziale può contenere un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="cacea-177">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="cacea-178">Una parte della classe contiene la firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="cacea-178">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="cacea-179">Un'implementazione facoltativa può essere definita nella stessa parte o in un'altra parte.</span><span class="sxs-lookup"><span data-stu-id="cacea-179">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="cacea-180">Se l'implementazione non viene specificata, il metodo e tutte le chiamate al metodo vengono rimosse in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="cacea-180">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>  
  
 <span data-ttu-id="cacea-181">I metodi parziali consentono all'implementatore di una parte di una classe di definire un metodo, simile a un evento.</span><span class="sxs-lookup"><span data-stu-id="cacea-181">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="cacea-182">L'implementatore dell'altra parte della classe può decidere se implementare il metodo o meno.</span><span class="sxs-lookup"><span data-stu-id="cacea-182">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="cacea-183">Se il metodo non viene implementato, il compilatore rimuove la firma del metodo e tutte le chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="cacea-183">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="cacea-184">Le chiamate al metodo, inclusi eventuali risultati che derivassero dalla valutazione di argomenti nelle chiamate, non hanno alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cacea-184">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="cacea-185">Pertanto, il codice nella classe parziale può usare liberamente un metodo parziale, anche se non viene specificata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="cacea-185">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="cacea-186">Non verranno generati errori in fase di compilazione o errori di runtime se il metodo viene chiamato ma non implementato.</span><span class="sxs-lookup"><span data-stu-id="cacea-186">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>  
  
 <span data-ttu-id="cacea-187">I metodi parziali sono particolarmente utili per personalizzare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cacea-187">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="cacea-188">Consentono di riservare un nome e una firma del metodo, in modo che il codice generato possa chiamare il metodo ma spetta allo sviluppatore decidere se implementare il metodo.</span><span class="sxs-lookup"><span data-stu-id="cacea-188">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="cacea-189">Analogamente alle classi parziali, i metodi parziali consentono di usare il codice creato da un generatore di codice con il codice creato da un sviluppatore senza alcun costo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cacea-189">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>  
  
 <span data-ttu-id="cacea-190">Una dichiarazione di metodo parziale è costituita da due parti: la definizione e l'implementazione,</span><span class="sxs-lookup"><span data-stu-id="cacea-190">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="cacea-191">che possono trovarsi in parti separate di una classe parziale o nella stessa parte.</span><span class="sxs-lookup"><span data-stu-id="cacea-191">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="cacea-192">Se non è presente la dichiarazione di implementazione, il compilatore ottimizza la dichiarazione di definizione e tutte le chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="cacea-192">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>  
  
```  
// Definition in file1.cs  
partial void onNameChanged();  
  
// Implementation in file2.cs  
partial void onNameChanged()  
{  
  // method body  
}  
```  
  
-   <span data-ttu-id="cacea-193">Le dichiarazioni di metodi parziali devono iniziare con la parola chiave contestuale [partial](../../../csharp/language-reference/keywords/partial-type.md) e il metodo deve restituire [void](../../../csharp/language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="cacea-193">Partial method declarations must begin with the contextual keyword [partial](../../../csharp/language-reference/keywords/partial-type.md) and the method must return [void](../../../csharp/language-reference/keywords/void.md).</span></span>  
  
-   <span data-ttu-id="cacea-194">I metodi parziali possono contenere il parametro [ref](../../../csharp/language-reference/keywords/ref.md) ma non il parametro [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="cacea-194">Partial methods can have [ref](../../../csharp/language-reference/keywords/ref.md) but not [out](../../../csharp/language-reference/keywords/out.md) parameters.</span></span>  
  
-   <span data-ttu-id="cacea-195">I metodi parziali sono implicitamente [private](../../../csharp/language-reference/keywords/private.md) e pertanto non possono essere [virtual](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="cacea-195">Partial methods are implicitly [private](../../../csharp/language-reference/keywords/private.md), and therefore they cannot be [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
-   <span data-ttu-id="cacea-196">I metodi parziali non possono essere [extern](../../../csharp/language-reference/keywords/extern.md) perché la presenza del corpo determina se è in corso una definizione o un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="cacea-196">Partial methods cannot be [extern](../../../csharp/language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>  
  
-   <span data-ttu-id="cacea-197">I metodi parziali possono contenere modificatori [static](../../../csharp/language-reference/keywords/static.md) e [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="cacea-197">Partial methods can have [static](../../../csharp/language-reference/keywords/static.md) and [unsafe](../../../csharp/language-reference/keywords/unsafe.md) modifiers.</span></span>  
  
-   <span data-ttu-id="cacea-198">I metodi parziali possono essere generici.</span><span class="sxs-lookup"><span data-stu-id="cacea-198">Partial methods can be generic.</span></span> <span data-ttu-id="cacea-199">I vincoli vengono inseriti nella dichiarazione di definizione del metodo parziale e possono essere ripetuti facoltativamente nella dichiarazione di implementazione.</span><span class="sxs-lookup"><span data-stu-id="cacea-199">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="cacea-200">I nomi dei parametri e dei parametri di tipo non devono essere uguali nella dichiarazione di implementazione e in quella di definizione.</span><span class="sxs-lookup"><span data-stu-id="cacea-200">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>  
  
-   <span data-ttu-id="cacea-201">È possibile creare un [delegato](../../../csharp/language-reference/keywords/delegate.md) di un metodo parziale che è stato definito e implementato, ma non di un metodo parziale che è stato solo definito.</span><span class="sxs-lookup"><span data-stu-id="cacea-201">You can make a [delegate](../../../csharp/language-reference/keywords/delegate.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="cacea-202">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="cacea-202">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cacea-203">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cacea-203">See Also</span></span>  
 <span data-ttu-id="cacea-204">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cacea-204">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cacea-205">[Classi](../../../csharp/programming-guide/classes-and-structs/classes.md) </span><span class="sxs-lookup"><span data-stu-id="cacea-205">[Classes](../../../csharp/programming-guide/classes-and-structs/classes.md) </span></span>  
 <span data-ttu-id="cacea-206">[Struct](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="cacea-206">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 <span data-ttu-id="cacea-207">[Interfacce](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="cacea-207">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 [<span data-ttu-id="cacea-208">partial (tipo)</span><span class="sxs-lookup"><span data-stu-id="cacea-208">partial (Type)</span></span>](../../../csharp/language-reference/keywords/partial-type.md)

