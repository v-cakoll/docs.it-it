---
title: Metodo ICorDebugVariableSymbol::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 747249c23089cbeba04c3a872823f01f2b334203
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="e8ccc-102">Metodo ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="e8ccc-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="e8ccc-103">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ccc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8ccc-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8ccc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8ccc-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e8ccc-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e8ccc-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e8ccc-108">Puntatore a una matrice di caratteri che contiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8ccc-109">Note</span><span class="sxs-lookup"><span data-stu-id="e8ccc-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8ccc-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e8ccc-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8ccc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8ccc-111">Requirements</span></span>  
 <span data-ttu-id="e8ccc-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8ccc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8ccc-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e8ccc-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e8ccc-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8ccc-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8ccc-115">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8ccc-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ccc-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8ccc-116">See Also</span></span>  
 [<span data-ttu-id="e8ccc-117">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="e8ccc-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="e8ccc-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e8ccc-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
