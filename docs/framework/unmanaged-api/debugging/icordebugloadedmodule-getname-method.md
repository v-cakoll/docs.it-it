---
title: Metodo ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63341bcd6079688ed1a8e18ec8c422bca1427c72
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910084"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="0b267-102">Metodo ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="0b267-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="0b267-103">Ottiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="0b267-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b267-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b267-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b267-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b267-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0b267-106">[in] Numero di caratteri nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="0b267-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0b267-107">[out] Puntatore al numero di caratteri effettivamente scritti nel buffer `szName`.</span><span class="sxs-lookup"><span data-stu-id="0b267-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="0b267-108">[out] Matrice di caratteri che contiene il nome del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="0b267-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b267-109">Note</span><span class="sxs-lookup"><span data-stu-id="0b267-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b267-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0b267-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b267-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b267-111">Requirements</span></span>  
 <span data-ttu-id="0b267-112">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b267-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b267-113">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="0b267-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b267-114">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b267-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b267-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b267-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b267-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b267-116">See also</span></span>

- [<span data-ttu-id="0b267-117">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="0b267-117">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)
- [<span data-ttu-id="0b267-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0b267-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
