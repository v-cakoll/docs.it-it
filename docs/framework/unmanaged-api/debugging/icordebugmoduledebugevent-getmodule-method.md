---
title: Metodo ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 1df71ddbf1ee76cc8202d8f9e263b9d95b4aaa09
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213361"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="54e9b-102">Metodo ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="54e9b-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="54e9b-103">Ottiene il modulo unito appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="54e9b-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54e9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54e9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="54e9b-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="54e9b-106">[out] Puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo unito che è stato appena caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="54e9b-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54e9b-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="54e9b-107">Remarks</span></span>  
 <span data-ttu-id="54e9b-108">È possibile chiamare il metodo [GetEventKind](icordebugdebugevent-geteventkind-method.md) per determinare se il modulo è stato caricato o scaricato.</span><span class="sxs-lookup"><span data-stu-id="54e9b-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54e9b-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="54e9b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e9b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54e9b-110">Requirements</span></span>  
 <span data-ttu-id="54e9b-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54e9b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e9b-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54e9b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54e9b-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54e9b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54e9b-114">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e9b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e9b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="54e9b-115">See also</span></span>

- [<span data-ttu-id="54e9b-116">Interfaccia ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="54e9b-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="54e9b-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="54e9b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
