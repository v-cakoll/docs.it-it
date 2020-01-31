---
title: Metodo ICorDebugDataTarget2::GetImageLocation
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: ba1cc8c91c53547c6ed4025ee67a69e253f3596d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783577"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="22193-102">Metodo ICorDebugDataTarget2::GetImageLocation</span><span class="sxs-lookup"><span data-stu-id="22193-102">ICorDebugDataTarget2::GetImageLocation Method</span></span>
<span data-ttu-id="22193-103">Restituisce il percorso di un modulo dall'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="22193-103">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22193-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22193-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22193-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="22193-105">Parameters</span></span>  
 `baseAddress`  
 <span data-ttu-id="22193-106">in Valore [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) che rappresenta l'indirizzo di base del modulo.</span><span class="sxs-lookup"><span data-stu-id="22193-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="22193-107">[in] Il numero di caratteri nel buffer che riceverà il percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="22193-107">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="22193-108">[out] Un puntatore al numero di caratteri scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="22193-108">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="22193-109">[out] Il percorso del modulo.</span><span class="sxs-lookup"><span data-stu-id="22193-109">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22193-110">Note</span><span class="sxs-lookup"><span data-stu-id="22193-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="22193-111">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="22193-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22193-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="22193-112">Requirements</span></span>  
 <span data-ttu-id="22193-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22193-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22193-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22193-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22193-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22193-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22193-116">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22193-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22193-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22193-117">See also</span></span>

- [<span data-ttu-id="22193-118">Interfaccia ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="22193-118">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="22193-119">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="22193-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
