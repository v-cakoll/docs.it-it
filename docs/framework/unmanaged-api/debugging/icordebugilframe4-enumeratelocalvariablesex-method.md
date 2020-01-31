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
ms.openlocfilehash: afeec3df03fc2b122ca8deb8123b79314b5e3837
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782426"
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a><span data-ttu-id="49a74-102">Metodo ICorDebugILFrame4::EnumerateLocalVariablesEx</span><span class="sxs-lookup"><span data-stu-id="49a74-102">ICorDebugILFrame4::EnumerateLocalVariablesEx Method</span></span>
<span data-ttu-id="49a74-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="49a74-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="49a74-104">Ottiene un enumeratore per le variabili locali nel frame e, facoltativamente, include le variabili aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="49a74-104">Gets an enumerator for the local variable in the frame, and optionally includes variables added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49a74-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49a74-105">Syntax</span></span>  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49a74-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="49a74-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="49a74-107">in Membro di enumerazione [ILCodeKind](ilcodekind-enumeration.md) che specifica se le variabili aggiunte nella strumentazione ReJIT del profiler sono incluse nel frame.</span><span class="sxs-lookup"><span data-stu-id="49a74-107">[in] An [ILCodeKind](ilcodekind-enumeration.md) enumeration member that specifies whether variables added in profiler ReJIT instrumentation are included in the frame.</span></span>  
  
 `ppValueEnum`  
 <span data-ttu-id="49a74-108">out Puntatore all'indirizzo di un oggetto "ICorDebugValueEnum" che rappresenta l'enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="49a74-108">[out] A pointer to the address of an "ICorDebugValueEnum" object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49a74-109">Note</span><span class="sxs-lookup"><span data-stu-id="49a74-109">Remarks</span></span>  
 <span data-ttu-id="49a74-110">Questo metodo è simile al metodo [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) , ad eccezione del fatto che accede facoltativamente alle variabili aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="49a74-110">This method is similar to the [EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md) method, except that it optionally accesses variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="49a74-111">L'impostazione di `flags` su `ILCODE_ORIGINAL_IL` equivale alla chiamata di [ICorDebugILFrame:: EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span><span class="sxs-lookup"><span data-stu-id="49a74-111">Setting `flags` to `ILCODE_ORIGINAL_IL` is equivalent to calling [ICorDebugILFrame::EnumerateLocalVariables](icordebugilframe-enumeratelocalvariables-method.md).</span></span> <span data-ttu-id="49a74-112">Impostare `flags` su `ILCODE_REJIT_IL` consente al debugger di accedere alle variabili locali aggiunte nella strumentazione ReJIT del profiler.</span><span class="sxs-lookup"><span data-stu-id="49a74-112">Setting `flags` to `ILCODE_REJIT_IL` allows the debugger to access the local variables added in profiler ReJIT instrumentation.</span></span> <span data-ttu-id="49a74-113">Se il linguaggio intermedio (IL) non è instrumentato, l'enumerazione è vuota e il metodo restituisce `S_OK`.</span><span class="sxs-lookup"><span data-stu-id="49a74-113">If the intermediate language (IL) is not instrumented, the enumeration is empty and the method returns `S_OK`.</span></span>  
  
 <span data-ttu-id="49a74-114">L'enumeratore potrebbe non includere tutte le variabili locali nel metodo in esecuzione, in quanto alcune potrebbero essere inattive.</span><span class="sxs-lookup"><span data-stu-id="49a74-114">The enumerator may not include all of the local variables in the running method, since some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49a74-115">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="49a74-115">Requirements</span></span>  
 <span data-ttu-id="49a74-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49a74-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49a74-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49a74-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49a74-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49a74-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49a74-119">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49a74-119">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49a74-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49a74-120">See also</span></span>

- [<span data-ttu-id="49a74-121">Interfaccia ICorDebugILFrame4</span><span class="sxs-lookup"><span data-stu-id="49a74-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="49a74-122">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="49a74-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="49a74-123">ReJIT: Guida alle procedure</span><span class="sxs-lookup"><span data-stu-id="49a74-123">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
