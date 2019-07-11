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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84fd40dbecf9a866a4ec0889cbb62c475c063475
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736226"
---
# <a name="inotifysink2onsynccallreturn-method"></a><span data-ttu-id="67430-102">Metodo INotifySink2::OnSyncCallReturn</span><span class="sxs-lookup"><span data-stu-id="67430-102">INotifySink2::OnSyncCallReturn Method</span></span>
<span data-ttu-id="67430-103">Viene richiamato quando una chiamata termina.</span><span class="sxs-lookup"><span data-stu-id="67430-103">Gets invoked when a call returns.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67430-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67430-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallReturn  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67430-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67430-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="67430-106">[in] ID della restituito dalla chiamata.</span><span class="sxs-lookup"><span data-stu-id="67430-106">[in] ID of the call being returned from.</span></span> <span data-ttu-id="67430-107">Visualizzare [Struttura CALL_ID](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span><span class="sxs-lookup"><span data-stu-id="67430-107">See [CALL_ID Structure](../../../../docs/framework/unmanaged-api/diagnostics/call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="67430-108">[in] Chiamare il buffer.</span><span class="sxs-lookup"><span data-stu-id="67430-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="67430-109">[in] Dimensioni del buffer di chiamate, espressa in byte.</span><span class="sxs-lookup"><span data-stu-id="67430-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67430-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="67430-110">Return Value</span></span>  
 <span data-ttu-id="67430-111">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="67430-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67430-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67430-112">Requirements</span></span>  
 <span data-ttu-id="67430-113">**Intestazione:** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="67430-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67430-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67430-114">See also</span></span>

- [<span data-ttu-id="67430-115">Interfaccia INotifySink2</span><span class="sxs-lookup"><span data-stu-id="67430-115">INotifySink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)
- [<span data-ttu-id="67430-116">Interfaccia INotifySource2</span><span class="sxs-lookup"><span data-stu-id="67430-116">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="67430-117">Interfaccia INotifyConnection2</span><span class="sxs-lookup"><span data-stu-id="67430-117">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
