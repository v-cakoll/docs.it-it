---
title: Metodo ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: c3565f4f9284bc121b0e2d3b0885cbea927acfdd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976421"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="0ce3a-102">Metodo ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="0ce3a-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="0ce3a-103">Ottiene un elenco dei moduli caricati fino a questo momento.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ce3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ce3a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ce3a-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="0ce3a-106">[in] Numero di moduli per i quali sono richieste informazioni.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="0ce3a-107">[out] Puntatore al numero di moduli sui quali sono state restituite informazioni.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="0ce3a-108">out Puntatore a una matrice di oggetti [Metodo icordebugloadedmodule](icordebugloadedmodule-interface.md) che forniscono informazioni sui moduli caricati.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-108">[out] A pointer to an array of [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ce3a-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="0ce3a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0ce3a-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ce3a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ce3a-111">Requirements</span></span>  
 <span data-ttu-id="0ce3a-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ce3a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ce3a-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0ce3a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0ce3a-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ce3a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0ce3a-115">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ce3a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce3a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ce3a-116">See also</span></span>

- [<span data-ttu-id="0ce3a-117">Interfaccia ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="0ce3a-117">ICorDebugDataTarget3 Interface</span></span>](icordebugdatatarget3-interface.md)
- [<span data-ttu-id="0ce3a-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0ce3a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
