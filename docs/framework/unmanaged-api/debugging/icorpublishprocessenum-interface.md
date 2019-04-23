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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5186df61eb82b29fcfa9776408498b748068e122
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173654"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="22ced-102">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="22ced-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="22ced-103">Una sottoclasse di [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaccia che fornisce metodi che scorrono una raccolta di [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="22ced-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="22ced-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="22ced-104">Methods</span></span>  
  
|<span data-ttu-id="22ced-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="22ced-105">Method</span></span>|<span data-ttu-id="22ced-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22ced-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="22ced-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="22ced-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="22ced-108">Ottiene il numero specificato di `ICorPublishProcess` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="22ced-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22ced-109">Note</span><span class="sxs-lookup"><span data-stu-id="22ced-109">Remarks</span></span>  
 <span data-ttu-id="22ced-110">Il `ICorPublishProcessEnum` interface implementa i metodi dell'interfaccia astratta [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="22ced-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="22ced-111">Un' `ICorPublishProcessEnum` viene creata dall'istanza di [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="22ced-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="22ced-112">L'attraversamento della raccolta di `ICorPublishProcess` oggetti si basa sui criteri di filtro forniti al momento il `ICorPublishProcessEnum` istanza è stata creata.</span><span class="sxs-lookup"><span data-stu-id="22ced-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22ced-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22ced-113">Requirements</span></span>  
 <span data-ttu-id="22ced-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22ced-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22ced-115">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="22ced-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="22ced-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22ced-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22ced-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22ced-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22ced-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22ced-118">See also</span></span>

- [<span data-ttu-id="22ced-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="22ced-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="22ced-120">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="22ced-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
