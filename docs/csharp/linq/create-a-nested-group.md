---
title: Creare un gruppo annidato
description: Come creare un gruppo annidato.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 361ac1f224c6eef292fcf8434c7e465c9448b19c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-nested-group"></a><span data-ttu-id="16b60-104">Creare un gruppo annidato</span><span class="sxs-lookup"><span data-stu-id="16b60-104">Create a nested group</span></span>

<span data-ttu-id="16b60-105">Nell'esempio seguente viene illustrato come creare gruppi annidati in un'espressione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="16b60-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="16b60-106">Ogni gruppo creato in base all'anno o al livello degli studenti viene ulteriormente suddiviso in gruppi in base ai nomi delle persone.</span><span class="sxs-lookup"><span data-stu-id="16b60-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16b60-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="16b60-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="16b60-108">Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="16b60-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 <span data-ttu-id="16b60-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="16b60-109">[!code-cs[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]</span></span>  
  
 <span data-ttu-id="16b60-110">Si noti che sono necessari tre cicli `foreach` annidati per eseguire l'iterazione degli elementi interni di un gruppo annidato.</span><span class="sxs-lookup"><span data-stu-id="16b60-110">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b60-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b60-111">See also</span></span>  
 [<span data-ttu-id="16b60-112">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="16b60-112">LINQ Query Expressions</span></span>](index.md)

