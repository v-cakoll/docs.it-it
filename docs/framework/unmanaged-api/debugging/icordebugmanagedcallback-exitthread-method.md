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
ms.openlocfilehash: 7a928aed73c0287a4cad2432fa6b6ebec43ea285
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489566"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="9a513-102">Metodo ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="9a513-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="9a513-103">Notifica al debugger che un thread che stava eseguendo codice gestito è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="9a513-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a513-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a513-104">Syntax</span></span>  
  
```  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a513-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a513-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9a513-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="9a513-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="9a513-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="9a513-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a513-108">Note</span><span class="sxs-lookup"><span data-stu-id="9a513-108">Remarks</span></span>  
 <span data-ttu-id="9a513-109">Una volta il `ExitThread` callback viene attivato, il thread non apparirà più nelle enumerazioni dei thread.</span><span class="sxs-lookup"><span data-stu-id="9a513-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a513-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a513-110">Requirements</span></span>  
 <span data-ttu-id="9a513-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a513-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a513-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a513-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a513-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a513-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a513-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a513-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a513-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a513-115">See also</span></span>
- [<span data-ttu-id="9a513-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9a513-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
