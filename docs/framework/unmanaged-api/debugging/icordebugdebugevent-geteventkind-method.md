---
title: Metodo ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 92606d7bd0a277dd327ce4fd430ce963a260206d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136664"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="e4980-102">Metodo ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="e4980-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="e4980-103">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="e4980-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4980-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e4980-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4980-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e4980-105">Parameters</span></span>  
 <span data-ttu-id="e4980-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="e4980-106">pDebugEventKind</span></span>  
 <span data-ttu-id="e4980-107">Puntatore a un membro di enumerazione [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) che indica il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="e4980-107">A pointer to a [CorDebugDebugEventKind](../../../../docs/framework/unmanaged-api/debugging/cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4980-108">Note</span><span class="sxs-lookup"><span data-stu-id="e4980-108">Remarks</span></span>  
 <span data-ttu-id="e4980-109">In base al valore di `pDebugEventKind`, è possibile chiamare `QueryInterface` per ottenere un'interfaccia degli eventi di debug più precisa, contenente dati aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e4980-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4980-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="e4980-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4980-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4980-111">Requirements</span></span>  
 <span data-ttu-id="e4980-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4980-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4980-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4980-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4980-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4980-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4980-115">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4980-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4980-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4980-116">See also</span></span>

- [<span data-ttu-id="e4980-117">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="e4980-117">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="e4980-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e4980-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
