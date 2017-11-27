---
title: Metodo INotifyConnection2::RegisterNotifySource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifyConnection2.RegisterNotifySource
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifyConnection2::RegisterNotifySource
helpviewer_keywords:
- INotifyConnection2::RegisterNotifySource method [.NET Framework debugging]
- RegisterNotifySource method [.NET Framework debugging]
ms.assetid: 2632da80-6e4b-4429-8dee-b382745a5f81
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 370f19d9fd1cbc268d43b9970b0cf27290796562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="inotifyconnection2registernotifysource-method"></a><span data-ttu-id="36321-102">Metodo INotifyConnection2::RegisterNotifySource</span><span class="sxs-lookup"><span data-stu-id="36321-102">INotifyConnection2::RegisterNotifySource Method</span></span>
<span data-ttu-id="36321-103">Installa un'origine di notifica specificato.</span><span class="sxs-lookup"><span data-stu-id="36321-103">Installs a specified notification source.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36321-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="36321-104">Syntax</span></span>  
  
```  
HRESULT RegisterNotifySource  
(  
    [in]  INotifySource2*  in_pNotifySource,  
    [out] INotifySink2**   out_ppNotifySink  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="36321-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="36321-105">Parameters</span></span>  
 `in_pNotifySource`  
 <span data-ttu-id="36321-106">[in] Specifica l'oggetto da utilizzare come origine della notifica.</span><span class="sxs-lookup"><span data-stu-id="36321-106">[in] Specifies the object to be used as the notification source.</span></span>  
  
 `out_ppNotifySink`  
 <span data-ttu-id="36321-107">[out] Riceve l'oggetto da utilizzare come sink di notifica.</span><span class="sxs-lookup"><span data-stu-id="36321-107">[out] Receives the object to be used as the notification sink.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36321-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="36321-108">Return Value</span></span>  
 <span data-ttu-id="36321-109">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="36321-109">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36321-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="36321-110">Requirements</span></span>  
 <span data-ttu-id="36321-111">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="36321-111">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36321-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="36321-112">See Also</span></span>  
 [<span data-ttu-id="36321-113">INotifyConnection2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="36321-113">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="36321-114">INotifySource2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="36321-114">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="36321-115">INotifySink2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="36321-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="36321-116">UnregisterNotifySource (metodo)</span><span class="sxs-lookup"><span data-stu-id="36321-116">UnregisterNotifySource Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-unregisternotifysource-method.md)
