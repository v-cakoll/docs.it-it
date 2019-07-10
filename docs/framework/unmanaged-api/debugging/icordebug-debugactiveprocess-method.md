---
title: Metodo ICorDebug::DebugActiveProcess
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe94203d315c32b62a191adf294a9c1310fe28e0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738269"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="4729f-102">Metodo ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="4729f-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="4729f-103">Collega il debugger a un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="4729f-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4729f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4729f-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4729f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4729f-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="4729f-106">[in] L'ID del processo a cui il debugger deve essere allegato.</span><span class="sxs-lookup"><span data-stu-id="4729f-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="4729f-107">[in] Valore booleano che è impostato su `true` se il debugger deve comportarsi come il debugger di Win32 per il processo e inviare il callback non gestite; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4729f-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="4729f-108">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato connesso il debugger.</span><span class="sxs-lookup"><span data-stu-id="4729f-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4729f-109">Note</span><span class="sxs-lookup"><span data-stu-id="4729f-109">Remarks</span></span>  
 <span data-ttu-id="4729f-110">Debug di interoperabilità non è supportato nelle piattaforme Win9x e non x86, ad esempio le piattaforme basate su IA-64 e AMD64 basato.</span><span class="sxs-lookup"><span data-stu-id="4729f-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4729f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4729f-111">Requirements</span></span>  
 <span data-ttu-id="4729f-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4729f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4729f-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4729f-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4729f-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4729f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4729f-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4729f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4729f-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4729f-116">See also</span></span>

- [<span data-ttu-id="4729f-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="4729f-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
