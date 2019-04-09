---
title: Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 98efd1446c88c3a6c004b5a3254c9db835a43804
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197373"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="535eb-102">Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="535eb-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="535eb-103">Ottiene i parametri del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="535eb-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="535eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="535eb-104">Syntax</span></span>  
  
```  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="535eb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="535eb-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="535eb-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="535eb-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="535eb-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="535eb-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="535eb-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="535eb-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="535eb-109">[out] Un puntatore a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matrice che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="535eb-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="535eb-110">Note</span><span class="sxs-lookup"><span data-stu-id="535eb-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="535eb-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="535eb-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="535eb-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="535eb-112">Requirements</span></span>  
 <span data-ttu-id="535eb-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="535eb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="535eb-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="535eb-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="535eb-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="535eb-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="535eb-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="535eb-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="535eb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="535eb-117">See also</span></span>

- [<span data-ttu-id="535eb-118">Metodo GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="535eb-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="535eb-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="535eb-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="535eb-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="535eb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
