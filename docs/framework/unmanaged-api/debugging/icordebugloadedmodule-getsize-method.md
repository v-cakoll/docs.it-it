---
title: Metodo ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 6a1c8c94b3c45ac995501b84bb4a69d73e7db25b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209851"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="cd695-102">Metodo ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="cd695-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="cd695-103">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="cd695-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd695-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cd695-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd695-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cd695-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="cd695-106">[out] Puntatore al numero di byte nel modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="cd695-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd695-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cd695-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd695-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="cd695-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd695-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd695-109">Requirements</span></span>  
 <span data-ttu-id="cd695-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd695-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd695-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd695-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd695-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd695-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd695-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd695-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd695-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd695-114">See also</span></span>

- [<span data-ttu-id="cd695-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="cd695-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="cd695-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd695-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
