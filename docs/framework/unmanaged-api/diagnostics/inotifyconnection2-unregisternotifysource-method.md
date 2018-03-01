---
title: Metodo INotifyConnection2::UnregisterNotifySource
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
- INotifyConnection2.UnregisterNotifySource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifyConnection2::UnregisterNotifySource
helpviewer_keywords:
- INotifyConnection2::UnregisterNotifySource method [.NET Framework debugging]
- UnregisterNotifySource method [.NET Framework debugging]
ms.assetid: 2fc6c715-646f-41fd-9c12-c59b40575269
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 308055a0b8a5d07d93838479de6c1dae3c29517d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="inotifyconnection2unregisternotifysource-method"></a><span data-ttu-id="f6581-102">Metodo INotifyConnection2::UnregisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="f6581-102">INotifyConnection2::UnregisterNotifySource Method</span></span>
<span data-ttu-id="f6581-103">Rimuove un oggetto di origine di notifica specificato dalla connessione.</span><span class="sxs-lookup"><span data-stu-id="f6581-103">Removes a specified notification source object from the connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6581-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f6581-104">Syntax</span></span>  
  
```  
HRESULT UnregisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6581-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f6581-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="f6581-106">[in] Oggetto di notifica di annullamento della registrazione.</span><span class="sxs-lookup"><span data-stu-id="f6581-106">[in] Notification object to be unregistered.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6581-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f6581-107">Return Value</span></span>  
 <span data-ttu-id="f6581-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="f6581-108">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6581-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f6581-109">Requirements</span></span>  
 <span data-ttu-id="f6581-110">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="f6581-110">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6581-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f6581-111">See Also</span></span>  
 [<span data-ttu-id="f6581-112">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="f6581-112">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="f6581-113">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="f6581-113">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="f6581-114">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="f6581-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="f6581-115">Metodo RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="f6581-115">RegisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-registernotifysource-method.md)
