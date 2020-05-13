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
ms.openlocfilehash: cd4a16bc8b48f147ed03555b51eee5f42a445bc6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212700"
---
# <a name="icordebugmanagedcallbackloadmodule-method"></a><span data-ttu-id="7b5a6-102">Metodo ICorDebugManagedCallback::LoadModule</span><span class="sxs-lookup"><span data-stu-id="7b5a6-102">ICorDebugManagedCallback::LoadModule Method</span></span>
<span data-ttu-id="7b5a6-103">Notifica al debugger che un modulo Common Language Runtime (CLR) è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="7b5a6-103">Notifies the debugger that a common language runtime (CLR) module has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b5a6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b5a6-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadModule (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b5a6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b5a6-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7b5a6-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stato caricato il modulo.</span><span class="sxs-lookup"><span data-stu-id="7b5a6-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the module has been loaded.</span></span>  
  
 `pModule`  
 <span data-ttu-id="7b5a6-107">in Puntatore a un oggetto ICorDebugModule che rappresenta il modulo CLR.</span><span class="sxs-lookup"><span data-stu-id="7b5a6-107">[in] A pointer to an ICorDebugModule object that represents the CLR module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b5a6-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7b5a6-108">Remarks</span></span>  
 <span data-ttu-id="7b5a6-109">Il `LoadModule` callback fornisce un tempo appropriato per esaminare i metadati per il modulo, impostare i flag del compilatore JIT (just-in-Time) o abilitare o disabilitare i callback di caricamento delle classi per il modulo.</span><span class="sxs-lookup"><span data-stu-id="7b5a6-109">The `LoadModule` callback provides an appropriate time to examine metadata for the module, set just-in-time (JIT) compiler flags, or enable or disable class loading callbacks for the module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b5a6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b5a6-110">Requirements</span></span>  
 <span data-ttu-id="7b5a6-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b5a6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b5a6-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b5a6-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b5a6-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b5a6-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b5a6-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b5a6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b5a6-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b5a6-115">See also</span></span>

- [<span data-ttu-id="7b5a6-116">Metodo UnloadModule</span><span class="sxs-lookup"><span data-stu-id="7b5a6-116">UnloadModule Method</span></span>](icordebugmanagedcallback-unloadmodule-method.md)
- [<span data-ttu-id="7b5a6-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="7b5a6-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
