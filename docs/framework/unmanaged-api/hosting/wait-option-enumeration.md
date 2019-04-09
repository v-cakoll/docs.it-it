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
ms.openlocfilehash: 0ac28f28d4d284ba26fadd46e53ebeb8e5b5f3cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139581"
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="45a6d-102">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="45a6d-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="45a6d-103">Contiene valori che indicano che l'azione di un host debba eseguire se l'operazione richiesta da common language runtime (CLR) Blocca.</span><span class="sxs-lookup"><span data-stu-id="45a6d-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45a6d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="45a6d-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="45a6d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="45a6d-105">Members</span></span>  
  
|<span data-ttu-id="45a6d-106">Member</span><span class="sxs-lookup"><span data-stu-id="45a6d-106">Member</span></span>|<span data-ttu-id="45a6d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="45a6d-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="45a6d-108">Notifica all'host che l'attività deve essere riattivata se Common Language Runtime chiama il [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="45a6d-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="45a6d-109">Notifica all'host che è necessario che distribuisca i messaggi sul thread del sistema operativo corrente se il thread si blocca.</span><span class="sxs-lookup"><span data-stu-id="45a6d-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="45a6d-110">Il runtime specifica questo valore solo su un <xref:System.Threading.ApartmentState.STA> thread.</span><span class="sxs-lookup"><span data-stu-id="45a6d-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="45a6d-111">Notifica all'host che la richiesta di sincronizzazione specificato non può essere interrotta da un host.</span><span class="sxs-lookup"><span data-stu-id="45a6d-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="45a6d-112">Vale a dire, l'host non può restituire `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="45a6d-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45a6d-113">Note</span><span class="sxs-lookup"><span data-stu-id="45a6d-113">Remarks</span></span>  
 <span data-ttu-id="45a6d-114">Il [IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) e [SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) entrambi i metodi accettano un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="45a6d-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45a6d-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="45a6d-115">Requirements</span></span>  
 <span data-ttu-id="45a6d-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45a6d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45a6d-117">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="45a6d-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45a6d-118">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="45a6d-118">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="45a6d-119">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="45a6d-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="45a6d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45a6d-120">See also</span></span>

- [<span data-ttu-id="45a6d-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="45a6d-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
