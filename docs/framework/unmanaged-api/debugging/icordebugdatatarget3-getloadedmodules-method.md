---
title: Metodo ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 464fd9ac44d6ba5717dbc4ecfbe03b6e6ad52276
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138658"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="b0e20-102">Metodo ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="b0e20-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="b0e20-103">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="b0e20-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0e20-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0e20-104">Syntax</span></span>  
  
```  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0e20-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0e20-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="b0e20-106">[in] Numero di moduli per i quali sono richieste informazioni.</span><span class="sxs-lookup"><span data-stu-id="b0e20-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="b0e20-107">[out] Puntatore al numero di moduli sui quali sono state restituite informazioni.</span><span class="sxs-lookup"><span data-stu-id="b0e20-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="b0e20-108">[out] Un puntatore a una matrice di [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) gli oggetti che forniscono informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="b0e20-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0e20-109">Note</span><span class="sxs-lookup"><span data-stu-id="b0e20-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0e20-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b0e20-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0e20-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0e20-111">Requirements</span></span>  
 <span data-ttu-id="b0e20-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0e20-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0e20-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0e20-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0e20-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0e20-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0e20-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0e20-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0e20-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0e20-116">See also</span></span>

- [<span data-ttu-id="b0e20-117">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="b0e20-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="b0e20-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b0e20-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
