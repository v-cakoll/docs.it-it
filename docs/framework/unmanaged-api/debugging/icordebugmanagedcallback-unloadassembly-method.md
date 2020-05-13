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
ms.openlocfilehash: 07996a78d7f559de587c8a3eb2babfc06675169d
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212646"
---
# <a name="icordebugmanagedcallbackunloadassembly-method"></a><span data-ttu-id="0f230-102">Metodo ICorDebugManagedCallback::UnloadAssembly</span><span class="sxs-lookup"><span data-stu-id="0f230-102">ICorDebugManagedCallback::UnloadAssembly Method</span></span>
<span data-ttu-id="0f230-103">Notifica al debugger che è stato scaricato un assembly Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0f230-103">Notifies the debugger that a common language runtime assembly has been unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f230-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f230-104">Syntax</span></span>  
  
```cpp  
HRESULT UnloadAssembly (  
    [in] IcorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugAssembly   *pAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f230-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f230-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="0f230-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione che contiene l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0f230-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contained the assembly.</span></span>  
  
 `pAssembly`  
 <span data-ttu-id="0f230-107">in Puntatore a un oggetto ICorDebugAssembly che rappresenta l'assembly.</span><span class="sxs-lookup"><span data-stu-id="0f230-107">[in] A pointer to an ICorDebugAssembly object that represents the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f230-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0f230-108">Remarks</span></span>  
 <span data-ttu-id="0f230-109">L'assembly non deve essere utilizzato dopo questo callback.</span><span class="sxs-lookup"><span data-stu-id="0f230-109">The assembly should not be used after this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f230-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f230-110">Requirements</span></span>  
 <span data-ttu-id="0f230-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f230-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f230-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f230-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f230-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f230-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f230-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f230-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f230-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f230-115">See also</span></span>

- [<span data-ttu-id="0f230-116">Metodo LoadAssembly</span><span class="sxs-lookup"><span data-stu-id="0f230-116">LoadAssembly Method</span></span>](icordebugmanagedcallback-loadassembly-method.md)
- [<span data-ttu-id="0f230-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="0f230-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
