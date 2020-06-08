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
ms.openlocfilehash: 2f83bc5b114b746958f936c311efa823d88441d1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503887"
---
# <a name="wait_option-enumeration"></a><span data-ttu-id="0489b-102">Enumerazione WAIT_OPTION</span><span class="sxs-lookup"><span data-stu-id="0489b-102">WAIT_OPTION Enumeration</span></span>
<span data-ttu-id="0489b-103">Contiene valori che indicano l'azione che un host deve eseguire se un'operazione richiesta dal Common Language Runtime (CLR) si blocca.</span><span class="sxs-lookup"><span data-stu-id="0489b-103">Contains values that indicate the action a host should take if an operation requested by the common language runtime (CLR) blocks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0489b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0489b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a><span data-ttu-id="0489b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0489b-105">Members</span></span>  
  
|<span data-ttu-id="0489b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0489b-106">Member</span></span>|<span data-ttu-id="0489b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0489b-107">Description</span></span>|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|<span data-ttu-id="0489b-108">Notifica all'host che l'attività deve essere riattivata se CLR chiama il metodo [IHostTask:: Alert](ihosttask-alert-method.md) .</span><span class="sxs-lookup"><span data-stu-id="0489b-108">Notifies the host that the task should be awakened if the CLR calls the [IHostTask::Alert](ihosttask-alert-method.md) method.</span></span>|  
|`WAIT_MSGPUMP`|<span data-ttu-id="0489b-109">Notifica all'host che è necessario pompare i messaggi nel thread del sistema operativo corrente se il thread viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="0489b-109">Notifies the host that it must pump messages on the current OS thread if the thread becomes blocked.</span></span> <span data-ttu-id="0489b-110">Il runtime specifica questo valore solo in un <xref:System.Threading.ApartmentState.STA> thread.</span><span class="sxs-lookup"><span data-stu-id="0489b-110">The runtime specifies this value only on an <xref:System.Threading.ApartmentState.STA> thread.</span></span>|  
|`WAIT_NOTINDEADLOCK`|<span data-ttu-id="0489b-111">Notifica all'host che la richiesta di sincronizzazione specificata non può essere interruppe da un host.</span><span class="sxs-lookup"><span data-stu-id="0489b-111">Notifies the host that the specified synchronization request cannot be broken by a host.</span></span> <span data-ttu-id="0489b-112">Ovvero, l'host non può restituire `HOST_E_DEADLOCK` .</span><span class="sxs-lookup"><span data-stu-id="0489b-112">That is, the host cannot return `HOST_E_DEADLOCK`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0489b-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0489b-113">Remarks</span></span>  
 <span data-ttu-id="0489b-114">I metodi [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) e [IHostTaskManager:: SwitchToTask accettano](ihosttaskmanager-switchtotask-method.md) accettano entrambi un parametro di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="0489b-114">The [IHostTaskManager::Sleep](ihosttaskmanager-sleep-method.md) and [IHostTaskManager::SwitchToTask](ihosttaskmanager-switchtotask-method.md) methods both take a parameter of this type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0489b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0489b-115">Requirements</span></span>  
 <span data-ttu-id="0489b-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0489b-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0489b-117">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0489b-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0489b-118">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0489b-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0489b-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0489b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0489b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0489b-120">See also</span></span>

- [<span data-ttu-id="0489b-121">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="0489b-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
