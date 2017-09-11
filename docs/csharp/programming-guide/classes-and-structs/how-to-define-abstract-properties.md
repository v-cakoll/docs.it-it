---
title: "Procedura: definire proprietà astratte (Guida per programmatori C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
caps.latest.revision: 13
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
ms.openlocfilehash: c6decaae138a21c24e94e2ed74111c860777f64b
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="023be-102">Procedura: definire proprietà astratte (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="023be-102">How to: Define Abstract Properties (C# Programming Guide)</span></span>
<span data-ttu-id="023be-103">L'esempio seguente mostra come definire proprietà di tipo [abstract](../../../csharp/language-reference/keywords/abstract.md).</span><span class="sxs-lookup"><span data-stu-id="023be-103">The following example shows how to define [abstract](../../../csharp/language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="023be-104">La dichiarazione di una proprietà astratta non fornisce un'implementazione delle funzioni di accesso della proprietà. Dichiara che la classe supporta le proprietà, ma l'implementazione delle funzioni di accesso viene demandata alle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="023be-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="023be-105">L'esempio seguente illustra come implementare le proprietà astratte ereditate da una classe di base.</span><span class="sxs-lookup"><span data-stu-id="023be-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="023be-106">L'esempio include tre file, ognuno dei quali viene compilato singolarmente e al cui assembly risultante viene fatto riferimento nella compilazione successiva:</span><span class="sxs-lookup"><span data-stu-id="023be-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
-   <span data-ttu-id="023be-107">abstractshape.cs: classe `Shape` che contiene una proprietà `Area` astratta.</span><span class="sxs-lookup"><span data-stu-id="023be-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
-   <span data-ttu-id="023be-108">shapes.cs: sottoclassi della classe `Shape`.</span><span class="sxs-lookup"><span data-stu-id="023be-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
-   <span data-ttu-id="023be-109">shapetest.cs: programma di test per la visualizzazione delle aree di alcuni oggetti derivati da `Shape`.</span><span class="sxs-lookup"><span data-stu-id="023be-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="023be-110">Per compilare l'esempio, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="023be-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="023be-111">Verrà creato il file eseguibile shapetest.exe.</span><span class="sxs-lookup"><span data-stu-id="023be-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="023be-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="023be-112">Example</span></span>  
 <span data-ttu-id="023be-113">Questo file dichiara la classe `Shape` che contiene la proprietà `Area` del tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="023be-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 <span data-ttu-id="023be-114">[!code-cs[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="023be-114">[!code-cs[csProgGuideInheritance#1](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_1.cs)]</span></span>  
  
-   <span data-ttu-id="023be-115">I modificatori della proprietà vengono inseriti nella dichiarazione della proprietà stessa.</span><span class="sxs-lookup"><span data-stu-id="023be-115">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="023be-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="023be-116">For example:</span></span>  
  
    ```  
    public abstract double Area  
    ```  
  
-   <span data-ttu-id="023be-117">Quando si dichiara una proprietà astratta, come `Area` in questo esempio, è sufficiente indicare le funzioni di accesso disponibili per la proprietà, senza implementarle.</span><span class="sxs-lookup"><span data-stu-id="023be-117">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="023be-118">In questo esempio è disponibile solo una funzione di accesso [get](../../../csharp/language-reference/keywords/get.md), quindi la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="023be-118">In this example, only a [get](../../../csharp/language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="023be-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="023be-119">Example</span></span>  
 <span data-ttu-id="023be-120">Il codice seguente mostra tre sottoclassi di `Shape` e il modo in cui eseguono l'override della proprietà `Area` per fornire la propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="023be-120">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 <span data-ttu-id="023be-121">[!code-cs[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="023be-121">[!code-cs[csProgGuideInheritance#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="023be-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="023be-122">Example</span></span>  
 <span data-ttu-id="023be-123">Il codice seguente mostra un programma di test che crea diversi oggetti derivati da `Shape` e stampa le relative aree.</span><span class="sxs-lookup"><span data-stu-id="023be-123">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 <span data-ttu-id="023be-124">[!code-cs[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="023be-124">[!code-cs[csProgGuideInheritance#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-define-abstract-properties_3.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="023be-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="023be-125">See Also</span></span>  
 <span data-ttu-id="023be-126">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="023be-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="023be-127">[Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="023be-127">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="023be-128">[Classi e membri delle classi astratte e sealed](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span><span class="sxs-lookup"><span data-stu-id="023be-128">[Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) </span></span>  
 <span data-ttu-id="023be-129">[Proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md) </span><span class="sxs-lookup"><span data-stu-id="023be-129">[Properties](../../../csharp/programming-guide/classes-and-structs/properties.md) </span></span>  
 [<span data-ttu-id="023be-130">Procedura: Creare e usare assembly dalla riga di comando</span><span class="sxs-lookup"><span data-stu-id="023be-130">How to: Create and Use Assemblies Using the Command Line</span></span>](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)

