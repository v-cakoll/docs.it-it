---
title: Metodo ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7acf08262c73df00a96cfb5c244cdfc352e51ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080481"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="d4eb6-102">Metodo ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="d4eb6-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="d4eb6-103">Restituisce il percorso di un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="d4eb6-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4eb6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4eb6-104">Syntax</span></span>  
  
```  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4eb6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4eb6-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="d4eb6-106">[in] Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="d4eb6-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d4eb6-107">[in] Il numero di caratteri nel buffer che riceverà il percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="d4eb6-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d4eb6-108">[out] Un puntatore al numero di caratteri scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="d4eb6-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="d4eb6-109">[out] Il percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="d4eb6-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4eb6-110">Note</span><span class="sxs-lookup"><span data-stu-id="d4eb6-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4eb6-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d4eb6-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4eb6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4eb6-112">Requirements</span></span>  
 <span data-ttu-id="d4eb6-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4eb6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4eb6-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4eb6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4eb6-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4eb6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4eb6-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4eb6-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4eb6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d4eb6-117">See also</span></span>

- [<span data-ttu-id="d4eb6-118">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="d4eb6-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="d4eb6-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d4eb6-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
