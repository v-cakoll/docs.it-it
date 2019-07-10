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
ms.openlocfilehash: 85247f2f3672e7827f4dd0c93e50cd5da914ee8f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755768"
---
# <a name="icordebugmanagedcallbackexitthread-method"></a><span data-ttu-id="a7653-102">Metodo ICorDebugManagedCallback::ExitThread</span><span class="sxs-lookup"><span data-stu-id="a7653-102">ICorDebugManagedCallback::ExitThread Method</span></span>
<span data-ttu-id="a7653-103">Notifica al debugger che un thread che stava eseguendo codice gestito è stato terminato.</span><span class="sxs-lookup"><span data-stu-id="a7653-103">Notifies the debugger that a thread that was executing managed code has exited.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7653-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7653-104">Syntax</span></span>  
  
```cpp  
HRESULT ExitThread (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *thread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7653-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7653-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="a7653-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="a7653-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread.</span></span>  
  
 `thread`  
 <span data-ttu-id="a7653-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="a7653-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7653-108">Note</span><span class="sxs-lookup"><span data-stu-id="a7653-108">Remarks</span></span>  
 <span data-ttu-id="a7653-109">Una volta il `ExitThread` callback viene attivato, il thread non apparirà più nelle enumerazioni dei thread.</span><span class="sxs-lookup"><span data-stu-id="a7653-109">Once the `ExitThread` callback is fired, the thread will no longer appear in thread enumerations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7653-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7653-110">Requirements</span></span>  
 <span data-ttu-id="a7653-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7653-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7653-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7653-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7653-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7653-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7653-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7653-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7653-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7653-115">See also</span></span>

- [<span data-ttu-id="a7653-116">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="a7653-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
