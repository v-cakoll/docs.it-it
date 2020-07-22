---
title: Come dichiarare e usare le proprietà di lettura/scrittura-Guida per programmatori C#
description: Informazioni su come usare le proprietà di lettura/scrittura in C#. Questo esempio include due proprietà, ognuna delle quali dispone di funzioni di accesso get e set, quindi le proprietà sono di lettura/scrittura.
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 08bdaa9446491d473cfb16e3b82bac41d7af5b79
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864449"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="641c6-104">Come dichiarare e usare le proprietà di lettura/scrittura (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="641c6-104">How to declare and use read write properties (C# Programming Guide)</span></span>
<span data-ttu-id="641c6-105">Le proprietà offrono i vantaggi dei membri dati pubblici senza i rischi associati all'accesso non protetto, non controllato e non verificato ai dati di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="641c6-105">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="641c6-106">Ciò si ottiene tramite le *funzioni di accesso*, ovvero metodi speciali che assegnano e recuperano valori dal membro dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="641c6-106">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="641c6-107">La funzione di accesso [set](../../language-reference/keywords/set.md) consente l'assegnazione di valori ai membri dati, mentre la funzione di accesso [get](../../language-reference/keywords/get.md) recupera i valori dei membri dati.</span><span class="sxs-lookup"><span data-stu-id="641c6-107">The [set](../../language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="641c6-108">Questo esempio mostra una classe `Person` con due proprietà: `Name` (string) e `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="641c6-108">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="641c6-109">Entrambe le proprietà forniscono le funzioni di accesso `get` e `set`, quindi vengono considerate proprietà di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="641c6-109">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="641c6-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="641c6-110">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a><span data-ttu-id="641c6-111">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="641c6-111">Robust Programming</span></span>  
 <span data-ttu-id="641c6-112">Nell'esempio precedente le proprietà `Name` e `Age` sono di tipo [public](../../language-reference/keywords/public.md) e includono entrambe le funzioni di accesso `get` e `set`.</span><span class="sxs-lookup"><span data-stu-id="641c6-112">In the previous example, the `Name` and `Age` properties are [public](../../language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="641c6-113">Ciò consente a qualsiasi oggetto di leggere e scrivere tali proprietà.</span><span class="sxs-lookup"><span data-stu-id="641c6-113">This allows any object to read and write these properties.</span></span> <span data-ttu-id="641c6-114">A volte è tuttavia preferibile escludere una delle funzioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="641c6-114">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="641c6-115">Se si omette la funzione di accesso `set`, ad esempio, la proprietà diventa di sola lettura:</span><span class="sxs-lookup"><span data-stu-id="641c6-115">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 <span data-ttu-id="641c6-116">In alternativa è possibile esporre pubblicamente una funzione di accesso ma rendere l'altra privata o protetta.</span><span class="sxs-lookup"><span data-stu-id="641c6-116">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="641c6-117">Per altre informazioni, vedere [Accessibilità asimmetrica delle funzioni di accesso](./restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="641c6-117">For more information, see [Asymmetric Accessor Accessibility](./restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="641c6-118">Una volta dichiarate le proprietà, è possibile usarle come se si trattasse di campi della classe.</span><span class="sxs-lookup"><span data-stu-id="641c6-118">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="641c6-119">Ciò consente di usare una sintassi molto semplice quando si vuole ottenere o impostare il valore di una proprietà, come nelle istruzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="641c6-119">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 <span data-ttu-id="641c6-120">Si noti che in un metodo `set` di una proprietà è disponibile una variabile `value` speciale.</span><span class="sxs-lookup"><span data-stu-id="641c6-120">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="641c6-121">Questa variabile contiene il valore specificato dall'utente, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="641c6-121">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 <span data-ttu-id="641c6-122">Si noti la semplice sintassi per incrementare la proprietà `Age` di un oggetto `Person`:</span><span class="sxs-lookup"><span data-stu-id="641c6-122">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 <span data-ttu-id="641c6-123">Se per modellare le proprietà venissero usati metodi `set` e `get` distinti, il codice equivalente sarebbe simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="641c6-123">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);
```  
  
 <span data-ttu-id="641c6-124">In questo esempio viene eseguito l'override del metodo `ToString`:</span><span class="sxs-lookup"><span data-stu-id="641c6-124">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 <span data-ttu-id="641c6-125">Si noti che il metodo `ToString` non viene usato in modo esplicito nel programma.</span><span class="sxs-lookup"><span data-stu-id="641c6-125">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="641c6-126">Viene richiamato per impostazione predefinita dalle chiamate a `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="641c6-126">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="641c6-127">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="641c6-127">See also</span></span>

- [<span data-ttu-id="641c6-128">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="641c6-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="641c6-129">Proprietà</span><span class="sxs-lookup"><span data-stu-id="641c6-129">Properties</span></span>](./properties.md)
- [<span data-ttu-id="641c6-130">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="641c6-130">Classes and Structs</span></span>](./index.md)
