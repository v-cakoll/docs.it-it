---
title: Modificatore new - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: 3a642996da8f0126e59e21d3553a7d8ba73dab23
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422675"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="e4e16-102">Modificatore new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e4e16-102">new modifier (C# Reference)</span></span>

<span data-ttu-id="e4e16-103">Se usata come modificatore di dichiarazione, la parola chiave `new` nasconde in modo esplicito un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="e4e16-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="e4e16-104">Quando si nasconde un membro ereditato, la versione derivata del membro sostituisce la versione della classe base.</span><span class="sxs-lookup"><span data-stu-id="e4e16-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="e4e16-105">Sebbene sia possibile nascondere i membri senza usare il modificatore `new`, viene visualizzato un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="e4e16-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="e4e16-106">Se si usa `new` in modo esplicito per nascondere un membro, esso elimina l'avviso.</span><span class="sxs-lookup"><span data-stu-id="e4e16-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>

<span data-ttu-id="e4e16-107">Per nascondere un membro ereditato, dichiararlo nella classe derivata usando lo stesso nome di membro e modificarlo con la parola chiave `new`.</span><span class="sxs-lookup"><span data-stu-id="e4e16-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="e4e16-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="e4e16-108">For example:</span></span>

[!code-csharp[csrefKeywordsOperator#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#8)]

<span data-ttu-id="e4e16-109">In questo esempio `BaseC.Invoke` è nascosto da `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="e4e16-109">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="e4e16-110">Il campo `x` non è interessato perché non è nascosto da un nome simile.</span><span class="sxs-lookup"><span data-stu-id="e4e16-110">The field `x` is not affected because it is not hidden by a similar name.</span></span>

<span data-ttu-id="e4e16-111">Un nome nascosto tramite ereditarietà accetta uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="e4e16-111">Name hiding through inheritance takes one of the following forms:</span></span>

- <span data-ttu-id="e4e16-112">In genere, una costante, un campo, una proprietà o un tipo introdotto in una classe o uno struct nasconde tutti i membri della classe base che condividono il nome.</span><span class="sxs-lookup"><span data-stu-id="e4e16-112">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="e4e16-113">Esistono casi particolari.</span><span class="sxs-lookup"><span data-stu-id="e4e16-113">There are special cases.</span></span>  <span data-ttu-id="e4e16-114">Se, ad esempio, si dichiara che un nuovo campo con il nome `N` dispone di un tipo non richiamabile e un tipo di base dichiara che `N` sia un metodo, il nuovo campo non nasconde la dichiarazione di base nella sintassi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e4e16-114">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="e4e16-115">Per informazioni dettagliate, vedere la sezione "Member Lookup" (Ricerca di membri) nella sezione "Expressions" (Espressioni) in [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) (Specifiche del linguaggio C# 5.0).</span><span class="sxs-lookup"><span data-stu-id="e4e16-115">See the [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) for details (see section "Member Lookup" in section "Expressions").</span></span>

- <span data-ttu-id="e4e16-116">Un metodo inserito in una classe o uno struct nasconde proprietà, campi e tipi che condividono il nome con la classe base.</span><span class="sxs-lookup"><span data-stu-id="e4e16-116">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="e4e16-117">Nasconde inoltre tutti i metodi della classe base con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="e4e16-117">It also hides all base class methods that have the same signature.</span></span>

- <span data-ttu-id="e4e16-118">Un indicizzatore inserito in una classe o uno struct nasconde tutti gli indicizzatori della classe base con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="e4e16-118">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>

<span data-ttu-id="e4e16-119">Non è possibile usare sia `new` sia [override](override.md) nello stesso membro, in quanto i significati dei due modificatori si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="e4e16-119">It is an error to use both `new` and [override](override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="e4e16-120">Il modificatore `new` crea un nuovo membro con lo stesso nome e fa sì che il membro originale venga nascosto.</span><span class="sxs-lookup"><span data-stu-id="e4e16-120">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="e4e16-121">Il modificatore `override` estende l'implementazione per un membro ereditato.</span><span class="sxs-lookup"><span data-stu-id="e4e16-121">The `override` modifier extends the implementation for an inherited member.</span></span>

<span data-ttu-id="e4e16-122">L'utilizzo del modificatore `new` in una dichiarazione che non nasconde un membro ereditato genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="e4e16-122">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>

## <a name="example"></a><span data-ttu-id="e4e16-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4e16-123">Example</span></span>

<span data-ttu-id="e4e16-124">In questo esempio, una classe base, `BaseC`, e una classe derivata, `DerivedC`, usano lo stesso nome di campo `x`, che nasconde il valore del campo ereditato.</span><span class="sxs-lookup"><span data-stu-id="e4e16-124">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="e4e16-125">Nell'esempio viene illustrato l'utilizzo del modificatore `new`.</span><span class="sxs-lookup"><span data-stu-id="e4e16-125">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="e4e16-126">Viene inoltre descritto come accedere ai membri nascosti della classe base usando i relativi nomi completi.</span><span class="sxs-lookup"><span data-stu-id="e4e16-126">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#9)]

## <a name="example"></a><span data-ttu-id="e4e16-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="e4e16-127">Example</span></span>

<span data-ttu-id="e4e16-128">In questo esempio, una classe annidata nasconde una classe che ha lo stesso nome nella classe base.</span><span class="sxs-lookup"><span data-stu-id="e4e16-128">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="e4e16-129">L'esempio illustra come usare il modificatore `new` per eliminare il messaggio di avviso e come accedere ai membri di classe nascosti tramite i relativi nomi completi.</span><span class="sxs-lookup"><span data-stu-id="e4e16-129">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>

[!code-csharp[csrefKeywordsOperator#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#10)]

<span data-ttu-id="e4e16-130">Se si rimuove il modificatore `new`, la compilazione e l'esecuzione del programma saranno comunque possibili, ma verrà visualizzato il messaggio di avviso riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e4e16-130">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>

```
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.
```

## <a name="c-language-specification"></a><span data-ttu-id="e4e16-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e4e16-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e4e16-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4e16-132">See also</span></span>

- [<span data-ttu-id="e4e16-133">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e4e16-133">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="e4e16-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e4e16-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e4e16-135">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="e4e16-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e4e16-136">Modificatori</span><span class="sxs-lookup"><span data-stu-id="e4e16-136">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="e4e16-137">Controllo delle versioni con le parole chiave Override e New</span><span class="sxs-lookup"><span data-stu-id="e4e16-137">Versioning with the Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)
- [<span data-ttu-id="e4e16-138">Sapere quando usare le parole chiave Override e New</span><span class="sxs-lookup"><span data-stu-id="e4e16-138">Knowing When to Use Override and New Keywords</span></span>](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
