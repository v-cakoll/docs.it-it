---
title: Metodo ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 6e3ebdcb5b3e85f6f5a329ed249aa58be903e30f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976395"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="b68f3-102">Metodo ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="b68f3-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="b68f3-103">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="b68f3-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b68f3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b68f3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b68f3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b68f3-105">Parameters</span></span>  
 <span data-ttu-id="b68f3-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="b68f3-106">pDebugEventKind</span></span>  
 <span data-ttu-id="b68f3-107">Puntatore a un membro di enumerazione [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) che indica il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="b68f3-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b68f3-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="b68f3-108">Remarks</span></span>  
 <span data-ttu-id="b68f3-109">In base al valore di `pDebugEventKind`, è possibile chiamare `QueryInterface` per ottenere un'interfaccia degli eventi di debug più precisa, contenente dati aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="b68f3-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b68f3-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b68f3-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b68f3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b68f3-111">Requirements</span></span>  
 <span data-ttu-id="b68f3-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b68f3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b68f3-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b68f3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b68f3-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b68f3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b68f3-115">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b68f3-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68f3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b68f3-116">See also</span></span>

- [<span data-ttu-id="b68f3-117">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="b68f3-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="b68f3-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b68f3-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
