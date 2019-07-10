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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda866c1a1f1f69f0d042ccfde3dfad293df9b37
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776512"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="01024-102">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="01024-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="01024-103">Contiene valori che indicano che l'azione di un host debba eseguire se l'operazione richiesta da common language runtime (CLR) Blocca.</span><span class="sxs-lookup"><span data-stu-id="01024-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01024-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01024-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="01024-105">Membri</span><span class="sxs-lookup"><span data-stu-id="01024-105">Members</span></span>  
  
|<span data-ttu-id="01024-106">Member</span><span class="sxs-lookup"><span data-stu-id="01024-106">Member</span></span>|<span data-ttu-id="01024-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="01024-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="01024-108">Notifica all'host che l'attività deve essere riattivata se Common Language Runtime chiama il [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="01024-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="01024-109">Notifica all'host che è necessario che distribuisca i messaggi sul thread del sistema operativo corrente se il thread si blocca.</span><span class="sxs-lookup"><span data-stu-id="01024-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="01024-110">Il runtime specifica questo valore solo su un <xref:System.Threading.ApartmentState.STA> thread.</span><span class="sxs-lookup"><span data-stu-id="01024-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="01024-111">Notifica all'host che la richiesta di sincronizzazione specificato non può essere interrotta da un host.</span><span class="sxs-lookup"><span data-stu-id="01024-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="01024-112">Vale a dire, l'host non può restituire `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="01024-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01024-113">Note</span><span class="sxs-lookup"><span data-stu-id="01024-113">Remarks</span></span>  
 <span data-ttu-id="01024-114">Il [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) e [SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) entrambi i metodi accettano un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="01024-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01024-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01024-115">Requirements</span></span>  
 <span data-ttu-id="01024-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01024-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01024-117">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="01024-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="01024-118">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="01024-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01024-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01024-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01024-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01024-120">See also</span></span>

- [<span data-ttu-id="01024-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="01024-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
