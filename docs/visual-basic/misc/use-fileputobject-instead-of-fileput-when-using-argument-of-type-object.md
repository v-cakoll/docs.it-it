---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: df7d7c54992984bcb1684e41f60ae8361a3aed03
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2018
ms.locfileid: "53774225"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="3baa7-102">Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'</span><span class="sxs-lookup"><span data-stu-id="3baa7-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="3baa7-103">Il metodo `FilePut` include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="3baa7-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="3baa7-104">Per evitare ambiguità, è opportuno usare`FilePutObject` invece di `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="3baa7-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3baa7-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3baa7-105">To correct this error</span></span>  
  
-   <span data-ttu-id="3baa7-106">Sostituire `FilePut` con `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="3baa7-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="3baa7-107">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="3baa7-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="3baa7-108">Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="3baa7-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3baa7-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3baa7-109">See Also</span></span>  
   
 [<span data-ttu-id="3baa7-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="3baa7-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="3baa7-111">WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="3baa7-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
