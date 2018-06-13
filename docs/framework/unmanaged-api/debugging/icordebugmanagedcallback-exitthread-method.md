---
title: Metodo ICorDebugManagedCallback::ExitThread
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ExitThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ExitThread
helpviewer_keywords:
- ExitThread method [.NET Framework debugging]
- ICorDebugManagedCallback::ExitThread method [.NET Framework debugging]
ms.assetid: 62db708b-6cf0-45c5-b897-4b5c75bd2505
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24b01fecc7947d14e36b4411a58d200667b0f2a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415542"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="599de-102">Metodo ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="599de-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="599de-103">Notifica al debugger che un thread che era in esecuzione il codice gestito è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="599de-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="599de-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="599de-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="599de-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="599de-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="599de-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione contenente il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="599de-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="599de-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="599de-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="599de-108">Note</span><span class="sxs-lookup"><span data-stu-id="599de-108">Remarks</span></span>  
 <span data-ttu-id="599de-109">Una volta il `ExitThread` callback viene generato, il thread non verrà più visualizzato nelle enumerazioni dei thread.</span><span class="sxs-lookup"><span data-stu-id="599de-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="599de-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="599de-110">Requirements</span></span>  
 <span data-ttu-id="599de-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="599de-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="599de-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="599de-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="599de-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="599de-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="599de-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="599de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="599de-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="599de-115">See Also</span></span>  
 [<span data-ttu-id="599de-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="599de-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
