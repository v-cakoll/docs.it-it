---
title: Metodo ICorDebugSymbolProvider::GetInstanceFieldSymbols
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 9c55ce4d36681e173047cfb51515a74899c5a9fe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791639"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="a1f61-102">Metodo ICorDebugSymbolProvider::GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="a1f61-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="a1f61-103">Ottiene i simboli dei campi di istanza che corrispondono a una firma typespec.</span><span class="sxs-lookup"><span data-stu-id="a1f61-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1f61-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1f61-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1f61-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1f61-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="a1f61-106">[in] Numero di byte nella matrice di `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="a1f61-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="a1f61-107">[in] Matrice di byte che contiene la firma `typespec`.</span><span class="sxs-lookup"><span data-stu-id="a1f61-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="a1f61-108">[in] Numero di simboli richiesti.</span><span class="sxs-lookup"><span data-stu-id="a1f61-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="a1f61-109">[out] Puntatore al numero di simboli recuperati dal metodo.</span><span class="sxs-lookup"><span data-stu-id="a1f61-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="a1f61-110">out Puntatore a una matrice [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) che contiene i simboli dei campi di istanza richiesti.</span><span class="sxs-lookup"><span data-stu-id="a1f61-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1f61-111">Note</span><span class="sxs-lookup"><span data-stu-id="a1f61-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a1f61-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a1f61-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1f61-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="a1f61-113">Requirements</span></span>  
 <span data-ttu-id="a1f61-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1f61-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1f61-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1f61-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1f61-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1f61-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1f61-117">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1f61-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f61-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1f61-118">See also</span></span>

- [<span data-ttu-id="a1f61-119">Metodo GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="a1f61-119">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="a1f61-120">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="a1f61-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="a1f61-121">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a1f61-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
