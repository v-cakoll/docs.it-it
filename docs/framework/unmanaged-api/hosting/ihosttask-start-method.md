---
title: Metodo IHostTask::Start
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: a4e8211f091b2a3a4f24d8350f6d7dbe7d7920af
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842387"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="98b86-102">Metodo IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="98b86-102">IHostTask::Start Method</span></span>
<span data-ttu-id="98b86-103">Richiede che l'host sposti l'attività rappresentata dall'istanza corrente di [IHostTask](ihosttask-interface.md) da un oggetto sospeso a uno stato attivo, in cui è possibile eseguire il codice.</span><span class="sxs-lookup"><span data-stu-id="98b86-103">Requests that the host move the task represented by the current [IHostTask](ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98b86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="98b86-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="98b86-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="98b86-105">Return Value</span></span>  
  
|<span data-ttu-id="98b86-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="98b86-106">HRESULT</span></span>|<span data-ttu-id="98b86-107">Description</span><span class="sxs-lookup"><span data-stu-id="98b86-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="98b86-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="98b86-108">S_OK</span></span>|<span data-ttu-id="98b86-109">Avvio restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="98b86-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="98b86-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="98b86-110">E_FAIL</span></span>|<span data-ttu-id="98b86-111">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="98b86-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="98b86-112">Quando un metodo restituisce E_FAIL, il Common Language Runtime (CLR) non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="98b86-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="98b86-113">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="98b86-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98b86-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="98b86-114">Remarks</span></span>  
 <span data-ttu-id="98b86-115">`Start`restituisce sempre un valore HRESULT di S_OK, tranne nei casi in cui si è verificato un errore irreversibile.</span><span class="sxs-lookup"><span data-stu-id="98b86-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98b86-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="98b86-116">Requirements</span></span>  
 <span data-ttu-id="98b86-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98b86-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98b86-118">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="98b86-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="98b86-119">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="98b86-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="98b86-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98b86-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98b86-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98b86-121">See also</span></span>

- [<span data-ttu-id="98b86-122">Interfaccia ICLRTask</span><span class="sxs-lookup"><span data-stu-id="98b86-122">ICLRTask Interface</span></span>](iclrtask-interface.md)
- [<span data-ttu-id="98b86-123">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="98b86-123">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
- [<span data-ttu-id="98b86-124">Interfaccia IHostTask</span><span class="sxs-lookup"><span data-stu-id="98b86-124">IHostTask Interface</span></span>](ihosttask-interface.md)
- [<span data-ttu-id="98b86-125">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="98b86-125">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
