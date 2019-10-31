---
title: Struttura StackOverflowInfo
ms.date: 03/30/2017
api_name:
- StackOverflowInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StackOverflowInfo
helpviewer_keywords:
- StackOverflowInfo structure [.NET Framework hosting]
ms.assetid: 519389f2-0217-436c-99d4-93a76ebce5b5
topic_type:
- apiref
ms.openlocfilehash: 1072026f92edbc646653c6dd74ec8e22d5b887e5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73105916"
---
# <a name="stackoverflowinfo-structure"></a><span data-ttu-id="cd06f-102">Struttura StackOverflowInfo</span><span class="sxs-lookup"><span data-stu-id="cd06f-102">StackOverflowInfo Structure</span></span>
<span data-ttu-id="cd06f-103">Archivia il tipo di overflow che si è verificato e le informazioni sull'eccezione generata a causa dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="cd06f-103">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd06f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd06f-104">Syntax</span></span>  
  
```cpp  
typedef struct _StackOverflowInfo {  
    StackOverflowType   soType;  
    EXCEPTION_POINTERS  *pExceptionInfo;  
} StackOverflowInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="cd06f-105">Members</span><span class="sxs-lookup"><span data-stu-id="cd06f-105">Members</span></span>  
  
|<span data-ttu-id="cd06f-106">Member</span><span class="sxs-lookup"><span data-stu-id="cd06f-106">Member</span></span>|<span data-ttu-id="cd06f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd06f-107">Description</span></span>|  
|------------|-----------------|  
|`soType`|<span data-ttu-id="cd06f-108">Valore dell'enumerazione [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) che specifica il tipo di overflow.</span><span class="sxs-lookup"><span data-stu-id="cd06f-108">A value of the [StackOverflowType](../../../../docs/framework/unmanaged-api/hosting/stackoverflowtype-enumeration.md) enumeration that specifies the type of overflow.</span></span>|  
|`pExceptionInfo`|<span data-ttu-id="cd06f-109">Puntatore a un oggetto `EXCEPTION_POINTERS` Win32, che contiene un record di eccezione con una descrizione indipendente dal computer di un'eccezione e un record di contesto con una descrizione dipendente dal computer del contesto del processore al momento dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd06f-109">A pointer to a Win32 `EXCEPTION_POINTERS` object, which contains an exception record with a machine-independent description of an exception and a context record with a machine-dependent description of the processor context at the time of the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd06f-110">Note</span><span class="sxs-lookup"><span data-stu-id="cd06f-110">Remarks</span></span>  
 <span data-ttu-id="cd06f-111">Un oggetto `StackOverflowInfo` viene passato al metodo [IActionOnCLREvent:: OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) per `Event_StackOverflow` eventi.</span><span class="sxs-lookup"><span data-stu-id="cd06f-111">A `StackOverflowInfo` object is passed to the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method for `Event_StackOverflow` events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd06f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd06f-112">Requirements</span></span>  
 <span data-ttu-id="cd06f-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd06f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd06f-114">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="cd06f-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="cd06f-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cd06f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd06f-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd06f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd06f-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd06f-117">See also</span></span>

- [<span data-ttu-id="cd06f-118">Strutture di hosting</span><span class="sxs-lookup"><span data-stu-id="cd06f-118">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
