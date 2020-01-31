---
title: Metodo ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: 190c9114cffa537ba162b19abdf30d5a6aee87f8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788451"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="57114-102">Metodo ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="57114-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="57114-103">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="57114-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57114-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57114-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57114-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="57114-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="57114-106">[out] Puntatore all'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="57114-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57114-107">Note</span><span class="sxs-lookup"><span data-stu-id="57114-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57114-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="57114-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57114-109">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="57114-109">Requirements</span></span>  
 <span data-ttu-id="57114-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57114-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57114-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="57114-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="57114-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="57114-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="57114-113">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57114-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57114-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57114-114">See also</span></span>

- [<span data-ttu-id="57114-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="57114-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="57114-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="57114-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
