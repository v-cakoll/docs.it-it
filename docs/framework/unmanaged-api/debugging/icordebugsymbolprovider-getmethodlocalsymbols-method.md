---
title: Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 41fc8e94ec8a5c8794674bebb32494bb3806e69d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791614"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="288b9-102">Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="288b9-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="288b9-103">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="288b9-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="288b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="288b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="288b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="288b9-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="288b9-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="288b9-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="288b9-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="288b9-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="288b9-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="288b9-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="288b9-109">out Puntatore a una matrice [Metodo icordebugvariablesymbol](icordebugvariablesymbol-interface.md) che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="288b9-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="288b9-110">Note</span><span class="sxs-lookup"><span data-stu-id="288b9-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="288b9-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="288b9-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="288b9-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="288b9-112">Requirements</span></span>  
 <span data-ttu-id="288b9-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="288b9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="288b9-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="288b9-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="288b9-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="288b9-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="288b9-116">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="288b9-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="288b9-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="288b9-117">See also</span></span>

- [<span data-ttu-id="288b9-118">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="288b9-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="288b9-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="288b9-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="288b9-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="288b9-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
