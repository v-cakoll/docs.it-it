---
title: Metodo ICorDebugProcess6::ProcessStateChanged
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
ms.openlocfilehash: 6be216741e902b15efc3a3ece95cb4a4229960e3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212847"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="5a4aa-102">Metodo ICorDebugProcess6::ProcessStateChanged</span><span class="sxs-lookup"><span data-stu-id="5a4aa-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="5a4aa-103">Notifica a [ICorDebug](icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5a4aa-103">Notifies [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a4aa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a4aa-104">Syntax</span></span>  
  
```cpp  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a4aa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a4aa-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="5a4aa-106">in Membro dell'enumerazione [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md)</span><span class="sxs-lookup"><span data-stu-id="5a4aa-106">[in] A member of the [ProcessStateChanged](icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a4aa-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5a4aa-107">Remarks</span></span>  
 <span data-ttu-id="5a4aa-108">Il debugger chiama questo metodo per notificare a [ICorDebug](icordebug-interface.md) che il processo è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="5a4aa-108">The debugger calls this method to notify [ICorDebug](icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5a4aa-109">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="5a4aa-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a4aa-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a4aa-110">Requirements</span></span>  
 <span data-ttu-id="5a4aa-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a4aa-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a4aa-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a4aa-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a4aa-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a4aa-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a4aa-114">**Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4aa-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4aa-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a4aa-115">See also</span></span>

- [<span data-ttu-id="5a4aa-116">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="5a4aa-116">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="5a4aa-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5a4aa-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
