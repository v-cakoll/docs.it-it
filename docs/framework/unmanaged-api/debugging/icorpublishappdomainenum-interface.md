---
title: Interfaccia ICorPublishAppDomainEnum
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 610f62274aea88c1d5f9bbe1456685aa1d3bca68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423741"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="97704-102">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="97704-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="97704-103">Una sottoclasse di [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaccia che fornisce metodi che scorrono una raccolta di [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti attualmente esistenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="97704-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97704-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="97704-104">Methods</span></span>  
  
|<span data-ttu-id="97704-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="97704-105">Method</span></span>|<span data-ttu-id="97704-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97704-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="97704-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="97704-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="97704-108">Ottiene il numero specificato di `ICorPublishAppDomain` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="97704-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97704-109">Note</span><span class="sxs-lookup"><span data-stu-id="97704-109">Remarks</span></span>  
 <span data-ttu-id="97704-110">Il `ICorPublishAppDomainEnum` interfaccia implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="97704-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97704-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97704-111">Requirements</span></span>  
 <span data-ttu-id="97704-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97704-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97704-113">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="97704-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="97704-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="97704-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97704-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97704-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97704-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97704-116">See Also</span></span>  
 [<span data-ttu-id="97704-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="97704-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="97704-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="97704-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
