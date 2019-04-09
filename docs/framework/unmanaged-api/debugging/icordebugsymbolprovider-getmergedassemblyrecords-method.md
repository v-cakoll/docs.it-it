---
title: Metodo ICorDebugSymbolProvider::GetMergedAssemblyRecords
ms.date: 03/30/2017
ms.assetid: cc4c510d-550d-4941-af34-81987caf3425
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9003482860e554049c39ea9ffed4c52345bfeff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183209"
---
# <a name="icordebugsymbolprovidergetmergedassemblyrecords-method"></a><span data-ttu-id="7974e-102">Metodo ICorDebugSymbolProvider::GetMergedAssemblyRecords</span><span class="sxs-lookup"><span data-stu-id="7974e-102">ICorDebugSymbolProvider::GetMergedAssemblyRecords Method</span></span>
<span data-ttu-id="7974e-103">Ottiene i record dei simboli per tutti gli assembly sottoposti a merge.</span><span class="sxs-lookup"><span data-stu-id="7974e-103">Gets the symbol records for all the merged assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7974e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7974e-104">Syntax</span></span>  
  
```  
HRESULT GetMergedAssemblyRecords(  
   [in] ULONG32 cRequestedRecords,  
   [out] ULONG32 *pcFetchedRecords,  
   [out, size_is(cRequestedRecords), length_is(*pcFetchedRecords)] ICorDebugMergedAssemblyRecord *pRecords[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7974e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7974e-105">Parameters</span></span>  
 `cRequestedRecords`  
 <span data-ttu-id="7974e-106">[in] Numero di record dei simboli richiesti.</span><span class="sxs-lookup"><span data-stu-id="7974e-106">[in] The number of symbol records requested.</span></span>  
  
 `pcFetchedRecords`  
 <span data-ttu-id="7974e-107">[out] Puntatore al numero di record dei simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="7974e-107">[out] A pointer to the number of symbol records retrieved by the method.</span></span>  
  
 `pRecords`  
 <span data-ttu-id="7974e-108">Un puntatore a una matrice di [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) oggetti.</span><span class="sxs-lookup"><span data-stu-id="7974e-108">A pointer to an array of [ICorDebugMergedAssemblyRecord](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md) objects.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7974e-109">Note</span><span class="sxs-lookup"><span data-stu-id="7974e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7974e-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="7974e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7974e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7974e-111">Requirements</span></span>  
 <span data-ttu-id="7974e-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7974e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7974e-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7974e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7974e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7974e-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7974e-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="7974e-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7974e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7974e-116">See also</span></span>

- [<span data-ttu-id="7974e-117">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="7974e-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="7974e-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="7974e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
