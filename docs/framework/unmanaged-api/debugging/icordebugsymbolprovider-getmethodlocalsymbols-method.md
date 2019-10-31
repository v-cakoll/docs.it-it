---
title: 'Metodo metodo icordebugsymbolprovider:: GetMethodLocalSymbols'
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 6cd04ea7f83fb7ae96d9ffd1beba39530511ec25
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138896"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="8f1ea-102">Metodo metodo icordebugsymbolprovider:: GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="8f1ea-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="8f1ea-103">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="8f1ea-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f1ea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f1ea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f1ea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f1ea-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="8f1ea-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="8f1ea-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="8f1ea-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="8f1ea-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="8f1ea-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="8f1ea-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="8f1ea-109">out Puntatore a una matrice [Metodo icordebugvariablesymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="8f1ea-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f1ea-110">Note</span><span class="sxs-lookup"><span data-stu-id="8f1ea-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f1ea-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8f1ea-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f1ea-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f1ea-112">Requirements</span></span>  
 <span data-ttu-id="8f1ea-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f1ea-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f1ea-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f1ea-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f1ea-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f1ea-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f1ea-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f1ea-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f1ea-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f1ea-117">See also</span></span>

- [<span data-ttu-id="8f1ea-118">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="8f1ea-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="8f1ea-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="8f1ea-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="8f1ea-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8f1ea-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
