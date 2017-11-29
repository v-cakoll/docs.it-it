---
title: Metodo ICorDebugManagedCallback::Exception
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.Exception
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::Exception
helpviewer_keywords:
- Exception method, ICorDebugManagedCallback interface [.NET Framework debugging]
- ICorDebugManagedCallback::Exception method [.NET Framework debugging]
ms.assetid: ab18a509-dff3-4930-b585-bd15e0414176
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 550b4961cb082ca6ee745b1d998a6fa95a22ace3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackexception-method"></a><span data-ttu-id="29be1-102">Metodo ICorDebugManagedCallback::Exception</span><span class="sxs-lookup"><span data-stu-id="29be1-102">ICorDebugManagedCallback::Exception Method</span></span>
<span data-ttu-id="29be1-103">Notifica al debugger che è stata generata un'eccezione dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="29be1-103">Notifies the debugger that an exception has been thrown from managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29be1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="29be1-104">Syntax</span></span>  
  
```  
HRESULT Exception (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] BOOL                unhandled  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="29be1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="29be1-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="29be1-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="29be1-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the exception was thrown.</span></span>  
  
 `pThread`  
 <span data-ttu-id="29be1-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread in cui è stata generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="29be1-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the exception was thrown.</span></span>  
  
 `unhandled`  
 <span data-ttu-id="29be1-108">[in] Se questo valore è `false`, l'eccezione non è stato ancora stato elaborato dall'applicazione; in caso contrario, l'eccezione viene gestita e interromperà il processo.</span><span class="sxs-lookup"><span data-stu-id="29be1-108">[in] If this value is `false`, the exception has not yet been processed by the application; otherwise, the exception is unhandled and will terminate the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29be1-109">Note</span><span class="sxs-lookup"><span data-stu-id="29be1-109">Remarks</span></span>  
 <span data-ttu-id="29be1-110">L'eccezione specifica può essere recuperato dall'oggetto del thread.</span><span class="sxs-lookup"><span data-stu-id="29be1-110">The specific exception can be retrieved from the thread object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29be1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="29be1-111">Requirements</span></span>  
 <span data-ttu-id="29be1-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29be1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29be1-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="29be1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="29be1-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="29be1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="29be1-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29be1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29be1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29be1-116">See Also</span></span>  
 [<span data-ttu-id="29be1-117">ICorDebugManagedCallback (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="29be1-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
