---
title: Proprietà dell'interfaccia - Guida per programmatori C#
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: cdd425970442e284d6fd6488bbb13394c12e939a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596444"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="6ef03-102">Proprietà dell'interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="6ef03-102">Interface Properties (C# Programming Guide)</span></span>
<span data-ttu-id="6ef03-103">Le proprietà possono essere dichiarate su una [interfaccia](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="6ef03-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="6ef03-104">Nell'esempio seguente viene illustrata la funzione di accesso di una proprietà di interfaccia:</span><span class="sxs-lookup"><span data-stu-id="6ef03-104">The following is an example of an interface property accessor:</span></span>  
  
 [!code-csharp[csProgGuideProperties#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#14)]  
  
 <span data-ttu-id="6ef03-105">La funzione di accesso di una proprietà di interfaccia non ha un corpo.</span><span class="sxs-lookup"><span data-stu-id="6ef03-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="6ef03-106">Lo scopo delle funzioni di accesso, pertanto, è quello di indicare se la proprietà è in lettura-scrittura, in sola lettura o in sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="6ef03-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ef03-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ef03-107">Example</span></span>  
 <span data-ttu-id="6ef03-108">Nell'esempio seguente l'interfaccia `IEmployee` include una proprietà in lettura-scrittura, `Name`, e una proprietà in sola lettura, `Counter`.</span><span class="sxs-lookup"><span data-stu-id="6ef03-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="6ef03-109">La classe `Employee` implementa l'interfaccia `IEmployee` e usa le due proprietà.</span><span class="sxs-lookup"><span data-stu-id="6ef03-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="6ef03-110">Il programma legge il nome di un nuovo dipendente e il numero corrente di dipendenti e quindi visualizza il nome del dipendente e il relativo numero calcolato.</span><span class="sxs-lookup"><span data-stu-id="6ef03-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>  
  
 <span data-ttu-id="6ef03-111">È possibile usare il nome completo della proprietà, che fa riferimento all'interfaccia in cui il membro è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="6ef03-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="6ef03-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6ef03-112">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]  
  
 <span data-ttu-id="6ef03-113">Questo meccanismo è denominato [Implementazione esplicita dell'interfaccia](../interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="6ef03-113">This is called [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="6ef03-114">Se la classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce includono la proprietà `Name`, sarà necessaria l'implementazione esplicita del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="6ef03-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="6ef03-115">In altre parole, la dichiarazione di proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="6ef03-115">That is, the following property declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#16)]  
  
 <span data-ttu-id="6ef03-116">implementa la proprietà `Name` nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="6ef03-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#17)]  
  
 <span data-ttu-id="6ef03-117">implementa la proprietà `Name` nell'interfaccia `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="6ef03-117">implements the `Name` property on the `ICitizen` interface.</span></span>  
  
 [!code-csharp[csProgGuideProperties#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideProperties/CS/Properties.cs#15)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a><span data-ttu-id="6ef03-118">Esempio di output</span><span class="sxs-lookup"><span data-stu-id="6ef03-118">Sample Output</span></span>  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a><span data-ttu-id="6ef03-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ef03-119">See also</span></span>

- [<span data-ttu-id="6ef03-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="6ef03-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6ef03-121">Proprietà</span><span class="sxs-lookup"><span data-stu-id="6ef03-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="6ef03-122">Uso delle proprietà</span><span class="sxs-lookup"><span data-stu-id="6ef03-122">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="6ef03-123">Confronto tra proprietà e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="6ef03-123">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="6ef03-124">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="6ef03-124">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="6ef03-125">Interfacce</span><span class="sxs-lookup"><span data-stu-id="6ef03-125">Interfaces</span></span>](../interfaces/index.md)
