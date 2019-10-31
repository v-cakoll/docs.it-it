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
ms.openlocfilehash: cbe2aa48a8b67b0b6e88f7b5267bc70848fe3cec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140318"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="0c4b8-102">Interfaccia ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="0c4b8-102">ICorPublishAppDomainEnum Interface</span></span>
<span data-ttu-id="0c4b8-103">Sottoclasse dell'interfaccia [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) che fornisce i metodi per attraversare una raccolta di oggetti [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) attualmente presenti all'interno di un processo.</span><span class="sxs-lookup"><span data-stu-id="0c4b8-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0c4b8-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="0c4b8-104">Methods</span></span>  
  
|<span data-ttu-id="0c4b8-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="0c4b8-105">Method</span></span>|<span data-ttu-id="0c4b8-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0c4b8-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0c4b8-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="0c4b8-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-next-method.md)|<span data-ttu-id="0c4b8-108">Ottiene il numero specificato di istanze di `ICorPublishAppDomain` dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="0c4b8-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c4b8-109">Note</span><span class="sxs-lookup"><span data-stu-id="0c4b8-109">Remarks</span></span>  
 <span data-ttu-id="0c4b8-110">L'interfaccia `ICorPublishAppDomainEnum` implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="0c4b8-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c4b8-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0c4b8-111">Requirements</span></span>  
 <span data-ttu-id="0c4b8-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c4b8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c4b8-113">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="0c4b8-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="0c4b8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c4b8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c4b8-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c4b8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4b8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c4b8-116">See also</span></span>

- [<span data-ttu-id="0c4b8-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0c4b8-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0c4b8-118">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="0c4b8-118">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
