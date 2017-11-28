---
title: Creare un gruppo annidato
description: Come creare un gruppo annidato.
keywords: .NET, .NET Core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 232aa46d975d7c338bbc776e3867f2e566601fde
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2017
---
# <a name="create-a-nested-group"></a><span data-ttu-id="24e7f-104">Creare un gruppo annidato</span><span class="sxs-lookup"><span data-stu-id="24e7f-104">Create a nested group</span></span>

<span data-ttu-id="24e7f-105">Nell'esempio seguente viene illustrato come creare gruppi annidati in un'espressione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="24e7f-105">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="24e7f-106">Ogni gruppo creato in base all'anno o al livello degli studenti viene ulteriormente suddiviso in gruppi in base ai nomi delle persone.</span><span class="sxs-lookup"><span data-stu-id="24e7f-106">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24e7f-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="24e7f-107">Example</span></span>

 > [!NOTE]
 > <span data-ttu-id="24e7f-108">Questo esempio contiene riferimenti a oggetti definiti nel codice di esempio in [Eseguire una query su una raccolta di oggetti](query-a-collection-of-objects.md).</span><span class="sxs-lookup"><span data-stu-id="24e7f-108">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span> 

 [!code-csharp[csProgGuideLINQ#24](../../../samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]  
  
 <span data-ttu-id="24e7f-109">Si noti che sono necessari tre cicli `foreach` annidati per eseguire l'iterazione degli elementi interni di un gruppo annidato.</span><span class="sxs-lookup"><span data-stu-id="24e7f-109">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24e7f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24e7f-110">See also</span></span>  
 [<span data-ttu-id="24e7f-111">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="24e7f-111">LINQ Query Expressions</span></span>](index.md)
