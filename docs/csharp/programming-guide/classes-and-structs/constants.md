---
title: Costanti (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 1fb39621-1738-49b1-a1b3-8587f109123f
caps.latest.revision: 24
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
ms.openlocfilehash: 85273420e9e0dbf4b8f24568d97be127c85d5f42
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="constants-c-programming-guide"></a><span data-ttu-id="10b8a-102">Costanti (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="10b8a-102">Constants (C# Programming Guide)</span></span>
<span data-ttu-id="10b8a-103">Le costanti sono valori non modificabili, che sono noti nella fase di compilazione e non cambiano per la durata del programma.</span><span class="sxs-lookup"><span data-stu-id="10b8a-103">Constants are immutable values which are known at compile time and do not change for the life of the program.</span></span> <span data-ttu-id="10b8a-104">Le costanti vengono dichiarate con il modificatore [const](../../../csharp/language-reference/keywords/const.md).</span><span class="sxs-lookup"><span data-stu-id="10b8a-104">Constants are declared with the [const](../../../csharp/language-reference/keywords/const.md) modifier.</span></span> <span data-ttu-id="10b8a-105">Solo i tipi incorporati C# (ad esclusione di <xref:System.Object?displayProperty=fullName>) possono essere dichiarati come `const`.</span><span class="sxs-lookup"><span data-stu-id="10b8a-105">Only the C# built-in types (excluding <xref:System.Object?displayProperty=fullName>) may be declared as `const`.</span></span> <span data-ttu-id="10b8a-106">Per l'elenco dei tipi incorporati, vedere [Tabella dei tipi incorporati](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="10b8a-106">For a list of the built-in types, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span> <span data-ttu-id="10b8a-107">I tipi definiti dall'utente, incluse le classi, gli struct e le matrici, non possono essere `const`.</span><span class="sxs-lookup"><span data-stu-id="10b8a-107">User-defined types, including classes, structs, and arrays, cannot be `const`.</span></span> <span data-ttu-id="10b8a-108">Usare il modificatore [readonly](../../../csharp/language-reference/keywords/readonly.md) per creare una classe, una matrice o uno struct che viene inizializzato una sola volta in fase di runtime (ad esempio in un costruttore) e successivamente non può più essere modificato.</span><span class="sxs-lookup"><span data-stu-id="10b8a-108">Use the [readonly](../../../csharp/language-reference/keywords/readonly.md) modifier to create a class, struct, or array that is initialized one time at runtime (for example in a constructor) and thereafter cannot be changed.</span></span>  
  
 <span data-ttu-id="10b8a-109">C# non supporta metodi, proprietà o eventi `const`.</span><span class="sxs-lookup"><span data-stu-id="10b8a-109">C# does not support `const` methods, properties, or events.</span></span>  
  
 <span data-ttu-id="10b8a-110">Il tipo enum consente di definire costanti denominate per i tipi incorporati interi (ad esempio `int`, `uint`, `long` e così via).</span><span class="sxs-lookup"><span data-stu-id="10b8a-110">The enum type enables you to define named constants for integral built-in types (for example `int`, `uint`, `long`, and so on).</span></span> <span data-ttu-id="10b8a-111">Per altre informazioni, vedere [enum](../../../csharp/language-reference/keywords/enum.md).</span><span class="sxs-lookup"><span data-stu-id="10b8a-111">For more information, see [enum](../../../csharp/language-reference/keywords/enum.md).</span></span>  
  
 <span data-ttu-id="10b8a-112">Le costanti devono essere inizializzate come vengono dichiarate.</span><span class="sxs-lookup"><span data-stu-id="10b8a-112">Constants must be initialized as they are declared.</span></span> <span data-ttu-id="10b8a-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="10b8a-113">For example:</span></span>  
  
 <span data-ttu-id="10b8a-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="10b8a-114">[!code-cs[csProgGuideObjects#64](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_1.cs)]</span></span>  
  
 <span data-ttu-id="10b8a-115">In questo esempio la costante `months` è sempre 12 e non può essere modificata neanche dalla stessa classe.</span><span class="sxs-lookup"><span data-stu-id="10b8a-115">In this example, the constant `months` is always 12, and it cannot be changed even by the class itself.</span></span> <span data-ttu-id="10b8a-116">In realtà, quando il compilatore incontra un identificatore costante nel codice sorgente C# (ad esempio `months`), lo sostituisce direttamente con il relativo valore letterale nel codice Intermediate Language (IL) che produce.</span><span class="sxs-lookup"><span data-stu-id="10b8a-116">In fact, when the compiler encounters a constant identifier in C# source code (for example, `months`), it substitutes the literal value directly into the intermediate language (IL) code that it produces.</span></span> <span data-ttu-id="10b8a-117">Poiché non esiste alcun indirizzo di variabile associato a una costante in fase di esecuzione, i campi `const` non possono essere passati per riferimento e non possono sostituire un l-value in un'espressione.</span><span class="sxs-lookup"><span data-stu-id="10b8a-117">Because there is no variable address associated with a constant at run time, `const` fields cannot be passed by reference and cannot appear as an l-value in an expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10b8a-118">Prestare attenzione quando si creano riferimenti a valori costanti definiti in un altro codice, ad esempio in file DLL.</span><span class="sxs-lookup"><span data-stu-id="10b8a-118">Use caution when you refer to constant values defined in other code such as DLLs.</span></span> <span data-ttu-id="10b8a-119">Se una nuova versione della DLL definisce un nuovo valore per la costante, il programma mantiene il vecchio valore letterale finché non viene ricompilato per la nuova versione.</span><span class="sxs-lookup"><span data-stu-id="10b8a-119">If a new version of the DLL defines a new value for the constant, your program will still hold the old literal value until it is recompiled against the new version.</span></span>  
  
 <span data-ttu-id="10b8a-120">È possibile dichiarare contemporaneamente più costanti dello stesso tipo, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="10b8a-120">Multiple constants of the same type can be declared at the same time, for example:</span></span>  
  
 <span data-ttu-id="10b8a-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="10b8a-121">[!code-cs[csProgGuideObjects#65](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_2.cs)]</span></span>  
  
 <span data-ttu-id="10b8a-122">L'espressione usata per inizializzare una costante può fare riferimento a un'altra costante, a condizione che crei un riferimento circolare.</span><span class="sxs-lookup"><span data-stu-id="10b8a-122">The expression that is used to initialize a constant can refer to another constant if it does not create a circular reference.</span></span> <span data-ttu-id="10b8a-123">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="10b8a-123">For example:</span></span>  
  
 <span data-ttu-id="10b8a-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="10b8a-124">[!code-cs[csProgGuideObjects#66](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_3.cs)]</span></span>  
  
 <span data-ttu-id="10b8a-125">Le costanti possono essere contrassegnate come [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) o `protected internal`.</span><span class="sxs-lookup"><span data-stu-id="10b8a-125">Constants can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), or `protected internal`.</span></span> <span data-ttu-id="10b8a-126">Questi modificatori definiscono l'accesso alla costante per gli utenti della classe.</span><span class="sxs-lookup"><span data-stu-id="10b8a-126">These access modifiers define how users of the class can access the constant.</span></span> <span data-ttu-id="10b8a-127">Per altre informazioni, vedere [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="10b8a-127">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="10b8a-128">L’accesso alle costanti avviene come se fossero campi [statici](../../../csharp/language-reference/keywords/static.md), perché il valore della costante è lo stesso per tutte le istanze del tipo.</span><span class="sxs-lookup"><span data-stu-id="10b8a-128">Constants are accessed as if they were [static](../../../csharp/language-reference/keywords/static.md) fields because the value of the constant is the same for all instances of the type.</span></span> <span data-ttu-id="10b8a-129">Per dichiararle non viene usata la parola chiave `static`.</span><span class="sxs-lookup"><span data-stu-id="10b8a-129">You do not use the `static` keyword to declare them.</span></span> <span data-ttu-id="10b8a-130">Per accedere alla costante, le espressioni non incluse nella classe che la definisce devono usare il nome della classe seguito da un punto e dal nome della costante stessa.</span><span class="sxs-lookup"><span data-stu-id="10b8a-130">Expressions that are not in the class that defines the constant must use the class name, a period, and the name of the constant to access the constant.</span></span> <span data-ttu-id="10b8a-131">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="10b8a-131">For example:</span></span>  
  
 <span data-ttu-id="10b8a-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="10b8a-132">[!code-cs[csProgGuideObjects#67](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/constants_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="10b8a-133">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="10b8a-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="10b8a-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10b8a-134">See Also</span></span>  
 <span data-ttu-id="10b8a-135">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="10b8a-135">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="10b8a-136">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="10b8a-136">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="10b8a-137">[Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="10b8a-137">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 <span data-ttu-id="10b8a-138">[Tipi](../../../csharp/programming-guide/types/index.md) </span><span class="sxs-lookup"><span data-stu-id="10b8a-138">[Types](../../../csharp/programming-guide/types/index.md) </span></span>  
 <span data-ttu-id="10b8a-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span><span class="sxs-lookup"><span data-stu-id="10b8a-139">[readonly](../../../csharp/language-reference/keywords/readonly.md) </span></span>  
 <span data-ttu-id="10b8a-140">[Immutability in C# Part One: Kinds of Immutability](http://go.microsoft.com/fwlink/?LinkId=112379) (Immutabilità in C# - Parte 1: tipi di immutabilità)</span><span class="sxs-lookup"><span data-stu-id="10b8a-140">[Immutability in C# Part One: Kinds of Immutability](http://go.microsoft.com/fwlink/?LinkId=112379)</span></span>

