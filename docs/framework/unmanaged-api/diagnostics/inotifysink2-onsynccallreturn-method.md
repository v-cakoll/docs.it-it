---
title: Metodo INotifySink2::OnSyncCallReturn
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallReturn
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallReturn
helpviewer_keywords:
- OnSyncCallReturn method [.NET Framework debugging]
- INotifySink2::OnSyncCallReturn method [.NET Framework debugging]
ms.assetid: c1bda761-6292-4750-a14b-7d5db8f33456
topic_type:
- apiref
ms.openlocfilehash: ff1dabcfc366607639cd98be4392f8dd59dc83a1
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442007"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="9bf82-102">Metodo INotifySink2::OnSyncCallReturn</span><span class="sxs-lookup"><span data-stu-id="9bf82-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="9bf82-103">Viene richiamato quando una chiamata restituisce.</span><span class="sxs-lookup"><span data-stu-id="9bf82-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bf82-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9bf82-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9bf82-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9bf82-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="9bf82-106">in ID della chiamata restituita da.</span><span class="sxs-lookup"><span data-stu-id="9bf82-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="9bf82-107">Vedere [struttura CALL_ID](call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="9bf82-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="9bf82-108">in Buffer di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9bf82-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="9bf82-109">in Dimensioni del buffer di chiamata, in byte.</span><span class="sxs-lookup"><span data-stu-id="9bf82-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9bf82-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9bf82-110">Return Value</span></span>  
 <span data-ttu-id="9bf82-111">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="9bf82-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bf82-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9bf82-112">Requirements</span></span>  
 <span data-ttu-id="9bf82-113">**Intestazione:** ProtocolNotify2. idl</span><span class="sxs-lookup"><span data-stu-id="9bf82-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf82-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9bf82-114">See also</span></span>

- [<span data-ttu-id="9bf82-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="9bf82-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="9bf82-116">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="9bf82-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="9bf82-117">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="9bf82-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)
