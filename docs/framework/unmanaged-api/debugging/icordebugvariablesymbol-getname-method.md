---
title: Metodo ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170170"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="1921b-102">Metodo ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="1921b-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="1921b-103">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="1921b-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1921b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1921b-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1921b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1921b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="1921b-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="1921b-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="1921b-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="1921b-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="1921b-108">Puntatore a una matrice di caratteri che contiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="1921b-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1921b-109">Note</span><span class="sxs-lookup"><span data-stu-id="1921b-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1921b-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1921b-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1921b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1921b-111">Requirements</span></span>  
 <span data-ttu-id="1921b-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1921b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1921b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1921b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1921b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1921b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1921b-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1921b-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1921b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1921b-116">See also</span></span>

- [<span data-ttu-id="1921b-117">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="1921b-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="1921b-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1921b-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
