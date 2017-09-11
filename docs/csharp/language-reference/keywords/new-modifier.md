---
title: Modificatore new (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: 28
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
ms.openlocfilehash: f763b9a1d2f146b8ebb475a01bd12f1a4238050a
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="1bba3-102">Modificatore new (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1bba3-102">new Modifier (C# Reference)</span></span>
<span data-ttu-id="1bba3-103">Se usata come modificatore di dichiarazione, la parola chiave `new` nasconde in modo esplicito un membro ereditato da una classe base.</span><span class="sxs-lookup"><span data-stu-id="1bba3-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="1bba3-104">Quando si nasconde un membro ereditato, la versione derivata del membro sostituisce la versione della classe base.</span><span class="sxs-lookup"><span data-stu-id="1bba3-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="1bba3-105">Sebbene sia possibile nascondere i membri senza usare il modificatore `new`, viene visualizzato un avviso del compilatore.</span><span class="sxs-lookup"><span data-stu-id="1bba3-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="1bba3-106">Se si usa `new` in modo esplicito per nascondere un membro, esso elimina l'avviso.</span><span class="sxs-lookup"><span data-stu-id="1bba3-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>  
  
 <span data-ttu-id="1bba3-107">Per nascondere un membro ereditato, dichiararlo nella classe derivata usando lo stesso nome di membro e modificarlo con la parola chiave `new`.</span><span class="sxs-lookup"><span data-stu-id="1bba3-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="1bba3-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1bba3-108">For example:</span></span>  
  
 <span data-ttu-id="1bba3-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1bba3-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span></span>  
  
 <span data-ttu-id="1bba3-110">In questo esempio `BaseC.Invoke` è nascosto da `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="1bba3-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="1bba3-111">Il campo `x` non è interessato perché non è nascosto da un nome simile.</span><span class="sxs-lookup"><span data-stu-id="1bba3-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>  
  
 <span data-ttu-id="1bba3-112">Un nome nascosto tramite ereditarietà accetta uno dei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="1bba3-112">Name hiding through inheritance takes one of the following forms:</span></span>  
  
-   <span data-ttu-id="1bba3-113">In genere, una costante, un campo, una proprietà o un tipo introdotto in una classe o uno struct nasconde tutti i membri della classe base che condividono il nome.</span><span class="sxs-lookup"><span data-stu-id="1bba3-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="1bba3-114">Esistono casi particolari.</span><span class="sxs-lookup"><span data-stu-id="1bba3-114">There are special cases.</span></span>  <span data-ttu-id="1bba3-115">Se, ad esempio, si dichiara che un nuovo campo con il nome `N` dispone di un tipo non richiamabile e un tipo di base dichiara che `N` sia un metodo, il nuovo campo non nasconde la dichiarazione di base nella sintassi di chiamata.</span><span class="sxs-lookup"><span data-stu-id="1bba3-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="1bba3-116">Per informazioni dettagliate, vedere la sezione "Member Lookup" (Ricerca di membri) nella sezione "Expressions" (Espressioni) in [C# language specification](http://go.microsoft.com/fwlink/?LinkId=199552) (Specifiche del linguaggio C#).</span><span class="sxs-lookup"><span data-stu-id="1bba3-116">See the [C# language specification](http://go.microsoft.com/fwlink/?LinkId=199552) for details (see section "Member Lookup" in section "Expressions").</span></span>  
  
-   <span data-ttu-id="1bba3-117">Un metodo inserito in una classe o uno struct nasconde proprietà, campi e tipi che condividono il nome con la classe base.</span><span class="sxs-lookup"><span data-stu-id="1bba3-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="1bba3-118">Nasconde inoltre tutti i metodi della classe base con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="1bba3-118">It also hides all base class methods that have the same signature.</span></span>  
  
-   <span data-ttu-id="1bba3-119">Un indicizzatore inserito in una classe o uno struct nasconde tutti gli indicizzatori della classe base con la stessa firma.</span><span class="sxs-lookup"><span data-stu-id="1bba3-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>  
  
 <span data-ttu-id="1bba3-120">Non è possibile usare sia `new` sia [override](../../../csharp/language-reference/keywords/override.md) nello stesso membro, in quanto i significati dei due modificatori si escludono reciprocamente.</span><span class="sxs-lookup"><span data-stu-id="1bba3-120">It is an error to use both `new` and [override](../../../csharp/language-reference/keywords/override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="1bba3-121">Il modificatore `new` crea un nuovo membro con lo stesso nome e fa sì che il membro originale venga nascosto.</span><span class="sxs-lookup"><span data-stu-id="1bba3-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="1bba3-122">Il modificatore `override` estende l'implementazione per un membro ereditato.</span><span class="sxs-lookup"><span data-stu-id="1bba3-122">The `override` modifier extends the implementation for an inherited member.</span></span>  
  
 <span data-ttu-id="1bba3-123">L'utilizzo del modificatore `new` in una dichiarazione che non nasconde un membro ereditato genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="1bba3-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bba3-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bba3-124">Example</span></span>  
 <span data-ttu-id="1bba3-125">In questo esempio, una classe base, `BaseC`, e una classe derivata, `DerivedC`, usano lo stesso nome di campo `x`, che nasconde il valore del campo ereditato.</span><span class="sxs-lookup"><span data-stu-id="1bba3-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="1bba3-126">Nell'esempio viene illustrato l'utilizzo del modificatore `new`.</span><span class="sxs-lookup"><span data-stu-id="1bba3-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="1bba3-127">Viene inoltre descritto come accedere ai membri nascosti della classe base usando i relativi nomi completi.</span><span class="sxs-lookup"><span data-stu-id="1bba3-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="1bba3-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="1bba3-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bba3-129">Esempio</span><span class="sxs-lookup"><span data-stu-id="1bba3-129">Example</span></span>  
 <span data-ttu-id="1bba3-130">In questo esempio, una classe annidata nasconde una classe che ha lo stesso nome nella classe base.</span><span class="sxs-lookup"><span data-stu-id="1bba3-130">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="1bba3-131">L'esempio illustra come usare il modificatore `new` per eliminare il messaggio di avviso e come accedere ai membri di classe nascosti tramite i relativi nomi completi.</span><span class="sxs-lookup"><span data-stu-id="1bba3-131">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="1bba3-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="1bba3-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span></span>  
  
 <span data-ttu-id="1bba3-133">Se si rimuove il modificatore `new`, la compilazione e l'esecuzione del programma saranno comunque possibili, ma verrà visualizzato il messaggio di avviso riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1bba3-133">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="1bba3-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1bba3-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1bba3-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bba3-135">See Also</span></span>  
 <span data-ttu-id="1bba3-136">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1bba3-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1bba3-137">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1bba3-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="1bba3-138">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="1bba3-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="1bba3-139">[Parole chiave per operatori](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="1bba3-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="1bba3-140">[Modificatori](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="1bba3-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="1bba3-141">[Controllo delle versioni con le parole chiave Override e New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="1bba3-141">[Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span></span>  
 [<span data-ttu-id="1bba3-142">Sapere quando usare le parole chiave Override e New</span><span class="sxs-lookup"><span data-stu-id="1bba3-142">Knowing When to Use Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)

