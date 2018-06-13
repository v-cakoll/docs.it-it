---
title: Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c590944c321050c9ecca330a2961a2a7b7f31e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420014"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="42805-102">Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="42805-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="42805-103">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="42805-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42805-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42805-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="42805-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="42805-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="42805-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="42805-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="42805-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="42805-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="42805-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="42805-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="42805-109">[out] Un puntatore a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matrice che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="42805-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="42805-110">Note</span><span class="sxs-lookup"><span data-stu-id="42805-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42805-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="42805-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42805-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42805-112">Requirements</span></span>  
 <span data-ttu-id="42805-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42805-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42805-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="42805-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="42805-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="42805-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="42805-116">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42805-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42805-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42805-117">See Also</span></span>  
 [<span data-ttu-id="42805-118">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="42805-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)  
 [<span data-ttu-id="42805-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="42805-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="42805-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="42805-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
