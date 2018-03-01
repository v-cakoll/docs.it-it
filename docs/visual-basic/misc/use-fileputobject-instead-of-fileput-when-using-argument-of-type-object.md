---
title: Usa &#39; FilePutObject &#39; invece di &#39; FilePut &#39; Quando si usano argomenti di tipo &#39; oggetto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5612c2bd4dc08f767643d2cd865a2ba1a8210c15
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="use-39fileputobject39-instead-of-39fileput39-when-using-argument-of-type-39object39"></a><span data-ttu-id="3a4f5-102">Usa &#39; FilePutObject &#39; invece di &#39; FilePut &#39; Quando si usano argomenti di tipo &#39; oggetto &#39;</span><span class="sxs-lookup"><span data-stu-id="3a4f5-102">Use &#39;FilePutObject&#39; instead of &#39;FilePut&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="3a4f5-103">Il `FilePut` metodo include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="3a4f5-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="3a4f5-104">Per evitare ambiguità, è opportuno usare`FilePutObject` invece di `FilePut` .</span><span class="sxs-lookup"><span data-stu-id="3a4f5-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3a4f5-105">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="3a4f5-105">To correct this error</span></span>  
  
-   <span data-ttu-id="3a4f5-106">Sostituire `FilePut` con `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="3a4f5-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
-   <span data-ttu-id="3a4f5-107">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="3a4f5-107">Cast the `Object` argument to a more specific type.</span></span>  
  
-   <span data-ttu-id="3a4f5-108">Usare la funzionalità disponibile nell'oggetto `My.Computer.FileSystem` .</span><span class="sxs-lookup"><span data-stu-id="3a4f5-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a4f5-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a4f5-109">See Also</span></span>  
   
 [<span data-ttu-id="3a4f5-110">FileSystem</span><span class="sxs-lookup"><span data-stu-id="3a4f5-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)  
 [<span data-ttu-id="3a4f5-111">WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="3a4f5-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
