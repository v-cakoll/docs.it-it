---
title: Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99f76bd19ef274c3d4207fdd071914b736314a3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148577"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="3473b-102">Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="3473b-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="3473b-103">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="3473b-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3473b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3473b-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3473b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3473b-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="3473b-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="3473b-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="3473b-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="3473b-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3473b-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="3473b-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="3473b-109">[out] Un puntatore a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matrice che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="3473b-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3473b-110">Note</span><span class="sxs-lookup"><span data-stu-id="3473b-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3473b-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3473b-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3473b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3473b-112">Requirements</span></span>  
 <span data-ttu-id="3473b-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3473b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3473b-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3473b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3473b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3473b-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3473b-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3473b-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3473b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3473b-117">See also</span></span>

- [<span data-ttu-id="3473b-118">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="3473b-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="3473b-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="3473b-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="3473b-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3473b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
