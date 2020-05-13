---
title: Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 7e9aa01a3fa1c90b0ab4f85970c4eb294b9a4904
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379606"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="95e78-102">Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="95e78-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="95e78-103">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="95e78-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e78-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95e78-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e78-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95e78-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="95e78-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="95e78-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="95e78-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="95e78-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="95e78-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="95e78-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="95e78-109">out Puntatore a una matrice [Metodo icordebugvariablesymbol](icordebugvariablesymbol-interface.md) che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="95e78-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95e78-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="95e78-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95e78-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="95e78-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e78-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95e78-112">Requirements</span></span>  
 <span data-ttu-id="95e78-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e78-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e78-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95e78-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95e78-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95e78-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95e78-116">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e78-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e78-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95e78-117">See also</span></span>

- [<span data-ttu-id="95e78-118">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="95e78-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="95e78-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="95e78-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="95e78-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="95e78-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
