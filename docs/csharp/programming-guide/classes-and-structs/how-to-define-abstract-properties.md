---
title: Come definire le proprietà astratte C# -Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: c46f36133b68a550a17cf882844fd2481eee8851
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705613"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="67930-102">Come definire le proprietà astratteC# (Guida per programmatori)</span><span class="sxs-lookup"><span data-stu-id="67930-102">How to define abstract properties (C# Programming Guide)</span></span>
<span data-ttu-id="67930-103">L'esempio seguente mostra come definire proprietà di tipo [abstract](../../language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="67930-103">The following example shows how to define [abstract](../../language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="67930-104">La dichiarazione di una proprietà astratta non fornisce un'implementazione delle funzioni di accesso della proprietà. Dichiara che la classe supporta le proprietà, ma l'implementazione delle funzioni di accesso viene demandata alle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="67930-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="67930-105">L'esempio seguente illustra come implementare le proprietà astratte ereditate da una classe di base.</span><span class="sxs-lookup"><span data-stu-id="67930-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="67930-106">L'esempio include tre file, ognuno dei quali viene compilato singolarmente e al cui assembly risultante viene fatto riferimento nella compilazione successiva:</span><span class="sxs-lookup"><span data-stu-id="67930-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="67930-107">abstractshape.cs: classe `Shape` che contiene una proprietà `Area` astratta.</span><span class="sxs-lookup"><span data-stu-id="67930-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="67930-108">shapes.cs: sottoclassi della classe `Shape`.</span><span class="sxs-lookup"><span data-stu-id="67930-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="67930-109">shapetest.cs: programma di test per la visualizzazione delle aree di alcuni oggetti derivati da `Shape`.</span><span class="sxs-lookup"><span data-stu-id="67930-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="67930-110">Per compilare l'esempio, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="67930-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="67930-111">Verrà creato il file eseguibile shapetest.exe.</span><span class="sxs-lookup"><span data-stu-id="67930-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67930-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="67930-112">Example</span></span>  
 <span data-ttu-id="67930-113">Questo file dichiara la classe `Shape` che contiene la proprietà `Area` del tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="67930-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="67930-114">I modificatori della proprietà vengono inseriti nella dichiarazione della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="67930-114">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="67930-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="67930-115">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="67930-116">Quando si dichiara una proprietà astratta, come `Area` in questo esempio, è sufficiente indicare le funzioni di accesso disponibili per la proprietà, senza implementarle.</span><span class="sxs-lookup"><span data-stu-id="67930-116">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="67930-117">In questo esempio è disponibile solo una funzione di accesso [get](../../language-reference/keywords/get.md), quindi la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="67930-117">In this example, only a [get](../../language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67930-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="67930-118">Example</span></span>  
 <span data-ttu-id="67930-119">Il codice seguente mostra tre sottoclassi di `Shape` e il modo in cui eseguono l'override della proprietà `Area` per fornire la propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="67930-119">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="67930-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="67930-120">Example</span></span>  
 <span data-ttu-id="67930-121">Il codice seguente mostra un programma di test che crea diversi oggetti derivati da `Shape` e stampa le relative aree.</span><span class="sxs-lookup"><span data-stu-id="67930-121">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="67930-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67930-122">See also</span></span>

- [<span data-ttu-id="67930-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="67930-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="67930-124">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="67930-124">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="67930-125">Classi e membri delle classi astratte e sealed</span><span class="sxs-lookup"><span data-stu-id="67930-125">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="67930-126">Proprietà</span><span class="sxs-lookup"><span data-stu-id="67930-126">Properties</span></span>](./properties.md)
