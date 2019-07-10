---
title: Metodo ICorDebugSymbolProvider::GetStaticFieldSymbols
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9379a335130242918f6fe200eeda5e4c262fd020
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771293"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="6aba9-102">Metodo ICorDebugSymbolProvider::GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="6aba9-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="6aba9-103">Ottiene i simboli dei campi statici che corrispondono a una firma typespec.</span><span class="sxs-lookup"><span data-stu-id="6aba9-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6aba9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6aba9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6aba9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6aba9-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="6aba9-106">[in] Numero di byte nella matrice di `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="6aba9-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="6aba9-107">[in] Matrice di byte che contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="6aba9-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="6aba9-108">[in] Numero di simboli richiesti.</span><span class="sxs-lookup"><span data-stu-id="6aba9-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="6aba9-109">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="6aba9-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="6aba9-110">[out] Un puntatore a un [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) matrice che contiene i simboli dei campi statici richiesti.</span><span class="sxs-lookup"><span data-stu-id="6aba9-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6aba9-111">Note</span><span class="sxs-lookup"><span data-stu-id="6aba9-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aba9-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6aba9-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6aba9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6aba9-113">Requirements</span></span>  
 <span data-ttu-id="6aba9-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6aba9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6aba9-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6aba9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6aba9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6aba9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6aba9-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6aba9-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aba9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aba9-118">See also</span></span>

- [<span data-ttu-id="6aba9-119">Metodo GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="6aba9-119">GetInstanceFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="6aba9-120">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="6aba9-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6aba9-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6aba9-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
