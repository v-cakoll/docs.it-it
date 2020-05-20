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
ms.openlocfilehash: f81ef3f5959e279b3fbbd94d6c5e8a2d86a38e7f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442020"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="84e74-102">Metodo INotifySink2::OnSyncCallExit</span><span class="sxs-lookup"><span data-stu-id="84e74-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="84e74-103">Viene richiamato quando si esce da una chiamata.</span><span class="sxs-lookup"><span data-stu-id="84e74-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e74-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84e74-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84e74-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="84e74-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="84e74-106">in ID della chiamata da chiudere.</span><span class="sxs-lookup"><span data-stu-id="84e74-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="84e74-107">Vedere [struttura CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="84e74-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="84e74-108">out Buffer di chiamata.</span><span class="sxs-lookup"><span data-stu-id="84e74-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="84e74-109">out Dimensioni del buffer di chiamata, in byte.</span><span class="sxs-lookup"><span data-stu-id="84e74-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84e74-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="84e74-110">Return Value</span></span>  
 <span data-ttu-id="84e74-111">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="84e74-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e74-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84e74-112">Requirements</span></span>  
 <span data-ttu-id="84e74-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="84e74-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e74-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84e74-114">See also</span></span>

- [<span data-ttu-id="84e74-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="84e74-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="84e74-116">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="84e74-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="84e74-117">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="84e74-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
