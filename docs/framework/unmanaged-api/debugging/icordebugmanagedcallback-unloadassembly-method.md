---
title: Metodo ICorDebugManagedCallback::UnloadAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UnloadAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UnloadAssembly
helpviewer_keywords:
- ICorDebugManagedCallback::UnloadAssembly method [.NET Framework debugging]
- UnloadAssembly method [.NET Framework debugging]
ms.assetid: 6734321c-c8a9-401f-a558-cad715ec4a77
topic_type:
- apiref
ms.openlocfilehash: 06c08499298656c8314d72667d9dac88c8d11e6a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788348"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="dd227-102">Metodo ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="dd227-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="dd227-103">Notifica al debugger che è stato scaricato un assembly Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="dd227-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd227-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd227-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd227-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dd227-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="dd227-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="dd227-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="dd227-107">in Puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly.</span><span class="sxs-lookup"><span data-stu-id="dd227-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd227-108">Note</span><span class="sxs-lookup"><span data-stu-id="dd227-108">Remarks</span></span>  
 <span data-ttu-id="dd227-109">L'assembly non deve essere utilizzato dopo questo callback.</span><span class="sxs-lookup"><span data-stu-id="dd227-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd227-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="dd227-110">Requirements</span></span>  
 <span data-ttu-id="dd227-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd227-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd227-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd227-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd227-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd227-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd227-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd227-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd227-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd227-115">See also</span></span>

- [<span data-ttu-id="dd227-116">Metodo LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="dd227-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="dd227-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="dd227-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
