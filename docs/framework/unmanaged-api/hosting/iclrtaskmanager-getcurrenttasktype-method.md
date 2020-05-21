---
title: Metodo ICLRTaskManager::GetCurrentTaskType
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
ms.openlocfilehash: 2bf1b8b10aded8e61b9bceab0ee02b1d7c0b752a
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762812"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="44c00-102">Metodo ICLRTaskManager::GetCurrentTaskType</span><span class="sxs-lookup"><span data-stu-id="44c00-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>
<span data-ttu-id="44c00-103">Ottiene il tipo dell'attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44c00-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44c00-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44c00-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44c00-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="44c00-105">Parameters</span></span>  
 `pTaskType`  
 <span data-ttu-id="44c00-106">out Puntatore a un valore dell'enumerazione [ETaskType](etasktype-enumeration.md) che indica il tipo di attività attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="44c00-106">[out] A pointer to a value of the [ETaskType](etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44c00-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44c00-107">Requirements</span></span>  
 <span data-ttu-id="44c00-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44c00-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44c00-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="44c00-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44c00-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="44c00-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44c00-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44c00-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44c00-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44c00-112">See also</span></span>

- [<span data-ttu-id="44c00-113">Interfaccia ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="44c00-113">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
