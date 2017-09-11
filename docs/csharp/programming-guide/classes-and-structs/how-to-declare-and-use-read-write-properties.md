---
title: "Procedura: dichiarare e usare proprietà Read Write (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e5e4ca1feff203dc2ab88c0d1dfae8098508fec7
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="8f7f3-102">Procedura: dichiarare e usare proprietà Read Write (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="8f7f3-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="8f7f3-103">Le proprietà offrono i vantaggi dei membri dati pubblici senza i rischi associati all'accesso non protetto, non controllato e non verificato ai dati di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="8f7f3-104">Ciò si ottiene tramite le *funzioni di accesso*, ovvero metodi speciali che assegnano e recuperano valori dal membro dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="8f7f3-105">La funzione di accesso [set](../../../csharp/language-reference/keywords/set.md) consente l'assegnazione di valori ai membri dati, mentre la funzione di accesso [get](../../../csharp/language-reference/keywords/get.md) recupera i valori dei membri dati.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="8f7f3-106">Questo esempio mostra una classe `Person` con due proprietà: `Name` (string) e `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="8f7f3-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="8f7f3-107">Entrambe le proprietà forniscono le funzioni di accesso `get` e `set`, quindi vengono considerate proprietà di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f7f3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="8f7f3-108">Example</span></span>  
 <span data-ttu-id="8f7f3-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f7f3-109">[!code-cs[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="8f7f3-110">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="8f7f3-110">Robust Programming</span></span>  
 <span data-ttu-id="8f7f3-111">Nell'esempio precedente le proprietà `Name` e `Age` sono di tipo [public](../../../csharp/language-reference/keywords/public.md) e includono entrambe le funzioni di accesso `get` e `set`.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-111">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="8f7f3-112">Ciò consente a qualsiasi oggetto di leggere e scrivere tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-112">This allows any object to read and write these properties.</span></span> <span data-ttu-id="8f7f3-113">A volte è tuttavia preferibile escludere una delle funzioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-113">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="8f7f3-114">Se si omette la funzione di accesso `set`, ad esempio, la proprietà diventa di sola lettura:</span><span class="sxs-lookup"><span data-stu-id="8f7f3-114">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 <span data-ttu-id="8f7f3-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f7f3-115">[!code-cs[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]</span></span>  
  
 <span data-ttu-id="8f7f3-116">In alternativa è possibile esporre pubblicamente una funzione di accesso ma rendere l'altra privata o protetta.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-116">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="8f7f3-117">Per altre informazioni, vedere [Accessibilità asimmetrica delle funzioni di accesso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="8f7f3-117">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="8f7f3-118">Una volta dichiarate le proprietà, è possibile usarle come se si trattasse di campi della classe.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-118">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="8f7f3-119">Ciò consente di usare una sintassi molto semplice quando si vuole ottenere o impostare il valore di una proprietà, come nelle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8f7f3-119">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 <span data-ttu-id="8f7f3-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f7f3-120">[!code-cs[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]</span></span>  
  
 <span data-ttu-id="8f7f3-121">Si noti che in un metodo `set` di una proprietà è disponibile una variabile `value` speciale.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-121">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="8f7f3-122">Questa variabile contiene il valore specificato dall'utente, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8f7f3-122">This variable contains the value that the user specified, for example:</span></span>  
  
 <span data-ttu-id="8f7f3-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f7f3-123">[!code-cs[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]</span></span>  
  
 <span data-ttu-id="8f7f3-124">Si noti la semplice sintassi per incrementare la proprietà `Age` di un oggetto `Person`:</span><span class="sxs-lookup"><span data-stu-id="8f7f3-124">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 <span data-ttu-id="8f7f3-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f7f3-125">[!code-cs[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]</span></span>  
  
 <span data-ttu-id="8f7f3-126">Se per modellare le proprietà venissero usati metodi `set` e `get` distinti, il codice equivalente sarebbe simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8f7f3-126">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="8f7f3-127">In questo esempio viene eseguito l'override del metodo `ToString`:</span><span class="sxs-lookup"><span data-stu-id="8f7f3-127">The `ToString` method is overridden in this example:</span></span>  
  
 <span data-ttu-id="8f7f3-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="8f7f3-128">[!code-cs[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]</span></span>  
  
 <span data-ttu-id="8f7f3-129">Si noti che il metodo `ToString` non viene usato in modo esplicito nel programma.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-129">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="8f7f3-130">Viene richiamato per impostazione predefinita dalle chiamate a `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="8f7f3-130">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7f3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f7f3-131">See Also</span></span>  
 <span data-ttu-id="8f7f3-132">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8f7f3-132">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8f7f3-133">[Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="8f7f3-133">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="8f7f3-134">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="8f7f3-134">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)

