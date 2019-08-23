---
title: Metodo ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2187a205b41388d191ad4f06db6d6caa86971e13
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913407"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="37eea-102">Metodo ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="37eea-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="37eea-103">Ottiene il nome del campo statico.</span><span class="sxs-lookup"><span data-stu-id="37eea-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37eea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37eea-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37eea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="37eea-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="37eea-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="37eea-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="37eea-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="37eea-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="37eea-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="37eea-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37eea-109">Note</span><span class="sxs-lookup"><span data-stu-id="37eea-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="37eea-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="37eea-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37eea-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37eea-111">Requirements</span></span>  
 <span data-ttu-id="37eea-112">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37eea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37eea-113">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="37eea-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37eea-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37eea-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37eea-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37eea-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37eea-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37eea-116">See also</span></span>

- [<span data-ttu-id="37eea-117">Interfaccia ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="37eea-117">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="37eea-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="37eea-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
