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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160135"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="224cb-102">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="224cb-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="224cb-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati in sulla pubblicazione delle informazioni sui processi e domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="224cb-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="224cb-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="224cb-104">Methods</span></span>  
  
|<span data-ttu-id="224cb-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="224cb-105">Method</span></span>|<span data-ttu-id="224cb-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="224cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="224cb-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="224cb-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="224cb-108">Crea una copia di questo `ICorPublishEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="224cb-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="224cb-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="224cb-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="224cb-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="224cb-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="224cb-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="224cb-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="224cb-112">Sposta il cursore all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="224cb-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="224cb-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="224cb-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="224cb-114">Sposta in avanti il cursore nell'enumerazione per il numero specificato di elementi.</span><span class="sxs-lookup"><span data-stu-id="224cb-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="224cb-115">Note</span><span class="sxs-lookup"><span data-stu-id="224cb-115">Remarks</span></span>  
 <span data-ttu-id="224cb-116">Gli enumeratori seguenti derivano da `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="224cb-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
-   [<span data-ttu-id="224cb-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="224cb-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
-   [<span data-ttu-id="224cb-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="224cb-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="224cb-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="224cb-119">Requirements</span></span>  
 <span data-ttu-id="224cb-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="224cb-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="224cb-121">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="224cb-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="224cb-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="224cb-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="224cb-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="224cb-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="224cb-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="224cb-124">See also</span></span>

- [<span data-ttu-id="224cb-125">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="224cb-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="224cb-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="224cb-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
