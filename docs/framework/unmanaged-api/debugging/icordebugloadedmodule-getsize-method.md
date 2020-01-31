---
title: Metodo ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: f207cd1c612b6444a9512adaa356ac2d01de7b9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788459"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="30c9b-102">Metodo ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="30c9b-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="30c9b-103">Ottiene le dimensioni, in byte, del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="30c9b-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30c9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30c9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="30c9b-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="30c9b-106">[out] Puntatore al numero di byte nel modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="30c9b-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30c9b-107">Note</span><span class="sxs-lookup"><span data-stu-id="30c9b-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30c9b-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="30c9b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30c9b-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="30c9b-109">Requirements</span></span>  
 <span data-ttu-id="30c9b-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30c9b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c9b-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30c9b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30c9b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30c9b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30c9b-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c9b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c9b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30c9b-114">See also</span></span>

- [<span data-ttu-id="30c9b-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="30c9b-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="30c9b-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="30c9b-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
