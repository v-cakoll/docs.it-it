---
title: Enumerazione NOTIFY_FILTER
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- NOTIFY_FILTER
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- NOTIFY_FILTER
helpviewer_keywords:
- NOTIFY_FILTER enumeration [.NET Framework debugging]
ms.assetid: 4789d08f-8683-45d3-ac30-73d48c61e470
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ef72cb965bec8f424f5df35d4f66715fa11a5e46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="notifyfilter-enumeration"></a><span data-ttu-id="9e7d5-102">Enumerazione NOTIFY_FILTER</span><span class="sxs-lookup"><span data-stu-id="9e7d5-102">NOTIFY_FILTER Enumeration</span></span>
<span data-ttu-id="9e7d5-103">Identifica i callback per funzioni del debugger.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-103">Identifies callbacks for debugger functions.</span></span> <span data-ttu-id="9e7d5-104">Per ulteriori informazioni, vedere il [INotifySource2:: SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-104">For more information, see the [INotifySource2::SetNotifyFilter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e7d5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e7d5-105">Syntax</span></span>  
  
```  
enum tagNOTIFY_FILTER  
{  
    NOTIFY_FILTER_ONSYNCCALLOUT    = 0x1,  
    NOTIFY_FILTER_ONSYNCCALLENTER  = 0x2,  
    NOTIFY_FILTER_ONSYNCCALLEXIT   = 0x4,  
    NOTIFY_FILTER_ONSYNCCALLRETURN = 0x8,  
    NOTIFY_FILTER_ALLSYNC = NOTIFY_FILTER_ONSYNCCALLOUT | NOTIFY_FILTER_ONSYNCCALLENTER | NOTIFY_FILTER_ONSYNCCALLEXIT | NOTIFY_FILTER_ONSYNCCALLRETURN,  
    NOTIFY_FILTER_ALL              = 0xffffffff,  
    NOTIFY_FILTER_NONE             = 0  
};  
```  
  
## <a name="members"></a><span data-ttu-id="9e7d5-106">Membri</span><span class="sxs-lookup"><span data-stu-id="9e7d5-106">Members</span></span>  
  
|<span data-ttu-id="9e7d5-107">Membro</span><span class="sxs-lookup"><span data-stu-id="9e7d5-107">Member</span></span>|<span data-ttu-id="9e7d5-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e7d5-108">Description</span></span>|  
|------------|-----------------|  
|`NOTIFY_FILTER_ONSYNCCALLOUT`|<span data-ttu-id="9e7d5-109">Indica che il [INotifySink2:: OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) metodo deve essere richiamato.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-109">Indicates that the [INotifySink2::OnSyncCallOut](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLENTER`|<span data-ttu-id="9e7d5-110">Indica che il [INotifySink2:: OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) metodo deve essere richiamato.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-110">Indicates that the [INotifySink2::OnSyncCallEnter](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLEXIT`|<span data-ttu-id="9e7d5-111">Indica che il [INotifySink2:: OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) metodo deve essere richiamato.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-111">Indicates that the [INotifySink2::OnSyncCallExit](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ONSYNCCALLRETURN`|<span data-ttu-id="9e7d5-112">Indica che il [INotifySink2:: OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) metodo deve essere richiamato.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-112">Indicates that the [INotifySink2::OnSyncCallReturn](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md) method should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALLSYNC`|<span data-ttu-id="9e7d5-113">Indica che tutti i [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) metodi devono essere richiamati.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-113">Indicates that all of the [INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md) methods should be invoked.</span></span>|  
|`NOTIFY_FILTER_ALL`|<span data-ttu-id="9e7d5-114">Attiva tutte le notifiche esistenti e future.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-114">Activates all existing and future notifications.</span></span>|  
|`NOTIFY_FILTER_NONE`|<span data-ttu-id="9e7d5-115">Indica che nessun metodo di notifica deve essere richiamato.</span><span class="sxs-lookup"><span data-stu-id="9e7d5-115">Indicates that no notification methods should be invoked.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e7d5-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9e7d5-116">Requirements</span></span>  
 <span data-ttu-id="9e7d5-117">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="9e7d5-117">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e7d5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e7d5-118">See Also</span></span>  
 [<span data-ttu-id="9e7d5-119">Enumerazioni dell'archivio simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="9e7d5-119">Diagnostics Symbol Store Enumerations</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)
