---
title: Metodo ICorDebugMergedAssemblyRecord::GetVersion
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: cad71080c86e92beb318722db86011b09ce02e91
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207631"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="ec8f5-102">Metodo ICorDebugMergedAssemblyRecord::GetVersion</span><span class="sxs-lookup"><span data-stu-id="ec8f5-102">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>
<span data-ttu-id="ec8f5-103">Ottiene le informazioni sulla versione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="ec8f5-103">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec8f5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec8f5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec8f5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec8f5-105">Parameters</span></span>  
 `pMajor`  
 <span data-ttu-id="ec8f5-106">[out] Puntatore al numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="ec8f5-106">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="ec8f5-107">[out] Puntatore al numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="ec8f5-107">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="ec8f5-108">[out] Puntatore al numero di build.</span><span class="sxs-lookup"><span data-stu-id="ec8f5-108">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="ec8f5-109">[out] Puntatore al numero di revisione.</span><span class="sxs-lookup"><span data-stu-id="ec8f5-109">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec8f5-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ec8f5-110">Remarks</span></span>  
 <span data-ttu-id="ec8f5-111">Per informazioni sui numeri di versione degli assembly, vedere l'argomento relativo alla classe <xref:System.Version>.</span><span class="sxs-lookup"><span data-stu-id="ec8f5-111">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ec8f5-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="ec8f5-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec8f5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec8f5-113">Requirements</span></span>  
 <span data-ttu-id="ec8f5-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec8f5-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec8f5-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec8f5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec8f5-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec8f5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec8f5-117">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec8f5-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec8f5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec8f5-118">See also</span></span>

- [<span data-ttu-id="ec8f5-119">Interfaccia ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="ec8f5-119">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="ec8f5-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="ec8f5-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
