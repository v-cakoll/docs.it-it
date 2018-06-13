---
title: Metodo ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 095c84a5cb448803bbfa45e0fad8a494343ca7f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422318"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="a16c1-102">Metodo ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="a16c1-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="a16c1-103">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="a16c1-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a16c1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a16c1-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a16c1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a16c1-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a16c1-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a16c1-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a16c1-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a16c1-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a16c1-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="a16c1-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a16c1-109">Note</span><span class="sxs-lookup"><span data-stu-id="a16c1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a16c1-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a16c1-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a16c1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a16c1-111">Requirements</span></span>  
 <span data-ttu-id="a16c1-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a16c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a16c1-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a16c1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a16c1-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="a16c1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a16c1-115">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a16c1-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a16c1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a16c1-116">See Also</span></span>  
 [<span data-ttu-id="a16c1-117">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a16c1-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="a16c1-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a16c1-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
