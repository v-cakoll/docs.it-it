---
title: Metodo ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: acce18517c105739417fc734b49ff004ca9546dc
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976378"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="34559-102">Metodo ICorDebugDebugEvent::GetThread</span><span class="sxs-lookup"><span data-stu-id="34559-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="34559-103">Ottiene il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="34559-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34559-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34559-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34559-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="34559-105">Parameters</span></span>  
 <span data-ttu-id="34559-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="34559-106">ppThread</span></span>  
 <span data-ttu-id="34559-107">[out] Un puntatore all'indirizzo di un oggetto ICorDebugThread che rappresenta il thread in cui si è verificato l'evento.</span><span class="sxs-lookup"><span data-stu-id="34559-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34559-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="34559-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="34559-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="34559-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34559-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="34559-110">Requirements</span></span>  
 <span data-ttu-id="34559-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34559-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34559-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34559-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34559-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34559-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34559-114">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34559-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34559-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="34559-115">See also</span></span>

- [<span data-ttu-id="34559-116">Interfaccia ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="34559-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="34559-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="34559-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
