---
title: Metodo ICorPublish::EnumProcesses
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublish.EnumProcesses
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c556cffa95b4d6471b8a07954ec7b93ddbdb21c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="8efdf-102">Metodo ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="8efdf-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="8efdf-103">Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="8efdf-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8efdf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8efdf-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8efdf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8efdf-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="8efdf-106">Il valore di [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumerazione che specifica il tipo di processo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="8efdf-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="8efdf-107">Nella versione corrente, è valido solo COR_PUB_MANAGEDONLY.</span><span class="sxs-lookup"><span data-stu-id="8efdf-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="8efdf-108">Un puntatore all'indirizzo di un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) istanza che è l'enumeratore dei processi.</span><span class="sxs-lookup"><span data-stu-id="8efdf-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8efdf-109">Note</span><span class="sxs-lookup"><span data-stu-id="8efdf-109">Remarks</span></span>  
 <span data-ttu-id="8efdf-110">Raccolta dell'enumeratore dei processi è basato su uno snapshot dei processi in esecuzione quando il `EnumProcesses` metodo viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="8efdf-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="8efdf-111">L'enumeratore non includerà alcun processo che termina prima o dopo `EnumProcesses` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="8efdf-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="8efdf-112">Il `EnumProcesses` metodo può essere chiamato più volte su questo [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) istanza per creare un nuovo insieme di processi aggiornato.</span><span class="sxs-lookup"><span data-stu-id="8efdf-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="8efdf-113">Le raccolte esistenti non saranno interessate dalle chiamate successive del `EnumProcesses` metodo.</span><span class="sxs-lookup"><span data-stu-id="8efdf-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8efdf-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8efdf-114">Requirements</span></span>  
 <span data-ttu-id="8efdf-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8efdf-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8efdf-116">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="8efdf-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8efdf-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8efdf-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8efdf-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8efdf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efdf-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8efdf-119">See Also</span></span>  
 [<span data-ttu-id="8efdf-120">ICorPublish (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8efdf-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
