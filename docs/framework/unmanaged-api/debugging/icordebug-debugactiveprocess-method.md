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
ms.openlocfilehash: 2d71cebb77ed3ca586e857710667c0077f4f76ed
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793590"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="6fa1a-102">Metodo ICorDebug::DebugActiveProcess</span><span class="sxs-lookup"><span data-stu-id="6fa1a-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="6fa1a-103">Connette il debugger a un processo esistente.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa1a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6fa1a-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fa1a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6fa1a-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="6fa1a-106">in ID del processo a cui deve essere collegato il debugger.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="6fa1a-107">in Valore booleano impostato su `true` se il debugger deve comportarsi come debugger Win32 per il processo e inviare i callback non gestiti; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="6fa1a-108">out Puntatore all'indirizzo di un oggetto "ICorDebugProcess" che rappresenta il processo a cui è stato collegato il debugger.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fa1a-109">Note</span><span class="sxs-lookup"><span data-stu-id="6fa1a-109">Remarks</span></span>  
 <span data-ttu-id="6fa1a-110">Il debug di interoperabilità non è supportato in piattaforme Win9x e non x86, ad esempio piattaforme basate su IA-64 e AMD64.</span><span class="sxs-lookup"><span data-stu-id="6fa1a-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa1a-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="6fa1a-111">Requirements</span></span>  
 <span data-ttu-id="6fa1a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fa1a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa1a-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fa1a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fa1a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fa1a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fa1a-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa1a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fa1a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6fa1a-116">See also</span></span>

- [<span data-ttu-id="6fa1a-117">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="6fa1a-117">ICorDebug Interface</span></span>](icordebug-interface.md)
