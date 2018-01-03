---
title: Metodo ICorDebugMergedAssemblyRecord::GetVersion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6a3865a82efec63aa85f4a0eee286bf8b79bd00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="43190-102">Metodo ICorDebugMergedAssemblyRecord::GetVersion</span><span class="sxs-lookup"><span data-stu-id="43190-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="43190-103">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="43190-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43190-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43190-104">Syntax</span></span>  
  
```  
HRESULT GetVersion(  
   [out] USHORT *pMajor,   
   [out] USHORT *pMinor,   
   [out] USHORT *pBuild,   
   [out] USHORT *pRevision  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43190-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43190-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="43190-106">[out] Puntatore al numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="43190-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="43190-107">[out] Puntatore al numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="43190-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="43190-108">[out] Puntatore al numero di build.</span><span class="sxs-lookup"><span data-stu-id="43190-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="43190-109">[out] Puntatore al numero di revisione.</span><span class="sxs-lookup"><span data-stu-id="43190-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43190-110">Note</span><span class="sxs-lookup"><span data-stu-id="43190-110">Remarks</span></span>  
 <span data-ttu-id="43190-111">Per informazioni sui numeri di versione degli assembly, vedere l'argomento relativo alla classe <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="43190-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43190-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="43190-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43190-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43190-113">Requirements</span></span>  
 <span data-ttu-id="43190-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43190-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43190-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="43190-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43190-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43190-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43190-117">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43190-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43190-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43190-118">See Also</span></span>  
 [<span data-ttu-id="43190-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="43190-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 [<span data-ttu-id="43190-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="43190-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
