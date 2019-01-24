---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 60eaabc686070aced908116728f06d4e82b5cecb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723394"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="b8d2e-102">Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'</span><span class="sxs-lookup"><span data-stu-id="b8d2e-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>
<span data-ttu-id="b8d2e-103">Il metodo `FileGet` include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="b8d2e-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="b8d2e-104">Per evitare ambiguità, è opportuno usare`FileGetObject` invece di `FileGet` .</span><span class="sxs-lookup"><span data-stu-id="b8d2e-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="b8d2e-105">Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="b8d2e-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b8d2e-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="b8d2e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="b8d2e-107">Sostituire `FileGet` con `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="b8d2e-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="b8d2e-108">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="b8d2e-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d2e-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8d2e-109">See also</span></span>

- [<span data-ttu-id="b8d2e-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="b8d2e-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
