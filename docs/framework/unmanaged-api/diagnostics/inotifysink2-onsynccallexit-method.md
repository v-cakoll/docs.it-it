---
title: Metodo INotifySink2::OnSyncCallExit
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8124af428d68606382e4449db3f68b0b61eb432c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500265"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="7e844-102">Metodo INotifySink2::OnSyncCallExit</span><span class="sxs-lookup"><span data-stu-id="7e844-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="7e844-103">Viene richiamato quando si esce da una chiamata.</span><span class="sxs-lookup"><span data-stu-id="7e844-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e844-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7e844-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e844-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7e844-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="7e844-106">[in] ID della chiamata in fase di chiusura.</span><span class="sxs-lookup"><span data-stu-id="7e844-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="7e844-107">Visualizzare [Struttura CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="7e844-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="7e844-108">[out] Chiamare il buffer.</span><span class="sxs-lookup"><span data-stu-id="7e844-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="7e844-109">[out] Dimensioni del buffer di chiamate, espressa in byte.</span><span class="sxs-lookup"><span data-stu-id="7e844-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e844-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7e844-110">Return Value</span></span>  
 <span data-ttu-id="7e844-111">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="7e844-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e844-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7e844-112">Requirements</span></span>  
 <span data-ttu-id="7e844-113">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="7e844-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e844-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e844-114">See also</span></span>
- [<span data-ttu-id="7e844-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="7e844-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="7e844-116">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="7e844-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="7e844-117">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="7e844-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
