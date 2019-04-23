---
title: Metodo INotifySink2::OnSyncCallOut
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallOut
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallOut
helpviewer_keywords:
- INotifySink2::OnSyncCallOut method [.NET Framework debugging]
- OnSyncCallOut method [.NET Framework debugging]
ms.assetid: 97f15656-8677-4079-8553-a1d8603355d6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cf36b9e09f5e9eeb28930a6adc48426927a60e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59145691"
---
# <a name="inotifysink2onsynccallout-method"></a><span data-ttu-id="14f40-102">Metodo INotifySink2::OnSyncCallOut</span><span class="sxs-lookup"><span data-stu-id="14f40-102">INotifySink2::OnSyncCallOut Method</span></span>
<span data-ttu-id="14f40-103">Viene richiamato quando una chiamata non è più valido.</span><span class="sxs-lookup"><span data-stu-id="14f40-103">Gets invoked when a call is out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14f40-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="14f40-104">Syntax</span></span>  
  
```  
HRESULT OnSyncCallOut  
(  
    [in]  CALL_ID  in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*   out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14f40-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="14f40-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="14f40-106">[in] ID della chiamata che non è più valido. Visualizzare [Struttura CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="14f40-106">[in] ID of the call that is out. See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="14f40-107">[out] Chiamare il buffer.</span><span class="sxs-lookup"><span data-stu-id="14f40-107">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="14f40-108">[out] Dimensioni del buffer di chiamate, espressa in byte.</span><span class="sxs-lookup"><span data-stu-id="14f40-108">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14f40-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="14f40-109">Return Value</span></span>  
 <span data-ttu-id="14f40-110">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="14f40-110">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14f40-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="14f40-111">Requirements</span></span>  
 <span data-ttu-id="14f40-112">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="14f40-112">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f40-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="14f40-113">See also</span></span>

- [<span data-ttu-id="14f40-114">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="14f40-114">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="14f40-115">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="14f40-115">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="14f40-116">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="14f40-116">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
