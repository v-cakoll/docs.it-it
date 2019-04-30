---
title: Interfaccia ICorPublishEnum
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1eac0b9fe252e476f8ff781f2181a203886d3beb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993538"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="51210-102">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="51210-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="51210-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati in sulla pubblicazione delle informazioni sui processi e domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="51210-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51210-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="51210-104">Methods</span></span>  
  
|<span data-ttu-id="51210-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="51210-105">Method</span></span>|<span data-ttu-id="51210-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51210-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51210-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="51210-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="51210-108">Crea una copia di questo `ICorPublishEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="51210-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="51210-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="51210-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="51210-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51210-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="51210-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="51210-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="51210-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51210-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="51210-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="51210-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="51210-114">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="51210-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51210-115">Note</span><span class="sxs-lookup"><span data-stu-id="51210-115">Remarks</span></span>  
 <span data-ttu-id="51210-116">Gli enumeratori seguenti derivano da `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="51210-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="51210-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="51210-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="51210-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="51210-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="51210-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51210-119">Requirements</span></span>  
 <span data-ttu-id="51210-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51210-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51210-121">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="51210-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="51210-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51210-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51210-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51210-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51210-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51210-124">See also</span></span>

- [<span data-ttu-id="51210-125">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="51210-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="51210-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="51210-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
