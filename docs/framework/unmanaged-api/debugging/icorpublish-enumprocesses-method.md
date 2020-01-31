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
ms.openlocfilehash: 5f785b22a3fbda6403c124ec70757b16f5335907
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790764"
---
# <a name="icorpublishenumprocesses-method"></a><span data-ttu-id="6ea07-102">Metodo ICorPublish::EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="6ea07-102">ICorPublish::EnumProcesses Method</span></span>
<span data-ttu-id="6ea07-103">Ottiene un enumeratore per i processi gestiti in esecuzione nel computer.</span><span class="sxs-lookup"><span data-stu-id="6ea07-103">Gets an enumerator for the managed processes running on this computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ea07-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProcesses (  
    [in] COR_PUB_ENUMPROCESS       Type,  
    [out] ICorPublishProcessEnum   **ppIEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ea07-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ea07-105">Parameters</span></span>  
 `Type`  
 <span data-ttu-id="6ea07-106">Valore dell'enumerazione [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) che specifica il tipo di processo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="6ea07-106">A value of the [COR_PUB_ENUMPROCESS](cor-pub-enumprocess-enumeration.md) enumeration that specifies the type of process to be retrieved.</span></span> <span data-ttu-id="6ea07-107">Nella versione corrente solo COR_PUB_MANAGEDONLY è valido.</span><span class="sxs-lookup"><span data-stu-id="6ea07-107">In the current version, only COR_PUB_MANAGEDONLY is valid.</span></span>  
  
 `ppIEnum`  
 <span data-ttu-id="6ea07-108">Puntatore all'indirizzo di un'istanza di [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) che rappresenta l'enumeratore dei processi.</span><span class="sxs-lookup"><span data-stu-id="6ea07-108">A pointer to the address of an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that is the enumerator of the processes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ea07-109">Note</span><span class="sxs-lookup"><span data-stu-id="6ea07-109">Remarks</span></span>  
 <span data-ttu-id="6ea07-110">La raccolta di processi dell'enumeratore si basa su uno snapshot dei processi in esecuzione quando viene chiamato il metodo `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="6ea07-110">The enumerator's collection of processes is based on a snapshot of the processes that are running when the `EnumProcesses` method is called.</span></span> <span data-ttu-id="6ea07-111">L'enumeratore non includerà i processi che terminano prima o si avviano dopo la chiamata di `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="6ea07-111">The enumerator will not include any processes that terminate before or start after `EnumProcesses` is called.</span></span>  
  
 <span data-ttu-id="6ea07-112">Il metodo `EnumProcesses` può essere chiamato più di una volta in questa istanza di [ICorPublish](icorpublish-interface.md) per creare una nuova raccolta aggiornata di processi.</span><span class="sxs-lookup"><span data-stu-id="6ea07-112">The `EnumProcesses` method may be called more than once on this [ICorPublish](icorpublish-interface.md) instance to create a new up-to-date collection of processes.</span></span> <span data-ttu-id="6ea07-113">Le raccolte esistenti non saranno interessate dalle chiamate successive del metodo `EnumProcesses`.</span><span class="sxs-lookup"><span data-stu-id="6ea07-113">Existing collections will not be affected by subsequent calls of the `EnumProcesses` method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ea07-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="6ea07-114">Requirements</span></span>  
 <span data-ttu-id="6ea07-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ea07-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ea07-116">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="6ea07-116">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6ea07-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ea07-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ea07-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ea07-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ea07-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ea07-119">See also</span></span>

- [<span data-ttu-id="6ea07-120">Interfaccia ICorPublish</span><span class="sxs-lookup"><span data-stu-id="6ea07-120">ICorPublish Interface</span></span>](icorpublish-interface.md)
