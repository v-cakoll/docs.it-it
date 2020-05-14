---
title: Metodo ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: ea414a39e140c74df736764dbbb1bb3934bda78f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397122"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="e3d97-102">Metodo ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="e3d97-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="e3d97-103">Ottiene il nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="e3d97-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d97-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e3d97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3d97-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e3d97-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e3d97-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e3d97-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e3d97-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="e3d97-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e3d97-108">Puntatore a una matrice di caratteri che contiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="e3d97-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3d97-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="e3d97-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3d97-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e3d97-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3d97-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e3d97-111">Requirements</span></span>  
 <span data-ttu-id="e3d97-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3d97-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3d97-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3d97-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3d97-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3d97-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3d97-115">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3d97-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d97-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e3d97-116">See also</span></span>

- [<span data-ttu-id="e3d97-117">Interfaccia ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="e3d97-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="e3d97-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e3d97-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
