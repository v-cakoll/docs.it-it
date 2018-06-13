---
title: Metodo ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bbc9581db839d9c0a48362eac2108f43665b0fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414856"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="0de45-102">Metodo ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="0de45-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="0de45-103">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="0de45-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0de45-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0de45-104">Syntax</span></span>  
  
```  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0de45-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0de45-105">Parameters</span></span>  
 <span data-ttu-id="0de45-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="0de45-106">pDebugEventKind</span></span>  
 <span data-ttu-id="0de45-107">Un puntatore a un [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) membro di enumerazione che indica il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="0de45-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0de45-108">Note</span><span class="sxs-lookup"><span data-stu-id="0de45-108">Remarks</span></span>  
 <span data-ttu-id="0de45-109">In base al valore di `pDebugEventKind`, è possibile chiamare `QueryInterface` per ottenere un'interfaccia degli eventi di debug più precisa, contenente dati aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="0de45-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0de45-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0de45-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0de45-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0de45-111">Requirements</span></span>  
 <span data-ttu-id="0de45-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0de45-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0de45-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0de45-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0de45-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="0de45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0de45-115">**Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0de45-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0de45-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0de45-116">See Also</span></span>  
 [<span data-ttu-id="0de45-117">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="0de45-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="0de45-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="0de45-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
