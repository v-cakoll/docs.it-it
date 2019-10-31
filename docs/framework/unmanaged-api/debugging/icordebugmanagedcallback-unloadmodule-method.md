---
title: Metodo ICorDebugManagedCallback::UnloadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadModule
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadModule method [.NET Framework debugging]
- UnloadModule method [.NET Framework debugging]
ms.assetid: b12bfcd9-1e29-48bf-9a3d-44bfae5df5e8
topic_type:
- apiref
ms.openlocfilehash: 70aaf32b9da751b49571ab98a95e432b7f84caa9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130644"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="9a8e2-102">Metodo ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="9a8e2-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="9a8e2-103">Notifica al debugger che è stato scaricato un modulo di Common Language Runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="9a8e2-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a8e2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a8e2-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a8e2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a8e2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9a8e2-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="9a8e2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="9a8e2-107">in Puntatore a un oggetto ICorDebugModule che rappresenta il modulo.</span><span class="sxs-lookup"><span data-stu-id="9a8e2-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a8e2-108">Note</span><span class="sxs-lookup"><span data-stu-id="9a8e2-108">Remarks</span></span>  
 <span data-ttu-id="9a8e2-109">Il modulo non deve essere usato dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="9a8e2-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a8e2-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a8e2-110">Requirements</span></span>  
 <span data-ttu-id="9a8e2-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a8e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a8e2-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a8e2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a8e2-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a8e2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a8e2-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8e2-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a8e2-115">See also</span></span>

- [<span data-ttu-id="9a8e2-116">Metodo LoadModule</span><span class="sxs-lookup"><span data-stu-id="9a8e2-116">LoadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="9a8e2-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9a8e2-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
