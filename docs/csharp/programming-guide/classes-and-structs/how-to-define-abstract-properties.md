---
title: Come definire le proprietà astratte-guida per programmatori C#
description: Informazioni su come definire le proprietà astratte in C#. La dichiarazione di una proprietà astratta indica che una classe supporta una proprietà. Le classi derivate implementano le funzioni di accesso.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: 4db71721495857c634e8090b986704d8a592b4e2
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864397"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="c3bf2-105">Come definire proprietà astratte (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c3bf2-105">How to define abstract properties (C# Programming Guide)</span></span>
<span data-ttu-id="c3bf2-106">L'esempio seguente mostra come definire proprietà di tipo [abstract](../../language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="c3bf2-106">The following example shows how to define [abstract](../../language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="c3bf2-107">La dichiarazione di una proprietà astratta non fornisce un'implementazione delle funzioni di accesso della proprietà. Dichiara che la classe supporta le proprietà, ma l'implementazione delle funzioni di accesso viene demandata alle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-107">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="c3bf2-108">L'esempio seguente illustra come implementare le proprietà astratte ereditate da una classe di base.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-108">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="c3bf2-109">L'esempio include tre file, ognuno dei quali viene compilato singolarmente e al cui assembly risultante viene fatto riferimento nella compilazione successiva:</span><span class="sxs-lookup"><span data-stu-id="c3bf2-109">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="c3bf2-110">abstractshape.cs: classe `Shape` che contiene una proprietà `Area` astratta.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-110">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="c3bf2-111">shapes.cs: sottoclassi della classe `Shape`.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-111">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="c3bf2-112">shapetest.cs: programma di test per la visualizzazione delle aree di alcuni oggetti derivati da `Shape`.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-112">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="c3bf2-113">Per compilare l'esempio, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c3bf2-113">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="c3bf2-114">Verrà creato il file eseguibile shapetest.exe.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-114">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3bf2-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3bf2-115">Example</span></span>  
 <span data-ttu-id="c3bf2-116">Questo file dichiara la classe `Shape` che contiene la proprietà `Area` del tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-116">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="c3bf2-117">I modificatori della proprietà vengono inseriti nella dichiarazione della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-117">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="c3bf2-118">ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c3bf2-118">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="c3bf2-119">Quando si dichiara una proprietà astratta, come `Area` in questo esempio, è sufficiente indicare le funzioni di accesso disponibili per la proprietà, senza implementarle.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-119">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="c3bf2-120">In questo esempio è disponibile solo una funzione di accesso [get](../../language-reference/keywords/get.md), quindi la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-120">In this example, only a [get](../../language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3bf2-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3bf2-121">Example</span></span>  
 <span data-ttu-id="c3bf2-122">Il codice seguente mostra tre sottoclassi di `Shape` e il modo in cui eseguono l'override della proprietà `Area` per fornire la propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-122">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="c3bf2-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="c3bf2-123">Example</span></span>  
 <span data-ttu-id="c3bf2-124">Il codice seguente mostra un programma di test che crea diversi oggetti derivati da `Shape` e stampa le relative aree.</span><span class="sxs-lookup"><span data-stu-id="c3bf2-124">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c3bf2-125">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="c3bf2-125">See also</span></span>

- [<span data-ttu-id="c3bf2-126">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c3bf2-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c3bf2-127">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="c3bf2-127">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="c3bf2-128">Classi e membri delle classi astratte e sealed</span><span class="sxs-lookup"><span data-stu-id="c3bf2-128">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="c3bf2-129">Proprietà</span><span class="sxs-lookup"><span data-stu-id="c3bf2-129">Properties</span></span>](./properties.md)
