---
title: Metodo ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: d8c91c10577efd6a76af778cd01002de006df43a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209877"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="355eb-102">Metodo ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="355eb-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="355eb-103">Ottiene l'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="355eb-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="355eb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="355eb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="355eb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="355eb-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="355eb-106">[out] Puntatore all'indirizzo di base del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="355eb-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="355eb-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="355eb-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="355eb-108">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="355eb-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="355eb-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="355eb-109">Requirements</span></span>  
 <span data-ttu-id="355eb-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="355eb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="355eb-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="355eb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="355eb-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="355eb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="355eb-113">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="355eb-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="355eb-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="355eb-114">See also</span></span>

- [<span data-ttu-id="355eb-115">Interfaccia ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="355eb-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="355eb-116">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="355eb-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
