---
title: Metodo ICorDebugILFrame4::EnumerateLocalVariablesEx
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49d2a0955f9ef0c54a8953971ce3671ce16d3b85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418929"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="62001-102">Metodo ICorDebugILFrame4::EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="62001-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="62001-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="62001-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="62001-104">Ottiene un enumeratore per le variabili locali nel frame e, facoltativamente, include le variabili aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="62001-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62001-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="62001-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="62001-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="62001-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="62001-107">[in] Un [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) membro di enumerazione che specifica se le variabili aggiunte nella strumentazione ReJIT del profiler vengono incluse nel frame.</span><span class="sxs-lookup"><span data-stu-id="62001-107">[in] An [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="62001-108">[out] Un puntatore all'indirizzo di un oggetto "ICorDebugValueEnum" che è l'enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="62001-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62001-109">Note</span><span class="sxs-lookup"><span data-stu-id="62001-109">Remarks</span></span>  
 <span data-ttu-id="62001-110">Questo metodo è simile al [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) metodo, ad eccezione del fatto che può accedere facoltativamente alle variabili aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="62001-110">This method is similar to the [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="62001-111">Impostazione `flags` a `ILCODE_ORIGINAL_IL` è equivalente alla chiamata [ICorDebugILFrame:: EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="62001-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="62001-112">Impostare `flags` su `ILCODE_REJIT_IL` consente al debugger di accedere alle variabili locali aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="62001-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="62001-113">Se il linguaggio intermedio (IL) non è instrumentato, l'enumerazione è vuota e il metodo restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="62001-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="62001-114">L'enumeratore potrebbe non includere tutte le variabili locali nel metodo in esecuzione, in quanto alcune potrebbero essere inattive.</span><span class="sxs-lookup"><span data-stu-id="62001-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62001-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="62001-115">Requirements</span></span>  
 <span data-ttu-id="62001-116">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62001-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62001-117">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="62001-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62001-118">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="62001-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62001-119">**Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62001-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62001-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62001-120">See Also</span></span>  
 [<span data-ttu-id="62001-121">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="62001-121">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [<span data-ttu-id="62001-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="62001-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="62001-123">ReJIT: Una Guida dettagliata</span><span class="sxs-lookup"><span data-stu-id="62001-123">ReJIT: A How-To Guide</span></span>](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
