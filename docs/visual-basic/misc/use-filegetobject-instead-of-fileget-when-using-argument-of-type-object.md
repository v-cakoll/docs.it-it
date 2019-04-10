---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: fdad64a4b35aa792c996d25a9fd72a9ce1126fbd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59306924"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="ed8df-102">Quando si usano argomenti di tipo 'Object', utilizzare 'FileGetObject' anziché 'FileGet'</span><span class="sxs-lookup"><span data-stu-id="ed8df-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>
<span data-ttu-id="ed8df-103">Il metodo `FileGet` include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="ed8df-103">The `FileGet` method includes an argument of type `Object`.</span></span> `FileGetObject` <span data-ttu-id="ed8df-104">invece di `FileGet` .</span><span class="sxs-lookup"><span data-stu-id="ed8df-104">should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="ed8df-105">Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="ed8df-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ed8df-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ed8df-106">To correct this error</span></span>  
  
1. <span data-ttu-id="ed8df-107">Sostituire `FileGet` con `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="ed8df-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="ed8df-108">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="ed8df-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed8df-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed8df-109">See also</span></span>

- [<span data-ttu-id="ed8df-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="ed8df-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
