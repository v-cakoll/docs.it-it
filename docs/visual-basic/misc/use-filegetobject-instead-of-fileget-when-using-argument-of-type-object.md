---
title: Utilizzare &#39;FileGetObject&#39; anziché &#39;FileGet&#39; quando si usano argomenti di tipo &#39;oggetto&#39;
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 2edb80f6df95774e0ea5a7b51e57925845d7ba75
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640417"
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="5681c-102">Utilizzare &#39;FileGetObject&#39; anziché &#39;FileGet&#39; quando si usano argomenti di tipo &#39;oggetto&#39;</span><span class="sxs-lookup"><span data-stu-id="5681c-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="5681c-103">Il metodo `FileGet` include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="5681c-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="5681c-104">Per evitare ambiguità, è opportuno usare`FileGetObject` invece di `FileGet` .</span><span class="sxs-lookup"><span data-stu-id="5681c-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="5681c-105">Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="5681c-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="5681c-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="5681c-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="5681c-107">Sostituire `FileGet` con `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="5681c-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="5681c-108">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="5681c-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5681c-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5681c-109">See Also</span></span>  
   
 [<span data-ttu-id="5681c-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="5681c-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
