---
title: Metodo ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c12ea84f1a706850972b2e404ec52eea3523de7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412636"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="37819-102">Metodo ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="37819-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="37819-103">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="37819-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37819-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="37819-104">Syntax</span></span>  
  
```  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37819-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="37819-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="37819-106">[out] Puntatore all'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="37819-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37819-107">Note</span><span class="sxs-lookup"><span data-stu-id="37819-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37819-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="37819-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37819-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37819-109">Requirements</span></span>  
 <span data-ttu-id="37819-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37819-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37819-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="37819-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37819-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="37819-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37819-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37819-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37819-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37819-114">See Also</span></span>  
 [<span data-ttu-id="37819-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="37819-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="37819-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="37819-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
