---
title: Metodo ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffcd6971a3229423f055765b0d64258a2dfa2aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477934"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="5e77e-102">Metodo ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="5e77e-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="5e77e-103">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="5e77e-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e77e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e77e-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e77e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e77e-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5e77e-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="5e77e-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5e77e-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="5e77e-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="5e77e-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="5e77e-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e77e-109">Note</span><span class="sxs-lookup"><span data-stu-id="5e77e-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e77e-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5e77e-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e77e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e77e-111">Requirements</span></span>  
 <span data-ttu-id="5e77e-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e77e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e77e-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e77e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e77e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e77e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e77e-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e77e-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e77e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e77e-116">See also</span></span>
- [<span data-ttu-id="5e77e-117">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="5e77e-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="5e77e-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5e77e-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
