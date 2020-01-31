---
title: Metodo ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: d4c22146422085daa4dc9d90ae5b3735a12500c2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793561"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="2b721-102">Metodo ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="2b721-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="2b721-103">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="2b721-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b721-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b721-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b721-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b721-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="2b721-106">[in] Numero di moduli per i quali sono richieste informazioni.</span><span class="sxs-lookup"><span data-stu-id="2b721-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="2b721-107">[out] Puntatore al numero di moduli sui quali sono state restituite informazioni.</span><span class="sxs-lookup"><span data-stu-id="2b721-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="2b721-108">out Puntatore a una matrice di oggetti [Metodo icordebugloadedmodule](icordebugloadedmodule-interface.md) che forniscono informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="2b721-108">[out] A pointer to an array of [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b721-109">Note</span><span class="sxs-lookup"><span data-stu-id="2b721-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2b721-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="2b721-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b721-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2b721-111">Requirements</span></span>  
 <span data-ttu-id="2b721-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b721-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b721-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b721-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b721-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b721-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b721-115">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b721-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b721-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b721-116">See also</span></span>

- [<span data-ttu-id="2b721-117">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="2b721-117">ICorDebugDataTarget3 Interface</span></span>](icordebugdatatarget3-interface.md)
- [<span data-ttu-id="2b721-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="2b721-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
