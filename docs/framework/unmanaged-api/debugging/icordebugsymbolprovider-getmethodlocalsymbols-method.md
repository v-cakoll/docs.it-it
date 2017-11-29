---
title: Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3533157f25bda881fdbd0c77186c590d5a49f8c5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="19c23-102">Metodo ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="19c23-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="19c23-103">Ottiene i simboli locali del metodo da un indirizzo RVA (Relative Virtual Address) di tale metodo.</span><span class="sxs-lookup"><span data-stu-id="19c23-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19c23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="19c23-104">Syntax</span></span>  
  
```  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19c23-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="19c23-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="19c23-106">[in] Indirizzo RVA (Relative Virtual Address) nativo del metodo.</span><span class="sxs-lookup"><span data-stu-id="19c23-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="19c23-107">[in] Numero di simboli locali richiesti.</span><span class="sxs-lookup"><span data-stu-id="19c23-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="19c23-108">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="19c23-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="19c23-109">[out] Un puntatore a un [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) matrice che contiene i simboli locali del metodo.</span><span class="sxs-lookup"><span data-stu-id="19c23-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19c23-110">Note</span><span class="sxs-lookup"><span data-stu-id="19c23-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19c23-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="19c23-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19c23-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="19c23-112">Requirements</span></span>  
 <span data-ttu-id="19c23-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19c23-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19c23-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="19c23-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="19c23-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19c23-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19c23-116">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19c23-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19c23-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19c23-117">See Also</span></span>  
 [<span data-ttu-id="19c23-118">Metodo GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="19c23-118">GetMethodParameterSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodparametersymbols-method.md)  
 [<span data-ttu-id="19c23-119">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="19c23-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="19c23-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="19c23-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
