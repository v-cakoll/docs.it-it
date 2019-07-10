---
title: Metodo ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 348c51507006fecfe756cb17fd0d6242617577d7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750229"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="a8821-102">Metodo ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="a8821-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="a8821-103">Restituisce il percorso di un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="a8821-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8821-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8821-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8821-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8821-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="a8821-106">[in] Oggetto [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) valore che rappresenta l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="a8821-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a8821-107">[in] Il numero di caratteri nel buffer che riceverà il percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="a8821-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="a8821-108">[out] Un puntatore al numero di caratteri scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="a8821-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="a8821-109">[out] Il percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="a8821-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8821-110">Note</span><span class="sxs-lookup"><span data-stu-id="a8821-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8821-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="a8821-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8821-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8821-112">Requirements</span></span>  
 <span data-ttu-id="a8821-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8821-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8821-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a8821-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a8821-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8821-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8821-116">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8821-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8821-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8821-117">See also</span></span>

- [<span data-ttu-id="a8821-118">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="a8821-118">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a8821-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="a8821-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
