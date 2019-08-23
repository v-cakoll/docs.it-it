---
title: Metodo ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 120b839b2b11c85f42bb1a0ae4701de0dea33879
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69912828"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="1ce35-102">Metodo ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="1ce35-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="1ce35-103">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="1ce35-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce35-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1ce35-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce35-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1ce35-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="1ce35-106">[in] Numero di moduli per i quali sono richieste informazioni.</span><span class="sxs-lookup"><span data-stu-id="1ce35-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="1ce35-107">[out] Puntatore al numero di moduli sui quali sono state restituite informazioni.</span><span class="sxs-lookup"><span data-stu-id="1ce35-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="1ce35-108">out Puntatore a una matrice di oggetti [Metodo icordebugloadedmodule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) che forniscono informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="1ce35-108">[out] A pointer to an array of [ICorDebugLoadedModule](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ce35-109">Note</span><span class="sxs-lookup"><span data-stu-id="1ce35-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ce35-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="1ce35-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ce35-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1ce35-111">Requirements</span></span>  
 <span data-ttu-id="1ce35-112">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ce35-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ce35-113">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="1ce35-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1ce35-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ce35-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ce35-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ce35-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce35-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ce35-116">See also</span></span>

- [<span data-ttu-id="1ce35-117">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="1ce35-117">ICorDebugDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)
- [<span data-ttu-id="1ce35-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="1ce35-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
