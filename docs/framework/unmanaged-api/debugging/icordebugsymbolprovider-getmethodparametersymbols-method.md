---
title: Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 051002b547aaa9745ae4efb516211123089c3128
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379604"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="4f0a1-102">Metodo ICorDebugSymbolProvider::GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="4f0a1-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="4f0a1-103">Ottiene i parametri del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="4f0a1-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f0a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4f0a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f0a1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4f0a1-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="4f0a1-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="4f0a1-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="4f0a1-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="4f0a1-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="4f0a1-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="4f0a1-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="4f0a1-109">out Puntatore a una matrice [Metodo icordebugvariablesymbol](icordebugvariablesymbol-interface.md) che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="4f0a1-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f0a1-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4f0a1-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4f0a1-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="4f0a1-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f0a1-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4f0a1-112">Requirements</span></span>  
 <span data-ttu-id="4f0a1-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f0a1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f0a1-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4f0a1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4f0a1-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f0a1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f0a1-116">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f0a1-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f0a1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4f0a1-117">See also</span></span>

- [<span data-ttu-id="4f0a1-118">Metodo GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="4f0a1-118">GetMethodLocalSymbols Method</span></span>](icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="4f0a1-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="4f0a1-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="4f0a1-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="4f0a1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
