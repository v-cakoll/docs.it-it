---
title: 'Metodo metodo icordebugsymbolprovider:: GetMergedAssemblyRecords'
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
ms.openlocfilehash: 6faf8960c06488c8fff5a076aae375529e1d0260
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138870"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="3d442-102">Metodo metodo icordebugsymbolprovider:: GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="3d442-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="3d442-103">Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.</span><span class="sxs-lookup"><span data-stu-id="3d442-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d442-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d442-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d442-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3d442-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="3d442-106">[in] Numero di record dei simboli richiesti.</span><span class="sxs-lookup"><span data-stu-id="3d442-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="3d442-107">[out] Puntatore al numero di record dei simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="3d442-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="3d442-108">Puntatore a una matrice di oggetti [Metodo icordebugmergedassemblyrecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="3d442-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d442-109">Note</span><span class="sxs-lookup"><span data-stu-id="3d442-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d442-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3d442-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d442-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d442-111">Requirements</span></span>  
 <span data-ttu-id="3d442-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d442-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d442-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d442-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d442-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d442-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d442-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d442-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d442-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d442-116">See also</span></span>

- [<span data-ttu-id="3d442-117">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="3d442-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3d442-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3d442-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
