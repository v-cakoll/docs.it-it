---
title: Metodo ICorDebugManagedCallback::Exception
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Exception
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91318ea596cc7d6c8a747901fea2749a64aa2623
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168116"
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="da52f-102">Metodo ICorDebugManagedCallback::Exception</span><span class="sxs-lookup"><span data-stu-id="da52f-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="da52f-103">Notifica al debugger che è stata generata un'eccezione dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="da52f-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da52f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="da52f-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da52f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="da52f-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="da52f-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="da52f-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="da52f-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="da52f-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="da52f-108">[in] Se questo valore è `false`, l'eccezione non è ancora stato elaborato dall'applicazione; in caso contrario, l'eccezione viene gestita e interromperà il processo.</span><span class="sxs-lookup"><span data-stu-id="da52f-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da52f-109">Note</span><span class="sxs-lookup"><span data-stu-id="da52f-109">Remarks</span></span>  
 <span data-ttu-id="da52f-110">L'eccezione specifica può essere recuperato dall'oggetto thread.</span><span class="sxs-lookup"><span data-stu-id="da52f-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da52f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="da52f-111">Requirements</span></span>  
 <span data-ttu-id="da52f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da52f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da52f-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="da52f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="da52f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da52f-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="da52f-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="da52f-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="da52f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="da52f-116">See also</span></span>

- [<span data-ttu-id="da52f-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="da52f-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
