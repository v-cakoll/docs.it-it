---
title: Metodo ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d23bf14fbb3d75534ac2d4a43eca0fbf3e994ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59161395"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="a4c02-102">Metodo ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="a4c02-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="a4c02-103">Ottiene il nome del campo di istanza.</span><span class="sxs-lookup"><span data-stu-id="a4c02-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4c02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4c02-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4c02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4c02-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="a4c02-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a4c02-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a4c02-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a4c02-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a4c02-108">[out] Matrice di caratteri contenente il nome restituito.</span><span class="sxs-lookup"><span data-stu-id="a4c02-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4c02-109">Note</span><span class="sxs-lookup"><span data-stu-id="a4c02-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4c02-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a4c02-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4c02-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4c02-111">Requirements</span></span>  
 <span data-ttu-id="a4c02-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4c02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4c02-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4c02-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4c02-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4c02-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a4c02-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="a4c02-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4c02-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4c02-116">See also</span></span>

- [<span data-ttu-id="a4c02-117">Interfaccia ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="a4c02-117">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="a4c02-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a4c02-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
