---
title: Metodo ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 0c67f8bdce49b4e9200b501aaf00ae293cced7d7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783409"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="d9bcb-102">Metodo ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="d9bcb-102">ICorDebugDebugEvent::GetEventKind Method</span></span>
<span data-ttu-id="d9bcb-103">Indica il tipo di evento rappresentato dall'oggetto `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="d9bcb-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9bcb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9bcb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9bcb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d9bcb-105">Parameters</span></span>  
 <span data-ttu-id="d9bcb-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="d9bcb-106">pDebugEventKind</span></span>  
 <span data-ttu-id="d9bcb-107">Puntatore a un membro di enumerazione [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) che indica il tipo di evento.</span><span class="sxs-lookup"><span data-stu-id="d9bcb-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9bcb-108">Note</span><span class="sxs-lookup"><span data-stu-id="d9bcb-108">Remarks</span></span>  
 <span data-ttu-id="d9bcb-109">In base al valore di `pDebugEventKind`, è possibile chiamare `QueryInterface` per ottenere un'interfaccia degli eventi di debug più precisa, contenente dati aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d9bcb-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9bcb-110">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="d9bcb-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9bcb-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="d9bcb-111">Requirements</span></span>  
 <span data-ttu-id="d9bcb-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9bcb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9bcb-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d9bcb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d9bcb-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9bcb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9bcb-115">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9bcb-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9bcb-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9bcb-116">See also</span></span>

- [<span data-ttu-id="d9bcb-117">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="d9bcb-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="d9bcb-118">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="d9bcb-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
