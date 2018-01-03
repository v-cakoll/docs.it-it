---
title: Usa &#39; FileGetObject &#39; invece di &#39; FileGet &#39; Quando si usano argomenti di tipo &#39; oggetto &#39;
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 090b8088-895a-482a-9362-606596bac304
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2c5be466a8a0339bdb57818755d85a26d632d774
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="use-39filegetobject39-instead-of-39fileget39-when-using-argument-of-type-39object39"></a><span data-ttu-id="f2891-102">Usa &#39; FileGetObject &#39; invece di &#39; FileGet &#39; Quando si usano argomenti di tipo &#39; oggetto &#39;</span><span class="sxs-lookup"><span data-stu-id="f2891-102">Use &#39;FileGetObject&#39; instead of &#39;FileGet&#39; when using argument of type &#39;Object&#39;</span></span>
<span data-ttu-id="f2891-103">Il metodo `FileGet` include un argomento di tipo `Object`.</span><span class="sxs-lookup"><span data-stu-id="f2891-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="f2891-104">Per evitare ambiguità, è opportuno usare`FileGetObject` invece di `FileGet` .</span><span class="sxs-lookup"><span data-stu-id="f2891-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="f2891-105">Si noti che la funzionalità offerta da `My.Computer.Filesystem` garantisce una maggiore facilità d'uso e prestazioni superiori sia rispetto a `FileGet` che a `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="f2891-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2891-106">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="f2891-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f2891-107">Sostituire `FileGet` con `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="f2891-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2.  <span data-ttu-id="f2891-108">Eseguire il cast dell'argomento `Object` su un tipo più specifico.</span><span class="sxs-lookup"><span data-stu-id="f2891-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2891-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2891-109">See Also</span></span>  
   
 [<span data-ttu-id="f2891-110">FileSystem</span><span class="sxs-lookup"><span data-stu-id="f2891-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
