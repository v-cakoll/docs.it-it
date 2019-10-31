---
title: 'Metodo metodo icordebugsymbolprovider:: GetObjectSize'
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: a5c0fe6d73302abbfabe2272cc878d6fd8f5fdec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138812"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="e2df6-102">Metodo metodo icordebugsymbolprovider:: GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="e2df6-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="e2df6-103">Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.</span><span class="sxs-lookup"><span data-stu-id="e2df6-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2df6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2df6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2df6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2df6-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="e2df6-106">[in] Numero di byte nella firma typespec.</span><span class="sxs-lookup"><span data-stu-id="e2df6-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="e2df6-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="e2df6-107">typeSig</span></span>  
 <span data-ttu-id="e2df6-108">[in] Firma typespec.</span><span class="sxs-lookup"><span data-stu-id="e2df6-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="e2df6-109">[out] Puntatore alla dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="e2df6-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2df6-110">Note</span><span class="sxs-lookup"><span data-stu-id="e2df6-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e2df6-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e2df6-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2df6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2df6-112">Requirements</span></span>  
 <span data-ttu-id="e2df6-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2df6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2df6-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2df6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2df6-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2df6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2df6-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2df6-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2df6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2df6-117">See also</span></span>

- [<span data-ttu-id="e2df6-118">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="e2df6-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e2df6-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e2df6-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
