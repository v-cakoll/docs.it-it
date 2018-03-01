---
title: Metodo INotifySink2::OnSyncCallEnter
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
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 102a4a24b82c87bed00895dc723b7fca02c20bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="0d997-102">Metodo INotifySink2::OnSyncCallEnter</span><span class="sxs-lookup"><span data-stu-id="0d997-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="0d997-103">Viene richiamato quando si immette una chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d997-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d997-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0d997-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0d997-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0d997-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="0d997-106">[in] ID di chiamata effettuata.</span><span class="sxs-lookup"><span data-stu-id="0d997-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="0d997-107">Vedere [Struttura CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="0d997-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="0d997-108">[in] Buffer di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0d997-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="0d997-109">[in] Dimensione del buffer di chiamata, in byte.</span><span class="sxs-lookup"><span data-stu-id="0d997-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d997-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0d997-110">Return Value</span></span>  
 <span data-ttu-id="0d997-111">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="0d997-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d997-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0d997-112">Requirements</span></span>  
 <span data-ttu-id="0d997-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="0d997-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d997-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d997-114">See Also</span></span>  
 [<span data-ttu-id="0d997-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="0d997-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [<span data-ttu-id="0d997-116">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="0d997-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="0d997-117">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="0d997-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
