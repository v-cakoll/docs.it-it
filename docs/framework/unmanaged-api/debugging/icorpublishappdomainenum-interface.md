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
ms.workload: dotnet
ms.openlocfilehash: 3f84a93053744f059eb3fdd06e2fb69e098e24ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="0e936-102">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="0e936-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="0e936-103">Una sottoclasse di [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaccia che fornisce metodi che scorrono una raccolta di [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="0e936-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0e936-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0e936-104">Methods</span></span>  
  
|<span data-ttu-id="0e936-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0e936-105">Method</span></span>|<span data-ttu-id="0e936-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0e936-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0e936-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="0e936-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="0e936-108">Ottiene il numero specificato di `ICorPublishAppDomain` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="0e936-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e936-109">Note</span><span class="sxs-lookup"><span data-stu-id="0e936-109">Remarks</span></span>  
 <span data-ttu-id="0e936-110">Il `ICorPublishAppDomainEnum` interfaccia implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0e936-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e936-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0e936-111">Requirements</span></span>  
 <span data-ttu-id="0e936-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e936-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e936-113">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="0e936-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0e936-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e936-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e936-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e936-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e936-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e936-116">See Also</span></span>  
 [<span data-ttu-id="0e936-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0e936-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="0e936-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="0e936-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
