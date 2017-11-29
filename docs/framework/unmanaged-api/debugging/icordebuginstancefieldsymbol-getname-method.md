---
title: Metodo ICorDebugInstanceFieldSymbol::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cfd56230d391c44343bdb3f575247b07af1e98ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="6255a-102">Metodo ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="6255a-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="6255a-103">Ottiene il nome del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="6255a-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6255a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6255a-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6255a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6255a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6255a-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="6255a-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6255a-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="6255a-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="6255a-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="6255a-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6255a-109">Note</span><span class="sxs-lookup"><span data-stu-id="6255a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6255a-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6255a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6255a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6255a-111">Requirements</span></span>  
 <span data-ttu-id="6255a-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6255a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6255a-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6255a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6255a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6255a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6255a-115">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6255a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6255a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6255a-116">See Also</span></span>  
 [<span data-ttu-id="6255a-117">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="6255a-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 [<span data-ttu-id="6255a-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6255a-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
