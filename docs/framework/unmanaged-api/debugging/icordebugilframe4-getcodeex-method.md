---
title: Metodo ICorDebugILFrame4::GetCodeEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.GetLocalVariableEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: aeda0e42-29ee-4ca8-9f21-ac4641677a62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24be4507e8ad6cde1e9c50582e352f0fc9b12ed3
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2018
ms.locfileid: "45677123"
---
# <a name="icordebugilframe4getcodeex-method"></a><span data-ttu-id="c7283-102">Metodo ICorDebugILFrame4::GetCodeEx</span><span class="sxs-lookup"><span data-stu-id="c7283-102">ICorDebugILFrame4::GetCodeEx Method</span></span>
<span data-ttu-id="c7283-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="c7283-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="c7283-104">Recupera un puntatore al codice eseguito da questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="c7283-104">Gets a pointer to the code that this stack frame is executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7283-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7283-105">Syntax</span></span>  
  
```cpp
HRESULT GetCodeEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7283-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7283-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="c7283-107">[in] Un' [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) membro di enumerazione che specifica se il linguaggio intermedio (IL) definito dalla richiesta ReJIT del profiler è inclusa nel frame.</span><span class="sxs-lookup"><span data-stu-id="c7283-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether the intermediate language (IL) defined by the profiler's ReJIT request is included in the frame.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="c7283-108">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugCode" che rappresenta il codice che lo stack frame corrente è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c7283-108">[out] A pointer to the address of an "ICorDebugCode" object that represents the code that this stack frame is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7283-109">Note</span><span class="sxs-lookup"><span data-stu-id="c7283-109">Remarks</span></span>  
 <span data-ttu-id="c7283-110">Questo metodo è simile al [ICorDebugFrame:: GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) metodo, ad eccezione del fatto che può accedere facoltativamente a codice definito dalla richiesta ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="c7283-110">This method is similar to the [ICorDebugFrame::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md) method, except that it optionally accesses code defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="c7283-111">Chiamare questo metodo con un `flags` valore del `ILCODE_ORIGINAL_IL` equivale alla chiamata [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); se il metodo è instrumentato, relativo linguaggio intermedio non sarà accessibile.</span><span class="sxs-lookup"><span data-stu-id="c7283-111">Calling this method with a `flags` value of `ILCODE_ORIGINAL_IL` is equivalent to calling [GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-getcode-method.md); if the method is instrumented, its IL will not be accessible.</span></span> <span data-ttu-id="c7283-112">`ILCODE_REJIT_IL` consente al debugger di accedere al linguaggio intermedio definito dalla richiesta ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="c7283-112">`ILCODE_REJIT_IL` allows the debugger to access the IL defined by the profiler's ReJIT request.</span></span> <span data-ttu-id="c7283-113">Se il linguaggio intermedio non è instrumentato, `ppCode` viene **null**, e il metodo restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="c7283-113">If the IL is not instrumented, `ppCode` is **null**, and the method returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7283-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7283-114">Requirements</span></span>  
 <span data-ttu-id="c7283-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7283-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7283-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7283-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7283-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7283-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7283-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7283-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7283-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7283-119">See Also</span></span>  
 [<span data-ttu-id="c7283-120">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="c7283-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="c7283-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="c7283-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c7283-122">ReJIT: Informazioni di Guida</span><span class="sxs-lookup"><span data-stu-id="c7283-122">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
