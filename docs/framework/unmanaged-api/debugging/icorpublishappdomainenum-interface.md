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
ms.openlocfilehash: 0f6d4af7c01f91dff77d6ba715ef845f523c7fb6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090048"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="3bf2a-102">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="3bf2a-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="3bf2a-103">Una sottoclasse di [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaccia che fornisce metodi che scorrono una raccolta di [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) oggetti attualmente presenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3bf2a-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="3bf2a-104">Methods</span></span>  
  
|<span data-ttu-id="3bf2a-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="3bf2a-105">Method</span></span>|<span data-ttu-id="3bf2a-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3bf2a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3bf2a-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="3bf2a-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="3bf2a-108">Ottiene il numero specificato di `ICorPublishAppDomain` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bf2a-109">Note</span><span class="sxs-lookup"><span data-stu-id="3bf2a-109">Remarks</span></span>  
 <span data-ttu-id="3bf2a-110">Il `ICorPublishAppDomainEnum` interface implementa i metodi dell'interfaccia astratta [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="3bf2a-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bf2a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3bf2a-111">Requirements</span></span>  
 <span data-ttu-id="3bf2a-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bf2a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bf2a-113">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3bf2a-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3bf2a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3bf2a-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3bf2a-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3bf2a-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3bf2a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3bf2a-116">See also</span></span>

- [<span data-ttu-id="3bf2a-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3bf2a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="3bf2a-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="3bf2a-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
