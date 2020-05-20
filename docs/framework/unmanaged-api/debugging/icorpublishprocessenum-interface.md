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
ms.openlocfilehash: 657d2d638a419ba88d4cf7152f4505de1bd23706
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421072"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="9f75b-102">Interfaccia ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="9f75b-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="9f75b-103">Sottoclasse dell'interfaccia [ICorPublishEnum](icorpublishenum-interface.md) che fornisce i metodi per attraversare una raccolta di oggetti [ICorPublishProcess](icorpublishprocess-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9f75b-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9f75b-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="9f75b-104">Methods</span></span>  
  
|<span data-ttu-id="9f75b-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="9f75b-105">Method</span></span>|<span data-ttu-id="9f75b-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9f75b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9f75b-107">Metodo Next</span><span class="sxs-lookup"><span data-stu-id="9f75b-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="9f75b-108">Ottiene il numero specificato di `ICorPublishProcess` istanze dalla raccolta, a partire dalla posizione corrente.</span><span class="sxs-lookup"><span data-stu-id="9f75b-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f75b-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9f75b-109">Remarks</span></span>  
 <span data-ttu-id="9f75b-110">L' `ICorPublishProcessEnum` interfaccia implementa i metodi dell'interfaccia astratta, [ICorPublishEnum](icorpublishenum-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9f75b-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="9f75b-111">Un' `ICorPublishProcessEnum` istanza viene creata dal metodo [ICorPublish:: EnumProcesses](icorpublish-enumprocesses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9f75b-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="9f75b-112">L'attraversamento della raccolta di `ICorPublishProcess` oggetti è basato sui criteri di filtro specificati al momento della creazione dell' `ICorPublishProcessEnum` istanza.</span><span class="sxs-lookup"><span data-stu-id="9f75b-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f75b-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f75b-113">Requirements</span></span>  
 <span data-ttu-id="9f75b-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f75b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f75b-115">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="9f75b-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9f75b-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f75b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f75b-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f75b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f75b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f75b-118">See also</span></span>

- [<span data-ttu-id="9f75b-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="9f75b-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9f75b-120">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="9f75b-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
