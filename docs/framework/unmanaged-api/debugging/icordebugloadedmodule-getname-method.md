---
title: Metodo ICorDebugLoadedModule::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 605bbaf1e98983af222a99bada1ca9451fe9337e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="30ca2-102">Metodo ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="30ca2-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="30ca2-103">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="30ca2-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30ca2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30ca2-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30ca2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30ca2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="30ca2-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="30ca2-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="30ca2-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="30ca2-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="30ca2-108">[out] Matrice di caratteri che contiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="30ca2-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30ca2-109">Note</span><span class="sxs-lookup"><span data-stu-id="30ca2-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30ca2-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="30ca2-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30ca2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30ca2-111">Requirements</span></span>  
 <span data-ttu-id="30ca2-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30ca2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30ca2-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="30ca2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30ca2-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30ca2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30ca2-115">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30ca2-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30ca2-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30ca2-116">See Also</span></span>  
 [<span data-ttu-id="30ca2-117">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="30ca2-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="30ca2-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="30ca2-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
