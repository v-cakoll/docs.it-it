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
ms.openlocfilehash: 7d083655326333f18ee98f8e84fff2ed182dde6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103458"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="1b6d5-102">Interfaccia ICorPublishEnum</span><span class="sxs-lookup"><span data-stu-id="1b6d5-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="1b6d5-103">Funge da interfaccia di base astratta per gli enumeratori utilizzati nella pubblicazione di informazioni sui processi e sui domini dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b6d5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="1b6d5-104">Methods</span></span>  
  
|<span data-ttu-id="1b6d5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="1b6d5-105">Method</span></span>|<span data-ttu-id="1b6d5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1b6d5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1b6d5-107">Metodo Clone</span><span class="sxs-lookup"><span data-stu-id="1b6d5-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="1b6d5-108">Crea una copia di questo oggetto `ICorPublishEnum`.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="1b6d5-109">Metodo GetCount</span><span class="sxs-lookup"><span data-stu-id="1b6d5-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="1b6d5-110">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="1b6d5-111">Metodo Reset</span><span class="sxs-lookup"><span data-stu-id="1b6d5-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="1b6d5-112">Sposta il cursore di all'inizio dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="1b6d5-113">Metodo Skip</span><span class="sxs-lookup"><span data-stu-id="1b6d5-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="1b6d5-114">Sposta il cursore verso l'interno dell'enumerazione in base al numero di elementi specificato.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b6d5-115">Note</span><span class="sxs-lookup"><span data-stu-id="1b6d5-115">Remarks</span></span>  
 <span data-ttu-id="1b6d5-116">Gli enumeratori seguenti derivano da `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="1b6d5-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="1b6d5-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="1b6d5-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="1b6d5-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="1b6d5-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="1b6d5-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b6d5-119">Requirements</span></span>  
 <span data-ttu-id="1b6d5-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b6d5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b6d5-121">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="1b6d5-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="1b6d5-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b6d5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b6d5-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b6d5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6d5-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b6d5-124">See also</span></span>

- [<span data-ttu-id="1b6d5-125">Coclasse CorpubPublish</span><span class="sxs-lookup"><span data-stu-id="1b6d5-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="1b6d5-126">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1b6d5-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
