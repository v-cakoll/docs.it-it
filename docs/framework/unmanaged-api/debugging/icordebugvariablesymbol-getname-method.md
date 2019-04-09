---
title: Metodo ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170170"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="ad483-102">Metodo ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="ad483-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="ad483-103">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="ad483-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad483-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ad483-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad483-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ad483-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="ad483-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="ad483-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="ad483-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="ad483-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="ad483-108">Puntatore a una matrice di caratteri che contiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="ad483-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad483-109">Note</span><span class="sxs-lookup"><span data-stu-id="ad483-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad483-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ad483-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad483-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ad483-111">Requirements</span></span>  
 <span data-ttu-id="ad483-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad483-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad483-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad483-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad483-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad483-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ad483-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ad483-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad483-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad483-116">See also</span></span>

- [<span data-ttu-id="ad483-117">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="ad483-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="ad483-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ad483-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
