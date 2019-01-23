---
title: Metodo ICorPublish::EnumProcesses
ms.date: 03/30/2017
api_name:
- ICorPublish.EnumProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish::EnumProcesses
helpviewer_keywords:
- ICorPublish::EnumProcesses method [.NET Framework debugging]
- EnumProcesses method [.NET Framework debugging]
ms.assetid: 4ae765f0-93b2-4b6f-aea1-7b0cf44e04a7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3af824a23d683f4d450ef6f60fd407928c41d51e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536958"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="34519-102">Metodo ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="34519-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="34519-103">Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="34519-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34519-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34519-104">Syntax</span></span>  
  
```  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34519-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34519-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="34519-106">Valore di [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumerazione che specifica il tipo di processo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="34519-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="34519-107">Nella versione corrente, solo COR_PUB_MANAGEDONLY è valido.</span><span class="sxs-lookup"><span data-stu-id="34519-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="34519-108">Un puntatore all'indirizzo di un [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) istanza che rappresenta l'enumeratore dei processi.</span><span class="sxs-lookup"><span data-stu-id="34519-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34519-109">Note</span><span class="sxs-lookup"><span data-stu-id="34519-109">Remarks</span></span>  
 <span data-ttu-id="34519-110">Raccolta dell'enumeratore dei processi si basa su uno snapshot dei processi in esecuzione quando il `EnumProcesses` viene chiamato il metodo.</span><span class="sxs-lookup"><span data-stu-id="34519-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="34519-111">L'enumeratore non verrà inclusi tutti i processi che termina prima o dopo l'avvio `EnumProcesses` viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="34519-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="34519-112">Il `EnumProcesses` metodo può essere chiamato più volte su questo [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) istanza per creare un nuovo insieme aggiornato di processi.</span><span class="sxs-lookup"><span data-stu-id="34519-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="34519-113">Le raccolte esistenti non influiranno dalle chiamate successive del `EnumProcesses` (metodo).</span><span class="sxs-lookup"><span data-stu-id="34519-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34519-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34519-114">Requirements</span></span>  
 <span data-ttu-id="34519-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34519-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34519-116">**Intestazione:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="34519-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="34519-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34519-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34519-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34519-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34519-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34519-119">See also</span></span>
- [<span data-ttu-id="34519-120">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="34519-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
