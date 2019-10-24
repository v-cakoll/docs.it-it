---
title: Parola chiave enum - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: 417f02ce9e8ee88edeb2a4dab88111cae39a8a4b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771858"
---
# <a name="enum-c-reference"></a><span data-ttu-id="69663-102">enum (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="69663-102">enum (C# Reference)</span></span>

<span data-ttu-id="69663-103">La parola chiave `enum` viene usata per dichiarare un'enumerazione, un tipo distinto costituito da un set di costanti denominate definite elenco degli enumeratori.</span><span class="sxs-lookup"><span data-stu-id="69663-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>

<span data-ttu-id="69663-104">In genere è preferibile definire un'enumerazione direttamente all'interno di uno spazio dei nomi in modo che tutte le classi nello spazio dei nomi possano accedervi con la stessa facilità.</span><span class="sxs-lookup"><span data-stu-id="69663-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="69663-105">Tuttavia, un'enumerazione può anche essere annidata all'interno di una classe o di uno struct.</span><span class="sxs-lookup"><span data-stu-id="69663-105">However, an enum can also be nested within a class or struct.</span></span>

<span data-ttu-id="69663-106">Per impostazione predefinita, il primo enumeratore ha un valore 0 e il valore di ogni enumeratore successivo viene incrementato di 1.</span><span class="sxs-lookup"><span data-stu-id="69663-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="69663-107">Ad esempio, nell'enumerazione seguente `Sat` è `0`, `Sun` è `1`, `Mon` è `2`e così via.</span><span class="sxs-lookup"><span data-stu-id="69663-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="69663-108">Gli enumeratori possono usare gli inizializzatori per sostituire i valori predefiniti, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="69663-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="69663-109">In questa enumerazione la sequenza di elementi viene forzata a iniziare da `1` anziché da `0`.</span><span class="sxs-lookup"><span data-stu-id="69663-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="69663-110">Tuttavia, si consiglia di includere una costante con valore pari a 0.</span><span class="sxs-lookup"><span data-stu-id="69663-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="69663-111">Per altre informazioni, vedere [Tipi di enumerazione](../../programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="69663-111">For more information, see [Enumeration Types](../../programming-guide/enumeration-types.md).</span></span>

<span data-ttu-id="69663-112">Ogni tipo di enumerazione ha un tipo sottostante, che può essere qualsiasi [tipo numerico integrale](../builtin-types/integral-numeric-types.md).</span><span class="sxs-lookup"><span data-stu-id="69663-112">Every enumeration type has an underlying type, which can be any [integral numeric type](../builtin-types/integral-numeric-types.md).</span></span> <span data-ttu-id="69663-113">Il tipo [char](char.md) non può essere un tipo sottostante di un'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="69663-113">The [char](char.md) type cannot be an underlying type of an enum.</span></span> <span data-ttu-id="69663-114">Il tipo sottostante predefinito degli elementi dell'enumerazione è [int](../builtin-types/integral-numeric-types.md). Per dichiarare un'enumerazione di un altro tipo integrale, ad esempio [byte](../builtin-types/integral-numeric-types.md), usare i due punti dopo l'identificatore seguito dal tipo, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="69663-114">The default underlying type of enumeration elements is [int](../builtin-types/integral-numeric-types.md). To declare an enum of another integral type, such as [byte](../builtin-types/integral-numeric-types.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

<span data-ttu-id="69663-115">A una variabile di tipo enumerazione può essere assegnato qualsiasi valore compreso nell'intervallo del tipo sottostante. I valori non sono limitati alle costanti denominate.</span><span class="sxs-lookup"><span data-stu-id="69663-115">A variable of an enumeration type can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>

<span data-ttu-id="69663-116">Il valore predefinito di un `enum E` è il valore prodotto dall'espressione `(E)0`.</span><span class="sxs-lookup"><span data-stu-id="69663-116">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>

> [!NOTE]
> <span data-ttu-id="69663-117">Un enumeratore non può contenere spazi vuoti nel nome.</span><span class="sxs-lookup"><span data-stu-id="69663-117">An enumerator cannot contain white space in its name.</span></span>

<span data-ttu-id="69663-118">Il tipo sottostante specifica la quantità di spazio di archiviazione allocata per ogni enumeratore.</span><span class="sxs-lookup"><span data-stu-id="69663-118">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="69663-119">Tuttavia, è necessario un cast esplicito per eseguire la conversione da un tipo `enum` a un tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="69663-119">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="69663-120">Ad esempio, l'istruzione seguente assegna l'enumeratore `Sun` a una variabile di tipo [int](../builtin-types/integral-numeric-types.md) usando un cast per convertire `enum` in `int`.</span><span class="sxs-lookup"><span data-stu-id="69663-120">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../builtin-types/integral-numeric-types.md) by using a cast to convert from `enum` to `int`.</span></span>

```csharp
int x = (int)Day.Sun;
```

<span data-ttu-id="69663-121">Quando si applica <xref:System.FlagsAttribute?displayProperty=nameWithType> a un'enumerazione che contiene elementi che possono essere combinati con un'operazione `OR` bit per bit, l'attributo influisce sul comportamento di `enum` quando viene usato con alcuni strumenti.</span><span class="sxs-lookup"><span data-stu-id="69663-121">When you apply <xref:System.FlagsAttribute?displayProperty=nameWithType> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="69663-122">È possibile notare queste modifiche quando si usano strumenti come i metodi della classe <xref:System.Console> e l'analizzatore di espressioni.</span><span class="sxs-lookup"><span data-stu-id="69663-122">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="69663-123">Vedere il terzo esempio.</span><span class="sxs-lookup"><span data-stu-id="69663-123">(See the third example.)</span></span>

## <a name="robust-programming"></a><span data-ttu-id="69663-124">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="69663-124">Robust programming</span></span>

<span data-ttu-id="69663-125">Come per le altre costanti, tutti i riferimenti ai singoli valori di un'enumerazione vengono convertiti in valori letterali numerici in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="69663-125">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="69663-126">Questo può creare potenziali problemi relativi al controllo delle versioni come descritto in [Costanti](../../programming-guide/classes-and-structs/constants.md).</span><span class="sxs-lookup"><span data-stu-id="69663-126">This can create potential versioning issues as described in [Constants](../../programming-guide/classes-and-structs/constants.md).</span></span>

<span data-ttu-id="69663-127">L'assegnazione di valori aggiuntivi alle nuove versioni delle enumerazioni o la modifica dei valori dei membri enum in una nuova versione può causare problemi per il codice sorgente dipendente.</span><span class="sxs-lookup"><span data-stu-id="69663-127">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="69663-128">I valori enum spesso vengono usati nelle istruzioni [switch](switch.md) .</span><span class="sxs-lookup"><span data-stu-id="69663-128">Enum values often are used in [switch](switch.md) statements.</span></span> <span data-ttu-id="69663-129">Se sono stati aggiunti altri elementi al tipo `enum` , la sezione predefinita dell'istruzione switch può essere selezionata in modo imprevisto.</span><span class="sxs-lookup"><span data-stu-id="69663-129">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>

<span data-ttu-id="69663-130">Se altri sviluppatori usano il codice, è opportuno fornire indicazioni su come dovrebbe rispondere il loro codice quando vengono aggiunti nuovi elementi a qualsiasi tipo `enum` .</span><span class="sxs-lookup"><span data-stu-id="69663-130">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>

## <a name="example"></a><span data-ttu-id="69663-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="69663-131">Example</span></span>

<span data-ttu-id="69663-132">Nell'esempio seguente viene dichiarata un'enumerazione `Day`.</span><span class="sxs-lookup"><span data-stu-id="69663-132">In the following example, an enumeration, `Day`, is declared.</span></span> <span data-ttu-id="69663-133">Due enumeratori vengono convertiti esplicitamente in un valore integer e assegnati a variabili integer.</span><span class="sxs-lookup"><span data-stu-id="69663-133">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a><span data-ttu-id="69663-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="69663-134">Example</span></span>

<span data-ttu-id="69663-135">Nell'esempio seguente l'opzione del tipo di base viene usata per dichiarare un `enum` i cui membri sono di tipo `long`.</span><span class="sxs-lookup"><span data-stu-id="69663-135">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="69663-136">Si noti che, anche se il tipo sottostante dell'enumerazione è `long`, i membri dell'enumerazione non sono ancora stati convertiti esplicitamente nel tipo `long` con un cast.</span><span class="sxs-lookup"><span data-stu-id="69663-136">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a><span data-ttu-id="69663-137">Esempio</span><span class="sxs-lookup"><span data-stu-id="69663-137">Example</span></span>

<span data-ttu-id="69663-138">L'esempio di codice seguente illustra l'utilizzo e gli effetti dell'attributo <xref:System.FlagsAttribute?displayProperty=nameWithType> su una dichiarazione `enum` .</span><span class="sxs-lookup"><span data-stu-id="69663-138">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=nameWithType> attribute on an `enum` declaration.</span></span>

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a><span data-ttu-id="69663-139">Comments</span><span class="sxs-lookup"><span data-stu-id="69663-139">Comments</span></span>

<span data-ttu-id="69663-140">Se si rimuove `Flags`, l'esempio visualizza i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="69663-140">If you remove `Flags`, the example displays the following values:</span></span>

`5`

`5`

## <a name="c-language-specification"></a><span data-ttu-id="69663-141">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="69663-141">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="69663-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69663-142">See also</span></span>

- [<span data-ttu-id="69663-143">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="69663-143">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="69663-144">Tipi di enumerazione</span><span class="sxs-lookup"><span data-stu-id="69663-144">Enumeration Types</span></span>](../../programming-guide/enumeration-types.md)
- [<span data-ttu-id="69663-145">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="69663-145">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="69663-146">Tipi integrali</span><span class="sxs-lookup"><span data-stu-id="69663-146">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="69663-147">Tabella dei tipi incorporati</span><span class="sxs-lookup"><span data-stu-id="69663-147">Built-In Types Table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="69663-148">Convenzioni di denominazione di enumerazione</span><span class="sxs-lookup"><span data-stu-id="69663-148">Enum Naming Conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
