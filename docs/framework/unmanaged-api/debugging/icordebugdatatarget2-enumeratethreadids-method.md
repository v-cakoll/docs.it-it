---
title: Metodo ICorDebugDataTarget2::EnumerateThreadIDs
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 4a65b76f384cdad68cba75af524dbe672c309624
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976486"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="7b242-102">Metodo ICorDebugDataTarget2::EnumerateThreadIDs</span><span class="sxs-lookup"><span data-stu-id="7b242-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="7b242-103">Restituisce un elenco di ID thread attivi.</span><span class="sxs-lookup"><span data-stu-id="7b242-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b242-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b242-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,
    [out] ULONG32 *pcThreadIds,
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b242-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b242-105">Parameters</span></span>  
 <span data-ttu-id="7b242-106">cThreadIDs</span><span class="sxs-lookup"><span data-stu-id="7b242-106">cThreadIDs</span></span>  
 <span data-ttu-id="7b242-107">[in] Il numero massimo di thread con ID che possono essere restituiti.</span><span class="sxs-lookup"><span data-stu-id="7b242-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="7b242-108">pcThreadIds</span><span class="sxs-lookup"><span data-stu-id="7b242-108">pcThreadIds</span></span>  
 <span data-ttu-id="7b242-109">[out] Un puntatore a `ULONG32` che indica il numero effettivo di ID thread scritti nella matrice `pThreadIds`.</span><span class="sxs-lookup"><span data-stu-id="7b242-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="7b242-110">pThreadIDs</span><span class="sxs-lookup"><span data-stu-id="7b242-110">pThreadIDs</span></span>  
 <span data-ttu-id="7b242-111">Una matrice di identificatori di thread.</span><span class="sxs-lookup"><span data-stu-id="7b242-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b242-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="7b242-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7b242-113">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7b242-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b242-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b242-114">Requirements</span></span>  
 <span data-ttu-id="7b242-115">**Piattaforme:** Vedere [requisiti di sistema](../../get-started/system-requirements.md). **Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="7b242-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b242-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b242-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b242-117">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b242-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b242-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b242-118">See also</span></span>

- [<span data-ttu-id="7b242-119">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="7b242-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="7b242-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7b242-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
