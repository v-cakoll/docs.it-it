---
title: Metodo ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f514acbd772c9d33ec4372cfaccb778d6bb41eb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993629"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="90db7-102">Metodo ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="90db7-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="90db7-103">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="90db7-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90db7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90db7-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90db7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="90db7-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="90db7-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="90db7-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="90db7-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="90db7-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="90db7-108">Puntatore a una matrice di caratteri che contiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="90db7-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90db7-109">Note</span><span class="sxs-lookup"><span data-stu-id="90db7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="90db7-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="90db7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90db7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90db7-111">Requirements</span></span>  
 <span data-ttu-id="90db7-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90db7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90db7-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90db7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90db7-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90db7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90db7-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90db7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90db7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90db7-116">See also</span></span>

- [<span data-ttu-id="90db7-117">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="90db7-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="90db7-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="90db7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
