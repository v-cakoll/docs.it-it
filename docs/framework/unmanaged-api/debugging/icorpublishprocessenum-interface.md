---
title: Interfaccia ICorPublishProcessEnum
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 3a7267548a957d403cfe02aa3d800a410c14b82a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103423"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="ac9d7-102">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="ac9d7-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="ac9d7-103">Sottoclasse dell'interfaccia [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) che fornisce i metodi per attraversare una raccolta di oggetti [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="ac9d7-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ac9d7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="ac9d7-104">Methods</span></span>  
  
|<span data-ttu-id="ac9d7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="ac9d7-105">Method</span></span>|<span data-ttu-id="ac9d7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac9d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ac9d7-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="ac9d7-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="ac9d7-108">Ottiene il numero specificato di istanze di `ICorPublishProcess` dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="ac9d7-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac9d7-109">Note</span><span class="sxs-lookup"><span data-stu-id="ac9d7-109">Remarks</span></span>  
 <span data-ttu-id="ac9d7-110">L'interfaccia `ICorPublishProcessEnum` implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ac9d7-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="ac9d7-111">Un'istanza di `ICorPublishProcessEnum` viene creata dal metodo [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="ac9d7-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="ac9d7-112">L'attraversamento della raccolta di oggetti `ICorPublishProcess` si basa sui criteri di filtro specificati al momento della creazione dell'istanza di `ICorPublishProcessEnum`.</span><span class="sxs-lookup"><span data-stu-id="ac9d7-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9d7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac9d7-113">Requirements</span></span>  
 <span data-ttu-id="ac9d7-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac9d7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9d7-115">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ac9d7-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ac9d7-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac9d7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac9d7-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9d7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac9d7-118">See also</span></span>

- [<span data-ttu-id="ac9d7-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ac9d7-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ac9d7-120">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="ac9d7-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
