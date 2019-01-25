---
title: Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 3d793151905c61ee12eccdfdb5e9567a4924bb35
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725558"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="85592-102">Quando si usano argomenti di tipo 'Object', utilizzare 'FilePutObject' anziché 'FilePut'</span><span class="sxs-lookup"><span data-stu-id="85592-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>
<span data-ttu-id="85592-103">Il metodo `FilePut` include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="85592-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="85592-104">Per evitare ambiguità, è opportuno usare`FilePutObject` invece di `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="85592-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="85592-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="85592-105">To correct this error</span></span>  
  
-   <span data-ttu-id="85592-106">Sostituire `FilePut` con `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="85592-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="85592-107">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="85592-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="85592-108">Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="85592-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85592-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85592-109">See also</span></span>

- [<span data-ttu-id="85592-110">My.Computer.FileSystem</span><span class="sxs-lookup"><span data-stu-id="85592-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="85592-111">My.Computer.FileSystem.WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="85592-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
