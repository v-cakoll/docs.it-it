---
title: Enumerazione WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 9ecfb551b55551e5f6cc7e7e9ffb55e5a96259ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141511"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="44929-102">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="44929-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="44929-103">Contiene valori che indicano l'azione che un host deve eseguire se un'operazione richiesta dal Common Language Runtime (CLR) si blocca.</span><span class="sxs-lookup"><span data-stu-id="44929-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44929-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="44929-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="44929-105">Members</span><span class="sxs-lookup"><span data-stu-id="44929-105">Members</span></span>  
  
|<span data-ttu-id="44929-106">Member</span><span class="sxs-lookup"><span data-stu-id="44929-106">Member</span></span>|<span data-ttu-id="44929-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="44929-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="44929-108">Notifica all'host che l'attività deve essere riattivata se CLR chiama il metodo [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="44929-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="44929-109">Notifica all'host che è necessario pompare i messaggi nel thread del sistema operativo corrente se il thread viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="44929-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="44929-110">Il runtime specifica questo valore solo in un thread <xref:System.Threading.ApartmentState.STA>.</span><span class="sxs-lookup"><span data-stu-id="44929-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="44929-111">Notifica all'host che la richiesta di sincronizzazione specificata non può essere interruppe da un host.</span><span class="sxs-lookup"><span data-stu-id="44929-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="44929-112">Ovvero, l'host non può restituire `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="44929-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44929-113">Note</span><span class="sxs-lookup"><span data-stu-id="44929-113">Remarks</span></span>  
 <span data-ttu-id="44929-114">I metodi [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) e [IHostTaskManager:: SwitchToTask accettano](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) accettano entrambi un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="44929-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44929-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="44929-115">Requirements</span></span>  
 <span data-ttu-id="44929-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44929-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44929-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="44929-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44929-118">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="44929-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44929-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44929-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44929-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44929-120">See also</span></span>

- [<span data-ttu-id="44929-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="44929-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
