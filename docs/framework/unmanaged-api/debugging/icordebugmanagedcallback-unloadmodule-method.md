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
ms.openlocfilehash: 4b44a16d143c1daea1ea6c36eb096ab9a937b272
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210044"
---
# <a name="icordebugmanagedcallbackunloadmodule-method"></a><span data-ttu-id="6c6fd-102">Metodo ICorDebugManagedCallback::UnloadModule</span><span class="sxs-lookup"><span data-stu-id="6c6fd-102">ICorDebugManagedCallback::UnloadModule Method</span></span>
<span data-ttu-id="6c6fd-103">Notifica al debugger che è stato scaricato un modulo di Common Language Runtime (DLL).</span><span class="sxs-lookup"><span data-stu-id="6c6fd-103">Notifies the debugger that a common language runtime module (DLL) has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c6fd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c6fd-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadModule (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugModule     *pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c6fd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c6fd-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6c6fd-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene il modulo.</span><span class="sxs-lookup"><span data-stu-id="6c6fd-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the module.</span></span>  
  
 `pModule`  
 <span data-ttu-id="6c6fd-107">in Puntatore a un oggetto ICorDebugModule che rappresenta il modulo.</span><span class="sxs-lookup"><span data-stu-id="6c6fd-107">[in] A pointer to an ICorDebugModule object that represents the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c6fd-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="6c6fd-108">Remarks</span></span>  
 <span data-ttu-id="6c6fd-109">Il modulo non deve essere usato dopo questa chiamata.</span><span class="sxs-lookup"><span data-stu-id="6c6fd-109">The module should not be used after this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c6fd-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c6fd-110">Requirements</span></span>  
 <span data-ttu-id="6c6fd-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c6fd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c6fd-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c6fd-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c6fd-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c6fd-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c6fd-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c6fd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c6fd-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c6fd-115">See also</span></span>

- [<span data-ttu-id="6c6fd-116">Metodo LoadModule</span><span class="sxs-lookup"><span data-stu-id="6c6fd-116">LoadModule Method</span></span>](icordebugmanagedcallback-loadmodule-method.md)
- [<span data-ttu-id="6c6fd-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="6c6fd-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
