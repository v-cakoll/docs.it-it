---
title: Metodo ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 01281e09533ba7196d3fa3e57c463636cfb0dd77
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760831"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="85fd7-102">Metodo ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="85fd7-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="85fd7-103">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="85fd7-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85fd7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85fd7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85fd7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="85fd7-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="85fd7-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="85fd7-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="85fd7-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="85fd7-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="85fd7-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="85fd7-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85fd7-109">Note</span><span class="sxs-lookup"><span data-stu-id="85fd7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85fd7-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="85fd7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85fd7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85fd7-111">Requirements</span></span>  
 <span data-ttu-id="85fd7-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85fd7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85fd7-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85fd7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85fd7-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85fd7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85fd7-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85fd7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85fd7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85fd7-116">See also</span></span>

- [<span data-ttu-id="85fd7-117">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="85fd7-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="85fd7-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="85fd7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
