---
title: Metodo IHostTaskManager::GetStackGuarantee
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetStackGuarantee
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetStackGuarantee
helpviewer_keywords:
- GetStackGuarantee method [.NET Framework hosting]
- IHostTaskManager::GetStackGuarantee method [.NET Framework hosting]
ms.assetid: 8176d732-c25c-4520-811d-e3310f339947
topic_type:
- apiref
ms.openlocfilehash: d76242eb8539f2e8dffbf39b7eaf595664bdce8e
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842023"
---
# <a name="ihosttaskmanagergetstackguarantee-method"></a><span data-ttu-id="4d897-102">Metodo IHostTaskManager::GetStackGuarantee</span><span class="sxs-lookup"><span data-stu-id="4d897-102">IHostTaskManager::GetStackGuarantee Method</span></span>
<span data-ttu-id="4d897-103">Ottiene la quantità di spazio dello stack che è garantita come disponibile al termine di un'operazione dello stack, ma prima della chiusura di un processo.</span><span class="sxs-lookup"><span data-stu-id="4d897-103">Gets the amount of stack space that is guaranteed to be available after a stack operation completes, but before the closing of a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d897-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d897-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackGuarantee(  
    [out] ULONG *pGuarantee  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d897-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d897-105">Parameters</span></span>  
 `pGuarantee`  
 <span data-ttu-id="4d897-106">out Puntatore al numero di byte disponibili.</span><span class="sxs-lookup"><span data-stu-id="4d897-106">[out] A pointer to the number of bytes that are available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d897-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d897-107">Requirements</span></span>  
 <span data-ttu-id="4d897-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d897-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d897-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4d897-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d897-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4d897-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d897-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d897-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d897-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4d897-112">See also</span></span>

- [<span data-ttu-id="4d897-113">Interfaccia IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="4d897-113">IHostTaskManager Interface</span></span>](ihosttaskmanager-interface.md)
