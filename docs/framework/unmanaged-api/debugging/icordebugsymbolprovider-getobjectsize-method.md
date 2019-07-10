---
title: Metodo ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b90e2a097e6dfd35b6237808a7b8b47937774b0d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771327"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="6b33a-102">Metodo ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="6b33a-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="6b33a-103">Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.</span><span class="sxs-lookup"><span data-stu-id="6b33a-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b33a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6b33a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b33a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6b33a-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="6b33a-106">[in] Numero di byte nella firma typespec.</span><span class="sxs-lookup"><span data-stu-id="6b33a-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="6b33a-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="6b33a-107">typeSig</span></span>  
 <span data-ttu-id="6b33a-108">[in] Firma typespec.</span><span class="sxs-lookup"><span data-stu-id="6b33a-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="6b33a-109">[out] Puntatore alla dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6b33a-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b33a-110">Note</span><span class="sxs-lookup"><span data-stu-id="6b33a-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b33a-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6b33a-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b33a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6b33a-112">Requirements</span></span>  
 <span data-ttu-id="6b33a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b33a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b33a-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b33a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b33a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b33a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b33a-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b33a-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b33a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b33a-117">See also</span></span>

- [<span data-ttu-id="6b33a-118">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="6b33a-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6b33a-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6b33a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
