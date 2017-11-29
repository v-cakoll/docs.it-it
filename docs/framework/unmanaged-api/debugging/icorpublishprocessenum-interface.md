---
title: Interfaccia ICorPublishProcessEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcessEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcessEnum
helpviewer_keywords: ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 66e31911289d1ef8b590a0b7e7896adfa4998adc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="86814-102">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="86814-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="86814-103">Una sottoclasse di [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interfaccia che fornisce metodi che scorrono una raccolta di [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="86814-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="86814-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="86814-104">Methods</span></span>  
  
|<span data-ttu-id="86814-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="86814-105">Method</span></span>|<span data-ttu-id="86814-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="86814-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="86814-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="86814-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="86814-108">Ottiene il numero specificato di `ICorPublishProcess` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="86814-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86814-109">Note</span><span class="sxs-lookup"><span data-stu-id="86814-109">Remarks</span></span>  
 <span data-ttu-id="86814-110">Il `ICorPublishProcessEnum` interfaccia implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="86814-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="86814-111">Un `ICorPublishProcessEnum` viene creata l'istanza di [ICorPublish:: EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="86814-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="86814-112">Di attraversamento della raccolta di `ICorPublishProcess` oggetti si basa sui criteri di filtro specificati al momento il `ICorPublishProcessEnum` è stata creata l'istanza.</span><span class="sxs-lookup"><span data-stu-id="86814-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86814-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86814-113">Requirements</span></span>  
 <span data-ttu-id="86814-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86814-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86814-115">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="86814-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="86814-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86814-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86814-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86814-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86814-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86814-118">See Also</span></span>  
 [<span data-ttu-id="86814-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="86814-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="86814-120">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="86814-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
