---
title: 'Procedura: Dichiarare e usare proprietà Read Write - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 348fcf6605030396095a2d94970ffe46e8d19357
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241840"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="44e34-102">Procedura: Dichiarare e usare proprietà Read Write (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="44e34-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="44e34-103">Le proprietà offrono i vantaggi dei membri dati pubblici senza i rischi associati all'accesso non protetto, non controllato e non verificato ai dati di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="44e34-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="44e34-104">Ciò si ottiene tramite le *funzioni di accesso*, ovvero metodi speciali che assegnano e recuperano valori dal membro dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="44e34-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="44e34-105">La funzione di accesso [set](../../../csharp/language-reference/keywords/set.md) consente l'assegnazione di valori ai membri dati, mentre la funzione di accesso [get](../../../csharp/language-reference/keywords/get.md) recupera i valori dei membri dati.</span><span class="sxs-lookup"><span data-stu-id="44e34-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="44e34-106">Questo esempio mostra una classe `Person` con due proprietà: `Name` (string) e `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="44e34-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="44e34-107">Entrambe le proprietà forniscono le funzioni di accesso `get` e `set`, quindi vengono considerate proprietà di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="44e34-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44e34-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="44e34-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="44e34-109">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="44e34-109">Robust Programming</span></span>  
 <span data-ttu-id="44e34-110">Nell'esempio precedente le proprietà `Name` e `Age` sono di tipo [public](../../../csharp/language-reference/keywords/public.md) e includono entrambe le funzioni di accesso `get` e `set`.</span><span class="sxs-lookup"><span data-stu-id="44e34-110">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="44e34-111">Ciò consente a qualsiasi oggetto di leggere e scrivere tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="44e34-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="44e34-112">A volte è tuttavia preferibile escludere una delle funzioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="44e34-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="44e34-113">Se si omette la funzione di accesso `set`, ad esempio, la proprietà diventa di sola lettura:</span><span class="sxs-lookup"><span data-stu-id="44e34-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 <span data-ttu-id="44e34-114">In alternativa è possibile esporre pubblicamente una funzione di accesso ma rendere l'altra privata o protetta.</span><span class="sxs-lookup"><span data-stu-id="44e34-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="44e34-115">Per altre informazioni, vedere [Accessibilità asimmetrica delle funzioni di accesso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="44e34-115">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="44e34-116">Una volta dichiarate le proprietà, è possibile usarle come se si trattasse di campi della classe.</span><span class="sxs-lookup"><span data-stu-id="44e34-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="44e34-117">Ciò consente di usare una sintassi molto semplice quando si vuole ottenere o impostare il valore di una proprietà, come nelle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44e34-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 <span data-ttu-id="44e34-118">Si noti che in un metodo `set` di una proprietà è disponibile una variabile `value` speciale.</span><span class="sxs-lookup"><span data-stu-id="44e34-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="44e34-119">Questa variabile contiene il valore specificato dall'utente, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="44e34-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 <span data-ttu-id="44e34-120">Si noti la semplice sintassi per incrementare la proprietà `Age` di un oggetto `Person`:</span><span class="sxs-lookup"><span data-stu-id="44e34-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 <span data-ttu-id="44e34-121">Se per modellare le proprietà venissero usati metodi `set` e `get` distinti, il codice equivalente sarebbe simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="44e34-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="44e34-122">In questo esempio viene eseguito l'override del metodo `ToString`:</span><span class="sxs-lookup"><span data-stu-id="44e34-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 <span data-ttu-id="44e34-123">Si noti che il metodo `ToString` non viene usato in modo esplicito nel programma.</span><span class="sxs-lookup"><span data-stu-id="44e34-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="44e34-124">Viene richiamato per impostazione predefinita dalle chiamate a `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="44e34-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e34-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44e34-125">See Also</span></span>

- [<span data-ttu-id="44e34-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="44e34-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="44e34-127">Proprietà</span><span class="sxs-lookup"><span data-stu-id="44e34-127">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
- [<span data-ttu-id="44e34-128">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="44e34-128">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
