---
title: ICorProfilerInfo9::GetILToNativeMapping3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetILToNativeMapping3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 5c49d75432980d2f3af77ee040bc6eb20886b027
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861671"
---
# <a name="icorprofilerinfo9getiltonativemapping3-method"></a><span data-ttu-id="1c70c-102">Metodo ICorProfilerInfo9:: GetILToNativeMapping3</span><span class="sxs-lookup"><span data-stu-id="1c70c-102">ICorProfilerInfo9::GetILToNativeMapping3 Method</span></span>

<span data-ttu-id="1c70c-103">Dato l'indirizzo iniziale del codice nativo, restituisce le informazioni di mapping native a per la versione compilato JIT del codice.</span><span class="sxs-lookup"><span data-stu-id="1c70c-103">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span>

## <a name="syntax"></a><span data-ttu-id="1c70c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c70c-104">Syntax</span></span>

```cpp
HRESULT GetILToNativeMapping3( [in]  UINT_PTR pNativeCodeStartAddress,
                               [in]  ULONG32 cMap,
                               [out] ULONG32 *pcMap,
                               [out] COR_DEBUG_IL_TO_NATIVE_MAP map[]);
```

## <a name="parameters"></a><span data-ttu-id="1c70c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c70c-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="1c70c-106">\[in] puntatore all'inizio di una funzione nativa.</span><span class="sxs-lookup"><span data-stu-id="1c70c-106">\[in] A pointer to the start of a native function.</span></span>

- `cMap`

  <span data-ttu-id="1c70c-107">\[in] dimensione massima della matrice di `map`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-107">\[in] The maximum size of the `map` array.</span></span>

- `pcMap`

  <span data-ttu-id="1c70c-108">\[out] numero totale di strutture COR_DEBUG_IL_TO_NATIVE_MAP disponibili.</span><span class="sxs-lookup"><span data-stu-id="1c70c-108">\[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>

- `map`

  <span data-ttu-id="1c70c-109">\[out] matrice di strutture [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) , ognuna delle quali specifica gli offset.</span><span class="sxs-lookup"><span data-stu-id="1c70c-109">\[out] An array of [COR_DEBUG_IL_TO_NATIVE_MAP](../debugging/cor-debug-il-to-native-map-structure.md) structures, each of which specifies the offsets.</span></span> <span data-ttu-id="1c70c-110">Dopo il completamento del metodo `GetILToNativeMapping3`, `map` conterrà alcune o tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="1c70c-110">After the `GetILToNativeMapping3` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>

## <a name="remarks"></a><span data-ttu-id="1c70c-111">Note</span><span class="sxs-lookup"><span data-stu-id="1c70c-111">Remarks</span></span>

<span data-ttu-id="1c70c-112">Quando è abilitata la compilazione a più livelli, un metodo può avere più di un corpo del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="1c70c-112">When tiered compilation is enabled, a method may have more than one native code body.</span></span> <span data-ttu-id="1c70c-113">[ICorProfilerInfo9:: GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) restituirà gli indirizzi iniziali per tutti i corpi del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="1c70c-113">[ICorProfilerInfo9::GetNativeCodeStartAddresses](icorprofilerinfo9-getnativecodestartaddresses-method.md) will return the start addresses for all of the native code bodies.</span></span>

## <a name="requirements"></a><span data-ttu-id="1c70c-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="1c70c-114">Requirements</span></span>

<span data-ttu-id="1c70c-115">**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="1c70c-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="1c70c-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1c70c-116">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="1c70c-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c70c-117">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="1c70c-118">**Versioni .NET Framework:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c70c-118">**.NET Framework Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1c70c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c70c-119">See also</span></span>

- [<span data-ttu-id="1c70c-120">Interfaccia ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="1c70c-120">ICorProfilerInfo9 Interface</span></span>](icorprofilerinfo9-interface.md)
