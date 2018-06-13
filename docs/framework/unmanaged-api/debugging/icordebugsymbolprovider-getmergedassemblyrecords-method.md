---
title: Metodo ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 502e7e0b52bb147b5fe37dcc6e4f6d13d642b6f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417544"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="38b88-102">Metodo ICorDebugSymbolProvider::GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="38b88-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="38b88-103">Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.</span><span class="sxs-lookup"><span data-stu-id="38b88-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38b88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38b88-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38b88-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38b88-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="38b88-106">[in] Numero di record dei simboli richiesti.</span><span class="sxs-lookup"><span data-stu-id="38b88-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="38b88-107">[out] Puntatore al numero di record dei simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="38b88-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="38b88-108">Un puntatore a una matrice di [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="38b88-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38b88-109">Note</span><span class="sxs-lookup"><span data-stu-id="38b88-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38b88-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="38b88-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38b88-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38b88-111">Requirements</span></span>  
 <span data-ttu-id="38b88-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38b88-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38b88-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="38b88-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38b88-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="38b88-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38b88-115">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38b88-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b88-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38b88-116">See Also</span></span>  
 [<span data-ttu-id="38b88-117">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="38b88-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="38b88-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="38b88-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
