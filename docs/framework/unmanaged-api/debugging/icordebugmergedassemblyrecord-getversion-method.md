---
title: Metodo ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 5dc9995e88086da854d2e9382cef81b229ff9dc9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178681"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="e1379-102">Metodo ICorDebugMergedAssemblyRecord::GetVersion</span><span class="sxs-lookup"><span data-stu-id="e1379-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="e1379-103">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="e1379-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1379-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1379-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1379-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1379-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="e1379-106">[out] Puntatore al numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="e1379-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="e1379-107">[out] Puntatore al numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="e1379-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="e1379-108">[out] Puntatore al numero di build.</span><span class="sxs-lookup"><span data-stu-id="e1379-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="e1379-109">[out] Puntatore al numero di revisione.</span><span class="sxs-lookup"><span data-stu-id="e1379-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1379-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e1379-110">Remarks</span></span>  
 <span data-ttu-id="e1379-111">Per informazioni sui numeri di versione degli assembly, vedere l'argomento relativo alla classe <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="e1379-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1379-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e1379-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1379-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1379-113">Requirements</span></span>  
 <span data-ttu-id="e1379-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1379-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1379-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1379-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1379-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1379-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1379-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1379-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1379-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1379-118">See also</span></span>

- [<span data-ttu-id="e1379-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="e1379-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="e1379-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e1379-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
