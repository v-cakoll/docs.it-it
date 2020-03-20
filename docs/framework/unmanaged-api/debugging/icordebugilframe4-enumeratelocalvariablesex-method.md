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
ms.openlocfilehash: 341a86f4c1c8367f979e193a6284bf89f1b03ca0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178798"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="97a78-102">Metodo ICorDebugILFrame4::EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="97a78-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="97a78-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="97a78-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="97a78-104">Ottiene un enumeratore per le variabili locali nel frame e, facoltativamente, include le variabili aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="97a78-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a78-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97a78-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97a78-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="97a78-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="97a78-107">[in] Un membro di enumerazione [ILCodeKind](ilcodekind-enumeration.md) che specifica se le variabili aggiunte nella strumentazione ReJIT del profiler sono incluse nel frame.</span><span class="sxs-lookup"><span data-stu-id="97a78-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="97a78-108">[fuori] Puntatore all'indirizzo di un oggetto "ICorDebugValueEnum" che è l'enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="97a78-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97a78-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="97a78-109">Remarks</span></span>  
 <span data-ttu-id="97a78-110">Questo metodo è simile al metodo [EnumerateLocalVariables,](icordebugilframe-enumeratelocalvariables-method.md) con la differenza che accede facoltativamente alle variabili aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="97a78-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="97a78-111">L'impostazione `flags` su `ILCODE_ORIGINAL_IL` equivale alla chiamata di [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="97a78-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="97a78-112">Impostare `flags` su `ILCODE_REJIT_IL` consente al debugger di accedere alle variabili locali aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="97a78-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="97a78-113">Se il linguaggio intermedio (IL) non è instrumentato, l'enumerazione è vuota e il metodo restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="97a78-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="97a78-114">L'enumeratore potrebbe non includere tutte le variabili locali nel metodo in esecuzione, in quanto alcune potrebbero essere inattive.</span><span class="sxs-lookup"><span data-stu-id="97a78-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97a78-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97a78-115">Requirements</span></span>  
 <span data-ttu-id="97a78-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97a78-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97a78-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97a78-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97a78-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97a78-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97a78-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97a78-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a78-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97a78-120">See also</span></span>

- [<span data-ttu-id="97a78-121">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="97a78-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="97a78-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="97a78-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="97a78-123">ReJIT: una guida alle procedure</span><span class="sxs-lookup"><span data-stu-id="97a78-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
