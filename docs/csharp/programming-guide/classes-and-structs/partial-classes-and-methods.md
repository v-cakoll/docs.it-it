---
title: Classi e metodi parziali - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: ea8d95c41df236897761ace1062ec325a069d52b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714739"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="52589-102">Classi e metodi parziali (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="52589-102">Partial Classes and Methods (C# Programming Guide)</span></span>

<span data-ttu-id="52589-103">È possibile suddividere la definizione di una [classe](../../language-reference/keywords/class.md) di uno [struct](../../language-reference/keywords/struct.md), di un'[interfaccia](../../language-reference/keywords/interface.md) o di un metodo tra due o più file di origine.</span><span class="sxs-lookup"><span data-stu-id="52589-103">It is possible to split the definition of a [class](../../language-reference/keywords/class.md), a [struct](../../language-reference/keywords/struct.md), an [interface](../../language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="52589-104">Ogni file di origine contiene una sezione della definizione di tipo o metodo e tutte le parti vengono combinate al momento della compilazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="52589-104">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>

## <a name="partial-classes"></a><span data-ttu-id="52589-105">Classi parziali</span><span class="sxs-lookup"><span data-stu-id="52589-105">Partial Classes</span></span>

<span data-ttu-id="52589-106">La suddivisione della definizione di una classe è consigliabile in diverse situazioni:</span><span class="sxs-lookup"><span data-stu-id="52589-106">There are several situations when splitting a class definition is desirable:</span></span>

- <span data-ttu-id="52589-107">Quando si lavora su progetti di grandi dimensioni, la distribuzione di una classe in file distinti ne consente l'uso simultaneo da parte di più programmatori.</span><span class="sxs-lookup"><span data-stu-id="52589-107">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>

- <span data-ttu-id="52589-108">Quando si usa un'origine generata automaticamente, è possibile aggiungere codice alla classe senza dover ricreare il file di origine.</span><span class="sxs-lookup"><span data-stu-id="52589-108">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="52589-109">Visual Studio usa questo approccio per la creazione di Windows Form, codice wrapper di servizi Web e così via.</span><span class="sxs-lookup"><span data-stu-id="52589-109">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="52589-110">È possibile creare codice che usa queste classi senza dover modificare il file creato da Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="52589-110">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>

- <span data-ttu-id="52589-111">Per suddividere la definizione di una classe, usare il modificatore della parola chiave [partial](../../language-reference/keywords/partial-type.md), come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="52589-111">To split a class definition, use the [partial](../../language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>

  [!code-csharp[csProgGuideObjects#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#26)]

<span data-ttu-id="52589-112">La parola chiave `partial` indica che è possibile definire altre parti della classe, dello struct o dell'interfaccia nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="52589-112">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="52589-113">Tutte le parti devono usare la parola chiave `partial`</span><span class="sxs-lookup"><span data-stu-id="52589-113">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="52589-114">ed essere disponibili in fase di compilazione in modo da formare il tipo finale.</span><span class="sxs-lookup"><span data-stu-id="52589-114">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="52589-115">Tutte le parti devono anche avere lo stesso livello di accessibilità, ad esempio `public`, `private` e così via.</span><span class="sxs-lookup"><span data-stu-id="52589-115">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>

<span data-ttu-id="52589-116">Se una parte viene dichiarata come astratta, l'intero tipo verrà considerato astratto.</span><span class="sxs-lookup"><span data-stu-id="52589-116">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="52589-117">Se una parte viene dichiarata come sealed, l'intero tipo verrà considerato sealed.</span><span class="sxs-lookup"><span data-stu-id="52589-117">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="52589-118">Se una parte dichiara un tipo base, l'intero tipo eredita la classe.</span><span class="sxs-lookup"><span data-stu-id="52589-118">If any part declares a base type, then the whole type inherits that class.</span></span>

<span data-ttu-id="52589-119">Tutte le parti che specificano una classe base devono concordare, tuttavia le parti che omettono una classe base ereditano comunque il tipo base.</span><span class="sxs-lookup"><span data-stu-id="52589-119">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="52589-120">Le parti possono specificare interfacce di base differenti e il tipo finale implementa tutte le interfacce elencate da tutte le dichiarazioni parziali.</span><span class="sxs-lookup"><span data-stu-id="52589-120">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="52589-121">Tutti i membri di classe, struttura o interfaccia dichiarati in una definizione parziale sono disponibili per tutte le altre parti.</span><span class="sxs-lookup"><span data-stu-id="52589-121">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="52589-122">Il tipo finale rappresenta la combinazione di tutte le parti in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="52589-122">The final type is the combination of all the parts at compile time.</span></span>

> [!NOTE]
> <span data-ttu-id="52589-123">Il modificatore `partial` non è disponibile per le dichiarazioni di delegato o di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="52589-123">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>

<span data-ttu-id="52589-124">L'esempio seguente illustra che i tipi annidati possono essere parziali, anche se non lo è il tipo all'interno del quale sono annidati.</span><span class="sxs-lookup"><span data-stu-id="52589-124">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>

[!code-csharp[csProgGuideObjects#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#25)]

<span data-ttu-id="52589-125">In fase di compilazione gli attributi delle definizioni di tipi parziali vengono uniti.</span><span class="sxs-lookup"><span data-stu-id="52589-125">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="52589-126">Si considerino ad esempio le dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52589-126">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#23)]

<span data-ttu-id="52589-127">Sono equivalenti alle dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52589-127">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#24)]

<span data-ttu-id="52589-128">Gli elementi seguenti vengono uniti da tutte le definizioni di tipi parziali:</span><span class="sxs-lookup"><span data-stu-id="52589-128">The following are merged from all the partial-type definitions:</span></span>

- <span data-ttu-id="52589-129">XML (commenti)</span><span class="sxs-lookup"><span data-stu-id="52589-129">XML comments</span></span>

- <span data-ttu-id="52589-130">interfacce</span><span class="sxs-lookup"><span data-stu-id="52589-130">interfaces</span></span>

- <span data-ttu-id="52589-131">attributi di parametri di tipo generico</span><span class="sxs-lookup"><span data-stu-id="52589-131">generic-type parameter attributes</span></span>

- <span data-ttu-id="52589-132">attributi class</span><span class="sxs-lookup"><span data-stu-id="52589-132">class attributes</span></span>

- <span data-ttu-id="52589-133">Membri di</span><span class="sxs-lookup"><span data-stu-id="52589-133">members</span></span>

<span data-ttu-id="52589-134">Si considerino ad esempio le dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52589-134">For example, consider the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#21)]

<span data-ttu-id="52589-135">Sono equivalenti alle dichiarazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52589-135">They are equivalent to the following declarations:</span></span>

[!code-csharp[csProgGuideObjects#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#22)]

### <a name="restrictions"></a><span data-ttu-id="52589-136">Restrizioni</span><span class="sxs-lookup"><span data-stu-id="52589-136">Restrictions</span></span>

<span data-ttu-id="52589-137">Quando si usano le definizioni parziali di classi è necessario rispettare diverse regole:</span><span class="sxs-lookup"><span data-stu-id="52589-137">There are several rules to follow when you are working with partial class definitions:</span></span>

- <span data-ttu-id="52589-138">Tutte le definizioni di tipi parziali destinate a essere parti dello stesso tipo devono essere modificate con `partial`.</span><span class="sxs-lookup"><span data-stu-id="52589-138">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="52589-139">Ad esempio, le dichiarazioni di classe seguenti generano un errore:</span><span class="sxs-lookup"><span data-stu-id="52589-139">For example, the following class declarations generate an error:</span></span>

  [!code-csharp[csProgGuideObjects#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#20)]

- <span data-ttu-id="52589-140">Il modificatore `partial` può essere specificato solo prima delle parole chiave `class`, `struct` o `interface`.</span><span class="sxs-lookup"><span data-stu-id="52589-140">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>

- <span data-ttu-id="52589-141">I tipi parziali annidati sono consentiti nelle definizioni di tipi parziali, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="52589-141">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>

  [!code-csharp[csProgGuideObjects#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#19)]

- <span data-ttu-id="52589-142">Tutte le definizioni di tipi parziali destinate a essere parti dello stesso tipo devono essere definite nello stesso assembly e nello stesso modulo (file con estensione exe o dll).</span><span class="sxs-lookup"><span data-stu-id="52589-142">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="52589-143">Le definizioni parziali non possono estendersi su più moduli.</span><span class="sxs-lookup"><span data-stu-id="52589-143">Partial definitions cannot span multiple modules.</span></span>

- <span data-ttu-id="52589-144">Il nome della classe e i parametri di tipo generico devono corrispondere in tutte le definizioni di tipi parziali.</span><span class="sxs-lookup"><span data-stu-id="52589-144">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="52589-145">I tipi generici possono essere parziali.</span><span class="sxs-lookup"><span data-stu-id="52589-145">Generic types can be partial.</span></span> <span data-ttu-id="52589-146">In ogni dichiarazione parziale è necessario usare gli stessi nomi di parametri nello stesso ordine.</span><span class="sxs-lookup"><span data-stu-id="52589-146">Each partial declaration must use the same parameter names in the same order.</span></span>

- <span data-ttu-id="52589-147">Le parole chiave riportate di seguito sono facoltative in una definizione di tipi parziali. Tuttavia, se presenti in una definizione, tali parole chiave non possono essere in conflitto con quelle specificate in un'altra definizione parziale per lo stesso tipo:</span><span class="sxs-lookup"><span data-stu-id="52589-147">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>

  - [<span data-ttu-id="52589-148">public</span><span class="sxs-lookup"><span data-stu-id="52589-148">public</span></span>](../../language-reference/keywords/public.md)

  - [<span data-ttu-id="52589-149">private</span><span class="sxs-lookup"><span data-stu-id="52589-149">private</span></span>](../../language-reference/keywords/private.md)

  - [<span data-ttu-id="52589-150">protected</span><span class="sxs-lookup"><span data-stu-id="52589-150">protected</span></span>](../../language-reference/keywords/protected.md)

  - [<span data-ttu-id="52589-151">internal</span><span class="sxs-lookup"><span data-stu-id="52589-151">internal</span></span>](../../language-reference/keywords/internal.md)

  - [<span data-ttu-id="52589-152">abstract</span><span class="sxs-lookup"><span data-stu-id="52589-152">abstract</span></span>](../../language-reference/keywords/abstract.md)

  - [<span data-ttu-id="52589-153">sealed</span><span class="sxs-lookup"><span data-stu-id="52589-153">sealed</span></span>](../../language-reference/keywords/sealed.md)

  - <span data-ttu-id="52589-154">classi base</span><span class="sxs-lookup"><span data-stu-id="52589-154">base class</span></span>

  - <span data-ttu-id="52589-155">modificatore [new](../../language-reference/keywords/new-modifier.md) (parti annidate)</span><span class="sxs-lookup"><span data-stu-id="52589-155">[new](../../language-reference/keywords/new-modifier.md) modifier (nested parts)</span></span>

  - <span data-ttu-id="52589-156">vincoli generici</span><span class="sxs-lookup"><span data-stu-id="52589-156">generic constraints</span></span>

<span data-ttu-id="52589-157">Per altre informazioni, vedere [Vincoli sui parametri di tipo](../generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="52589-157">For more information, see [Constraints on Type Parameters](../generics/constraints-on-type-parameters.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="52589-158">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="52589-158">Example 1</span></span>

### <a name="description"></a><span data-ttu-id="52589-159">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52589-159">Description</span></span>

<span data-ttu-id="52589-160">Nell'esempio seguente i campi e il costruttore della classe `Coords` vengono dichiarati in una definizione parziale di classe, mentre il membro `PrintCoords` viene dichiarato in un'altra definizione parziale di classe.</span><span class="sxs-lookup"><span data-stu-id="52589-160">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>

### <a name="code"></a><span data-ttu-id="52589-161">Codice</span><span class="sxs-lookup"><span data-stu-id="52589-161">Code</span></span>

[!code-csharp[csProgGuideObjects#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#17)]

## <a name="example-2"></a><span data-ttu-id="52589-162">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="52589-162">Example 2</span></span>

### <a name="description"></a><span data-ttu-id="52589-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="52589-163">Description</span></span>

<span data-ttu-id="52589-164">L'esempio seguente dimostra che è anche possibile sviluppare struct e interfacce parziali.</span><span class="sxs-lookup"><span data-stu-id="52589-164">The following example shows that you can also develop partial structs and interfaces.</span></span>

### <a name="code"></a><span data-ttu-id="52589-165">Codice</span><span class="sxs-lookup"><span data-stu-id="52589-165">Code</span></span>

[!code-csharp[csProgGuideObjects#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#18)]

## <a name="partial-methods"></a><span data-ttu-id="52589-166">Metodi parziali</span><span class="sxs-lookup"><span data-stu-id="52589-166">Partial Methods</span></span>

<span data-ttu-id="52589-167">Una classe o uno struct parziale può contenere un metodo parziale.</span><span class="sxs-lookup"><span data-stu-id="52589-167">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="52589-168">Una parte della classe contiene la firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="52589-168">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="52589-169">Un'implementazione facoltativa può essere definita nella stessa parte o in un'altra parte.</span><span class="sxs-lookup"><span data-stu-id="52589-169">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="52589-170">Se l'implementazione non viene specificata, il metodo e tutte le chiamate al metodo vengono rimosse in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="52589-170">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>

<span data-ttu-id="52589-171">I metodi parziali consentono all'implementatore di una parte di una classe di definire un metodo, simile a un evento.</span><span class="sxs-lookup"><span data-stu-id="52589-171">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="52589-172">L'implementatore dell'altra parte della classe può decidere se implementare il metodo o meno.</span><span class="sxs-lookup"><span data-stu-id="52589-172">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="52589-173">Se il metodo non viene implementato, il compilatore rimuove la firma del metodo e tutte le chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="52589-173">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="52589-174">Le chiamate al metodo, inclusi eventuali risultati che derivassero dalla valutazione di argomenti nelle chiamate, non hanno alcun effetto in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="52589-174">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="52589-175">Pertanto, il codice nella classe parziale può usare liberamente un metodo parziale, anche se non viene specificata l'implementazione.</span><span class="sxs-lookup"><span data-stu-id="52589-175">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="52589-176">Non verranno generati errori in fase di compilazione o errori di runtime se il metodo viene chiamato ma non implementato.</span><span class="sxs-lookup"><span data-stu-id="52589-176">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>

<span data-ttu-id="52589-177">I metodi parziali sono particolarmente utili per personalizzare il codice generato.</span><span class="sxs-lookup"><span data-stu-id="52589-177">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="52589-178">Consentono di riservare un nome e una firma del metodo, in modo che il codice generato possa chiamare il metodo ma spetta allo sviluppatore decidere se implementare il metodo.</span><span class="sxs-lookup"><span data-stu-id="52589-178">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="52589-179">Analogamente alle classi parziali, i metodi parziali consentono di usare il codice creato da un generatore di codice con il codice creato da un sviluppatore senza alcun costo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="52589-179">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>

<span data-ttu-id="52589-180">Una dichiarazione di metodo parziale è costituita da due parti: la definizione e l'implementazione,</span><span class="sxs-lookup"><span data-stu-id="52589-180">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="52589-181">che possono trovarsi in parti separate di una classe parziale o nella stessa parte.</span><span class="sxs-lookup"><span data-stu-id="52589-181">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="52589-182">Se non è presente la dichiarazione di implementazione, il compilatore ottimizza la dichiarazione di definizione e tutte le chiamate al metodo.</span><span class="sxs-lookup"><span data-stu-id="52589-182">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- <span data-ttu-id="52589-183">Le dichiarazioni di metodi parziali devono iniziare con la parola chiave contestuale [partial](../../language-reference/keywords/partial-type.md) e il metodo deve restituire [void](../../language-reference/keywords/void.md).</span><span class="sxs-lookup"><span data-stu-id="52589-183">Partial method declarations must begin with the contextual keyword [partial](../../language-reference/keywords/partial-type.md) and the method must return [void](../../language-reference/keywords/void.md).</span></span>

- <span data-ttu-id="52589-184">I metodi parziali possono contenere il parametro [in](../../language-reference/keywords/in-parameter-modifier.md) o [ref](../../language-reference/keywords/ref.md) ma non il parametro [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="52589-184">Partial methods can have [in](../../language-reference/keywords/in-parameter-modifier.md) or [ref](../../language-reference/keywords/ref.md) but not [out](../../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

- <span data-ttu-id="52589-185">I metodi parziali sono implicitamente [private](../../language-reference/keywords/private.md) e pertanto non possono essere [virtual](../../language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="52589-185">Partial methods are implicitly [private](../../language-reference/keywords/private.md), and therefore they cannot be [virtual](../../language-reference/keywords/virtual.md).</span></span>

- <span data-ttu-id="52589-186">I metodi parziali non possono essere [extern](../../language-reference/keywords/extern.md) perché la presenza del corpo determina se è in corso una definizione o un'implementazione.</span><span class="sxs-lookup"><span data-stu-id="52589-186">Partial methods cannot be [extern](../../language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>

- <span data-ttu-id="52589-187">I metodi parziali possono contenere modificatori [static](../../language-reference/keywords/static.md) e [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="52589-187">Partial methods can have [static](../../language-reference/keywords/static.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span>

- <span data-ttu-id="52589-188">I metodi parziali possono essere generici.</span><span class="sxs-lookup"><span data-stu-id="52589-188">Partial methods can be generic.</span></span> <span data-ttu-id="52589-189">I vincoli vengono inseriti nella dichiarazione di definizione del metodo parziale e possono essere ripetuti facoltativamente nella dichiarazione di implementazione.</span><span class="sxs-lookup"><span data-stu-id="52589-189">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="52589-190">I nomi dei parametri e dei parametri di tipo non devono essere uguali nella dichiarazione di implementazione e in quella di definizione.</span><span class="sxs-lookup"><span data-stu-id="52589-190">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>

- <span data-ttu-id="52589-191">È possibile creare un [delegato](../../language-reference/builtin-types/reference-types.md) di un metodo parziale che è stato definito e implementato, ma non di un metodo parziale che è stato solo definito.</span><span class="sxs-lookup"><span data-stu-id="52589-191">You can make a [delegate](../../language-reference/builtin-types/reference-types.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="52589-192">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="52589-192">C# Language Specification</span></span>

<span data-ttu-id="52589-193">Per altre informazioni, vedere [Tipi parziali](~/_csharplang/spec/classes.md#partial-types) in [Specifica del linguaggio C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="52589-193">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="52589-194">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="52589-194">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="52589-195">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52589-195">See also</span></span>

- [<span data-ttu-id="52589-196">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="52589-196">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="52589-197">Classi</span><span class="sxs-lookup"><span data-stu-id="52589-197">Classes</span></span>](./classes.md)
- [<span data-ttu-id="52589-198">Struct</span><span class="sxs-lookup"><span data-stu-id="52589-198">Structs</span></span>](./structs.md)
- [<span data-ttu-id="52589-199">Interfacce</span><span class="sxs-lookup"><span data-stu-id="52589-199">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="52589-200">partial (tipo)</span><span class="sxs-lookup"><span data-stu-id="52589-200">partial (Type)</span></span>](../../language-reference/keywords/partial-type.md)
