---
title: Modificatore new (Riferimenti per C#)
ms.date: 07/20/2015
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
ms.openlocfilehash: b66cfacc2203e0e529c19b5c566abad6c676f149
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273968"
---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="535ee-102">Modificatore new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="535ee-102">new Modifier (C# Reference)</span></span>
<span data-ttu-id="535ee-103">Se usata come modificatore di dichiarazione, la parola chiave `new` nasconde in modo esplicito un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="535ee-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="535ee-104">Quando si nasconde un membro ereditato, la versione derivata del membro sostituisce la versione della classe base.</span><span class="sxs-lookup"><span data-stu-id="535ee-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="535ee-105">Sebbene sia possibile nascondere i membri senza usare il modificatore `new`, viene visualizzato un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="535ee-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="535ee-106">Se si usa `new` in modo esplicito per nascondere un membro, esso elimina l'avviso.</span><span class="sxs-lookup"><span data-stu-id="535ee-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>  
  
 <span data-ttu-id="535ee-107">Per nascondere un membro ereditato, dichiararlo nella classe derivata usando lo stesso nome di membro e modificarlo con la parola chiave `new`.</span><span class="sxs-lookup"><span data-stu-id="535ee-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="535ee-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="535ee-108">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]  
  
 <span data-ttu-id="535ee-109">In questo esempio `BaseC.Invoke` è nascosto da `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="535ee-109">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="535ee-110">Il campo `x` non è interessato perché non è nascosto da un nome simile.</span><span class="sxs-lookup"><span data-stu-id="535ee-110">The field `x` is not affected because it is not hidden by a similar name.</span></span>  
  
 <span data-ttu-id="535ee-111">Un nome nascosto tramite ereditarietà accetta uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="535ee-111">Name hiding through inheritance takes one of the following forms:</span></span>  
  
-   <span data-ttu-id="535ee-112">In genere, una costante, un campo, una proprietà o un tipo introdotto in una classe o uno struct nasconde tutti i membri della classe base che condividono il nome.</span><span class="sxs-lookup"><span data-stu-id="535ee-112">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="535ee-113">Esistono casi particolari.</span><span class="sxs-lookup"><span data-stu-id="535ee-113">There are special cases.</span></span>  <span data-ttu-id="535ee-114">Se, ad esempio, si dichiara che un nuovo campo con il nome `N` dispone di un tipo non richiamabile e un tipo di base dichiara che `N` sia un metodo, il nuovo campo non nasconde la dichiarazione di base nella sintassi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="535ee-114">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="535ee-115">Per informazioni dettagliate, vedere la sezione "Member Lookup" (Ricerca di membri) nella sezione "Expressions" (Espressioni) in [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) (Specifiche del linguaggio C# 5.0).</span><span class="sxs-lookup"><span data-stu-id="535ee-115">See the [C# 5.0 language specification](https://www.microsoft.com/download/details.aspx?id=7029) for details (see section "Member Lookup" in section "Expressions").</span></span>  
  
-   <span data-ttu-id="535ee-116">Un metodo inserito in una classe o uno struct nasconde proprietà, campi e tipi che condividono il nome con la classe base.</span><span class="sxs-lookup"><span data-stu-id="535ee-116">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="535ee-117">Nasconde inoltre tutti i metodi della classe base con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="535ee-117">It also hides all base class methods that have the same signature.</span></span>  
  
-   <span data-ttu-id="535ee-118">Un indicizzatore inserito in una classe o uno struct nasconde tutti gli indicizzatori della classe base con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="535ee-118">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>  
  
 <span data-ttu-id="535ee-119">Non è possibile usare sia `new` sia [override](../../../csharp/language-reference/keywords/override.md) nello stesso membro, in quanto i significati dei due modificatori si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="535ee-119">It is an error to use both `new` and [override](../../../csharp/language-reference/keywords/override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="535ee-120">Il modificatore `new` crea un nuovo membro con lo stesso nome e fa sì che il membro originale venga nascosto.</span><span class="sxs-lookup"><span data-stu-id="535ee-120">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="535ee-121">Il modificatore `override` estende l'implementazione per un membro ereditato.</span><span class="sxs-lookup"><span data-stu-id="535ee-121">The `override` modifier extends the implementation for an inherited member.</span></span>  
  
 <span data-ttu-id="535ee-122">L'utilizzo del modificatore `new` in una dichiarazione che non nasconde un membro ereditato genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="535ee-122">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="535ee-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="535ee-123">Example</span></span>  
 <span data-ttu-id="535ee-124">In questo esempio, una classe base, `BaseC`, e una classe derivata, `DerivedC`, usano lo stesso nome di campo `x`, che nasconde il valore del campo ereditato.</span><span class="sxs-lookup"><span data-stu-id="535ee-124">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="535ee-125">Nell'esempio viene illustrato l'utilizzo del modificatore `new`.</span><span class="sxs-lookup"><span data-stu-id="535ee-125">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="535ee-126">Viene inoltre descritto come accedere ai membri nascosti della classe base usando i relativi nomi completi.</span><span class="sxs-lookup"><span data-stu-id="535ee-126">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="535ee-127">Esempio</span><span class="sxs-lookup"><span data-stu-id="535ee-127">Example</span></span>  
 <span data-ttu-id="535ee-128">In questo esempio, una classe annidata nasconde una classe che ha lo stesso nome nella classe base.</span><span class="sxs-lookup"><span data-stu-id="535ee-128">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="535ee-129">L'esempio illustra come usare il modificatore `new` per eliminare il messaggio di avviso e come accedere ai membri di classe nascosti tramite i relativi nomi completi.</span><span class="sxs-lookup"><span data-stu-id="535ee-129">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>  
  
 [!code-csharp[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]  
  
 <span data-ttu-id="535ee-130">Se si rimuove il modificatore `new`, la compilazione e l'esecuzione del programma saranno comunque possibili, ma verrà visualizzato il messaggio di avviso riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="535ee-130">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="535ee-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="535ee-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="535ee-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="535ee-132">See Also</span></span>  
 [<span data-ttu-id="535ee-133">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="535ee-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="535ee-134">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="535ee-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="535ee-135">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="535ee-135">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="535ee-136">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="535ee-136">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="535ee-137">Modificatori</span><span class="sxs-lookup"><span data-stu-id="535ee-137">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="535ee-138">Controllo delle versioni con le parole chiave Override e New</span><span class="sxs-lookup"><span data-stu-id="535ee-138">Versioning with the Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)  
 [<span data-ttu-id="535ee-139">Sapere quando usare le parole chiave Override e New</span><span class="sxs-lookup"><span data-stu-id="535ee-139">Knowing When to Use Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)
