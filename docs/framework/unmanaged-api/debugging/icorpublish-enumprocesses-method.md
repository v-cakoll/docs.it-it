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
ms.openlocfilehash: 5f0dd814ad5adfa1b0dd7199530a3f993634a548
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121788"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="101fb-102">Metodo ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="101fb-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="101fb-103">Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="101fb-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="101fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="101fb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="101fb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="101fb-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="101fb-106">Valore dell'enumerazione [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) che specifica il tipo di processo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="101fb-106">A value of the [COR_PUB_ENUMPROCESS](../../../../docs/framework/unmanaged-api/debugging/cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="101fb-107">Nella versione corrente, solo COR_PUB_MANAGEDONLY è valido.</span><span class="sxs-lookup"><span data-stu-id="101fb-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="101fb-108">Puntatore all'indirizzo di un'istanza di [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) che rappresenta l'enumeratore dei processi.</span><span class="sxs-lookup"><span data-stu-id="101fb-108">A pointer to the address of an [ICorPublishProcessEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="101fb-109">Note</span><span class="sxs-lookup"><span data-stu-id="101fb-109">Remarks</span></span>  
 <span data-ttu-id="101fb-110">La raccolta di processi dell'enumeratore si basa su uno snapshot dei processi in esecuzione quando viene chiamato il metodo `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="101fb-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="101fb-111">L'enumeratore non includerà i processi che terminano prima o si avviano dopo la chiamata di `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="101fb-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="101fb-112">Il metodo `EnumProcesses` può essere chiamato più di una volta in questa istanza di [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) per creare una nuova raccolta aggiornata di processi.</span><span class="sxs-lookup"><span data-stu-id="101fb-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="101fb-113">Le raccolte esistenti non saranno interessate dalle chiamate successive del metodo `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="101fb-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="101fb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="101fb-114">Requirements</span></span>  
 <span data-ttu-id="101fb-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="101fb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="101fb-116">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="101fb-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="101fb-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="101fb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="101fb-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="101fb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="101fb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="101fb-119">See also</span></span>

- [<span data-ttu-id="101fb-120">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="101fb-120">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)
