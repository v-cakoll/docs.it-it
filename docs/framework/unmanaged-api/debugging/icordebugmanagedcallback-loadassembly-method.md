---
title: Metodo ICorDebugManagedCallback::LoadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadAssembly
helpviewer_keywords:
- LoadAssembly method [.NET Framework debugging]
- ICorDebugManagedCallback::LoadAssembly method [.NET Framework debugging]
ms.assetid: 55cb673a-e240-43a6-a406-6912e7c0fe66
topic_type:
- apiref
ms.openlocfilehash: 80836cbbf82a97ccd6dc7251e5cbe934e0cbe66f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777281"
---
# <a name="icordebugmanagedcallbackloadassembly-method"></a><span data-ttu-id="9a5f3-102">Metodo ICorDebugManagedCallback::LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="9a5f3-102">ICorDebugManagedCallback::LoadAssembly Method</span></span>
<span data-ttu-id="9a5f3-103">Notifica al debugger che un assembly Common Language Runtime (CLR) è stato caricato correttamente.</span><span class="sxs-lookup"><span data-stu-id="9a5f3-103">Notifies the debugger that a common language runtime (CLR) assembly has been successfully loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a5f3-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadAssembly (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugAssembly  *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a5f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a5f3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="9a5f3-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione in cui è stato caricato l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9a5f3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the assembly has been loaded.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="9a5f3-107">in Puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly.</span><span class="sxs-lookup"><span data-stu-id="9a5f3-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a5f3-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9a5f3-108">Requirements</span></span>  
 <span data-ttu-id="9a5f3-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a5f3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a5f3-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a5f3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a5f3-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a5f3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a5f3-112">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a5f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5f3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a5f3-113">See also</span></span>

- [<span data-ttu-id="9a5f3-114">Metodo UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="9a5f3-114">UnloadAssembly Method</span></span>](icordebugmanagedcallback-unloadassembly-method.md)
- [<span data-ttu-id="9a5f3-115">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="9a5f3-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
