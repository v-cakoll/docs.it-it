---
title: Utilizzare &#39;FilePutObject&#39; anziché &#39;FilePut&#39; quando si usano argomenti di tipo &#39;oggetto&#39;
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 529352d98c175981c20861205ce04c8a2ebcdca9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641128"
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="ba6c7-102">Utilizzare &#39;FilePutObject&#39; anziché &#39;FilePut&#39; quando si usano argomenti di tipo &#39;oggetto&#39;</span><span class="sxs-lookup"><span data-stu-id="ba6c7-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="ba6c7-103">Il `FilePut` metodo include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="ba6c7-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="ba6c7-104">Per evitare ambiguità, è opportuno usare`FilePutObject` invece di `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="ba6c7-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ba6c7-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="ba6c7-105">To correct this error</span></span>  
  
-   <span data-ttu-id="ba6c7-106">Sostituire `FilePut` con `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="ba6c7-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="ba6c7-107">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="ba6c7-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="ba6c7-108">Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="ba6c7-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba6c7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba6c7-109">See Also</span></span>  
   
 [<span data-ttu-id="ba6c7-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="ba6c7-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="ba6c7-111">WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="ba6c7-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
