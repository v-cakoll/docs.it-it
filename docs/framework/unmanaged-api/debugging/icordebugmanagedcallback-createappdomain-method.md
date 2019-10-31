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
ms.openlocfilehash: fa829d0a08846287835d2ac66a461b4b9b27a09a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73090235"
---
# <a name="icordebugmanagedcallbackcreateappdomain-method"></a><span data-ttu-id="a7ee2-102">Metodo ICorDebugManagedCallback::CreateAppDomain</span><span class="sxs-lookup"><span data-stu-id="a7ee2-102">ICorDebugManagedCallback::CreateAppDomain Method</span></span>
<span data-ttu-id="a7ee2-103">Notifica al debugger che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7ee2-103">Notifies the debugger that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7ee2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7ee2-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAppDomain (  
    [in] ICorDebugProcess   *pProcess,  
    [in] ICorDebugAppDomain *pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7ee2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7ee2-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a7ee2-106">in Puntatore a un oggetto ICorDebugProcess che rappresenta il processo in cui è stato creato il dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a7ee2-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the application domain was created.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="a7ee2-107">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione creato.</span><span class="sxs-lookup"><span data-stu-id="a7ee2-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that has been created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7ee2-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7ee2-108">Requirements</span></span>  
 <span data-ttu-id="a7ee2-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7ee2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7ee2-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7ee2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7ee2-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7ee2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7ee2-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7ee2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ee2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7ee2-113">See also</span></span>

- [<span data-ttu-id="a7ee2-114">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="a7ee2-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
