---
title: Metodo ICorDebugSymbolProvider2::GetFrameProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f74ed8cdd7448d7ebeaa98108e84b42e86f428b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="a7693-102">Metodo ICorDebugSymbolProvider2::GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="a7693-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="a7693-103">Restituisce l'indirizzo RVA (Relative Virtual Address) iniziale di un metodo e il frame padre in base a un indirizzo virtuale relativo al codice.</span><span class="sxs-lookup"><span data-stu-id="a7693-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7693-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7693-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a7693-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7693-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="a7693-106">[in] Indirizzo RVA (Relative Virtual Address)</span><span class="sxs-lookup"><span data-stu-id="a7693-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="a7693-107">[out] Puntatore all'indirizzo RVA (Relative Virtual Address) di avvio del metodo.</span><span class="sxs-lookup"><span data-stu-id="a7693-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="a7693-108">[out] Puntatore all'indirizzo RVA (Relative Virtual Address) di avvio del frame.</span><span class="sxs-lookup"><span data-stu-id="a7693-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7693-109">Note</span><span class="sxs-lookup"><span data-stu-id="a7693-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7693-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a7693-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7693-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7693-111">Requirements</span></span>  
 <span data-ttu-id="a7693-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7693-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7693-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a7693-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7693-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7693-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7693-115">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7693-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7693-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7693-116">See Also</span></span>  
 [<span data-ttu-id="a7693-117">Interfaccia ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="a7693-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="a7693-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a7693-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
