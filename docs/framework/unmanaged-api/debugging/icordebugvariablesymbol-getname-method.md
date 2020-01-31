---
title: Metodo ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: 172eea452442aa94ea010e2c434908ab8d040a93
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790916"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="775c8-102">Metodo ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="775c8-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="775c8-103">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="775c8-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="775c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="775c8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="775c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="775c8-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="775c8-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="775c8-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="775c8-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="775c8-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="775c8-108">Puntatore a una matrice di caratteri che contiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="775c8-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="775c8-109">Note</span><span class="sxs-lookup"><span data-stu-id="775c8-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="775c8-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="775c8-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="775c8-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="775c8-111">Requirements</span></span>  
 <span data-ttu-id="775c8-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="775c8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="775c8-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="775c8-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="775c8-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="775c8-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="775c8-115">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="775c8-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="775c8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="775c8-116">See also</span></span>

- [<span data-ttu-id="775c8-117">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="775c8-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="775c8-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="775c8-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
