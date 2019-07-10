---
title: Metodo ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb7861e33a02b994c4c29569a811f4e2f3c44cec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762316"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="cc415-102">Metodo ICorDebugMergedAssemblyRecord::GetVersion</span><span class="sxs-lookup"><span data-stu-id="cc415-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="cc415-103">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="cc415-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc415-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc415-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc415-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc415-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="cc415-106">[out] Puntatore al numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="cc415-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="cc415-107">[out] Puntatore al numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="cc415-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="cc415-108">[out] Puntatore al numero di build.</span><span class="sxs-lookup"><span data-stu-id="cc415-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="cc415-109">[out] Puntatore al numero di revisione.</span><span class="sxs-lookup"><span data-stu-id="cc415-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc415-110">Note</span><span class="sxs-lookup"><span data-stu-id="cc415-110">Remarks</span></span>  
 <span data-ttu-id="cc415-111">Per informazioni sui numeri di versione degli assembly, vedere l'argomento relativo alla classe <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="cc415-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc415-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cc415-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc415-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc415-113">Requirements</span></span>  
 <span data-ttu-id="cc415-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc415-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc415-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc415-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc415-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc415-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc415-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc415-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc415-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc415-118">See also</span></span>

- [<span data-ttu-id="cc415-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="cc415-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="cc415-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cc415-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
