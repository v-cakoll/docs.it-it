---
title: Metodo ICorDebugManagedCallback::LoadModule
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadModule
helpviewer_keywords:
- ICorDebugManagedCallback::LoadModule method [.NET Framework debugging]
- LoadModule method [.NET Framework debugging]
ms.assetid: 66ec04e9-87cb-42ce-9720-81522abb5d5a
topic_type:
- apiref
ms.openlocfilehash: d13c5be314dc39f3e7b42a8d6b13f6a25751067d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130718"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="85470-102">Metodo ICorDebugManagedCallback::LoadModule</span><span class="sxs-lookup"><span data-stu-id="85470-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="85470-103">Notifica al debugger che un modulo Common Language Runtime (CLR) è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="85470-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85470-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85470-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85470-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85470-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="85470-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stato caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="85470-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="85470-107">in Puntatore a un oggetto ICorDebugModule che rappresenta il modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="85470-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85470-108">Note</span><span class="sxs-lookup"><span data-stu-id="85470-108">Remarks</span></span>  
 <span data-ttu-id="85470-109">Il callback `LoadModule` fornisce un tempo appropriato per esaminare i metadati per il modulo, impostare i flag del compilatore JIT (just-in-Time) o abilitare o disabilitare i callback di caricamento delle classi per il modulo.</span><span class="sxs-lookup"><span data-stu-id="85470-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85470-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85470-110">Requirements</span></span>  
 <span data-ttu-id="85470-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85470-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85470-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85470-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85470-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85470-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85470-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85470-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85470-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85470-115">See also</span></span>

- [<span data-ttu-id="85470-116">Metodo UnloadModule</span><span class="sxs-lookup"><span data-stu-id="85470-116">UnloadModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="85470-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="85470-117">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
