---
title: Metodo ICorDebugManagedCallback::CreateAppDomain
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateAppDomain
helpviewer_keywords:
- CreateAppDomain method [.NET Framework debugging]
- ICorDebugManagedCallback::CreateAppDomain method [.NET Framework debugging]
ms.assetid: 48d410d7-6749-4125-a8fd-f9562c7088e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3958e62f23615d4c9038713bb973a6d16424f348
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759720"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="0cd19-102">Metodo ICorDebugManagedCallback::CreateAppDomain</span><span class="sxs-lookup"><span data-stu-id="0cd19-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="0cd19-103">Notifica al debugger che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0cd19-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd19-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cd19-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cd19-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0cd19-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0cd19-106">[in] Un puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0cd19-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="0cd19-107">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione creato.</span><span class="sxs-lookup"><span data-stu-id="0cd19-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cd19-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0cd19-108">Requirements</span></span>  
 <span data-ttu-id="0cd19-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cd19-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cd19-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cd19-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cd19-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cd19-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cd19-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cd19-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd19-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cd19-113">See also</span></span>

- [<span data-ttu-id="0cd19-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0cd19-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
