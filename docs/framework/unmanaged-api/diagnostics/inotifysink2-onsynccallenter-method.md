---
title: Metodo INotifySink2::OnSyncCallEnter
ms.date: 03/30/2017
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
ms.openlocfilehash: 85f00698f42f120b209cca14f293a58ae4c65f6f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442033"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="d7d40-102">Metodo INotifySink2::OnSyncCallEnter</span><span class="sxs-lookup"><span data-stu-id="d7d40-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="d7d40-103">Viene richiamato quando si immette una chiamata.</span><span class="sxs-lookup"><span data-stu-id="d7d40-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7d40-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7d40-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7d40-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d7d40-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="d7d40-106">in ID della chiamata immessa.</span><span class="sxs-lookup"><span data-stu-id="d7d40-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="d7d40-107">Vedere [struttura CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="d7d40-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="d7d40-108">in Buffer di chiamata.</span><span class="sxs-lookup"><span data-stu-id="d7d40-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="d7d40-109">in Dimensioni del buffer di chiamata, in byte.</span><span class="sxs-lookup"><span data-stu-id="d7d40-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7d40-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d7d40-110">Return Value</span></span>  
 <span data-ttu-id="d7d40-111">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="d7d40-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7d40-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d7d40-112">Requirements</span></span>  
 <span data-ttu-id="d7d40-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="d7d40-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d40-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7d40-114">See also</span></span>

- [<span data-ttu-id="d7d40-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="d7d40-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="d7d40-116">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="d7d40-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="d7d40-117">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="d7d40-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
