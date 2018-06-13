---
title: Metodo ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9768fb91749158bf3193919b2106bde1c618468a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413231"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="8a566-102">Metodo ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="8a566-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="8a566-103">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="8a566-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a566-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8a566-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a566-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8a566-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="8a566-106">[out] Puntatore al numero di byte nel modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="8a566-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a566-107">Note</span><span class="sxs-lookup"><span data-stu-id="8a566-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a566-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="8a566-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a566-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8a566-109">Requirements</span></span>  
 <span data-ttu-id="8a566-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a566-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a566-111">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8a566-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a566-112">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8a566-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a566-113">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a566-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a566-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8a566-114">See Also</span></span>  
 [<span data-ttu-id="8a566-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="8a566-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="8a566-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8a566-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
