---
title: Metodo ICorDebugSymbolProvider::GetObjectSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8817eb79c825a02ec5654ec340dedd6c77889a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="96b40-102">Metodo ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="96b40-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="96b40-103">Restituisce le dimensioni dell'oggetto per un oggetto in base alla relativa firma typespec.</span><span class="sxs-lookup"><span data-stu-id="96b40-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96b40-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96b40-104">Syntax</span></span>  
  
```  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96b40-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="96b40-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="96b40-106">[in] Numero di byte nella firma typespec.</span><span class="sxs-lookup"><span data-stu-id="96b40-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="96b40-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="96b40-107">typeSig</span></span>  
 <span data-ttu-id="96b40-108">[in] Firma typespec.</span><span class="sxs-lookup"><span data-stu-id="96b40-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="96b40-109">[out] Puntatore alla dimensione dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="96b40-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96b40-110">Note</span><span class="sxs-lookup"><span data-stu-id="96b40-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96b40-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="96b40-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96b40-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96b40-112">Requirements</span></span>  
 <span data-ttu-id="96b40-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96b40-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96b40-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="96b40-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="96b40-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="96b40-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="96b40-116">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96b40-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b40-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96b40-117">See Also</span></span>  
 [<span data-ttu-id="96b40-118">Interfaccia ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="96b40-118">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="96b40-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="96b40-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
