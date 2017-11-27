---
title: Enumerazione WAIT_OPTION
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: WAIT_OPTION
api_location: mscoree.dll
api_type: COM
f1_keywords: WAIT_OPTION
helpviewer_keywords: WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08bdfc928c56d144f50399814a81795fea74574a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="waitoption-enumeration"></a><span data-ttu-id="baa14-102">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="baa14-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="baa14-103">Contiene valori che indicano che l'azione di un host deve avere se l'operazione richiesta da common language runtime (CLR) Blocca.</span><span class="sxs-lookup"><span data-stu-id="baa14-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baa14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="baa14-104">Syntax</span></span>  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="baa14-105">Membri</span><span class="sxs-lookup"><span data-stu-id="baa14-105">Members</span></span>  
  
|<span data-ttu-id="baa14-106">Membro</span><span class="sxs-lookup"><span data-stu-id="baa14-106">Member</span></span>|<span data-ttu-id="baa14-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="baa14-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="baa14-108">Notifica all'host che l'attività deve essere riattivata se Common Language Runtime chiama il [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="baa14-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="baa14-109">Notifica all'host che è necessario il message pump sul thread del sistema operativo corrente se il thread si blocca.</span><span class="sxs-lookup"><span data-stu-id="baa14-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="baa14-110">Il runtime specifica questo valore solo su un <xref:System.Threading.ApartmentState.STA> thread.</span><span class="sxs-lookup"><span data-stu-id="baa14-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="baa14-111">Notifica all'host che la richiesta di sincronizzazione specificata non può essere interrotta da un host.</span><span class="sxs-lookup"><span data-stu-id="baa14-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="baa14-112">Vale a dire l'host non può restituire `HOST_E_DEADLOCK`.</span><span class="sxs-lookup"><span data-stu-id="baa14-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="baa14-113">Note</span><span class="sxs-lookup"><span data-stu-id="baa14-113">Remarks</span></span>  
 <span data-ttu-id="baa14-114">Il [IHostTaskManager:: Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) e [SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) entrambi i metodi accettano un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="baa14-114">The [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baa14-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="baa14-115">Requirements</span></span>  
 <span data-ttu-id="baa14-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baa14-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baa14-117">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="baa14-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="baa14-118">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="baa14-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="baa14-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baa14-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa14-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="baa14-120">See Also</span></span>  
 [<span data-ttu-id="baa14-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="baa14-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
