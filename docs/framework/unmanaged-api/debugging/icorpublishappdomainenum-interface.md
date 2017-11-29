---
title: Interfaccia ICorPublishAppDomainEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishAppDomainEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishAppDomainEnum
helpviewer_keywords: ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8359eda5432a9b3818fd58f6adc18570e4c5f154
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="f604e-102">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="f604e-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="f604e-103">Una sottoclasse di [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaccia che fornisce metodi che scorrono una raccolta di [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="f604e-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f604e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f604e-104">Methods</span></span>  
  
|<span data-ttu-id="f604e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f604e-105">Method</span></span>|<span data-ttu-id="f604e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f604e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f604e-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="f604e-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="f604e-108">Ottiene il numero specificato di `ICorPublishAppDomain` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="f604e-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f604e-109">Note</span><span class="sxs-lookup"><span data-stu-id="f604e-109">Remarks</span></span>  
 <span data-ttu-id="f604e-110">Il `ICorPublishAppDomainEnum` interfaccia implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f604e-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f604e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f604e-111">Requirements</span></span>  
 <span data-ttu-id="f604e-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f604e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f604e-113">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f604e-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f604e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f604e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f604e-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f604e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f604e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f604e-116">See Also</span></span>  
 [<span data-ttu-id="f604e-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f604e-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f604e-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="f604e-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
