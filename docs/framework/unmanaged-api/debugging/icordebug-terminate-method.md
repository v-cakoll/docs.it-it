---
title: Metodo ICorDebug::Terminate
ms.date: 03/30/2017
api_name:
- ICorDebug.Terminate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Terminate
helpviewer_keywords:
- Terminate method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Terminate method [.NET Framework debugging]
ms.assetid: fffe5616-0896-4426-ab5e-21869b514883
topic_type:
- apiref
ms.openlocfilehash: 2d3f8360a1fb1164fd4e26f85246251409bee376
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788953"
---
# <a name="icordebugterminate-method"></a><span data-ttu-id="0c4b9-102">Metodo ICorDebug::Terminate</span><span class="sxs-lookup"><span data-stu-id="0c4b9-102">ICorDebug::Terminate Method</span></span>
<span data-ttu-id="0c4b9-103">Termina l'oggetto `ICorDebug`.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-103">Terminates the `ICorDebug` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c4b9-104">`Terminate` non devono essere chiamati fino a quando non viene ricevuto un callback [ICorDebugManagedCallback:: ExitProcess](icordebugmanagedcallback-exitprocess-method.md) per tutti i processi di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-104">`Terminate` should not be called until an [ICorDebugManagedCallback::ExitProcess](icordebugmanagedcallback-exitprocess-method.md) callback has been received for all processes being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c4b9-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0c4b9-105">Syntax</span></span>  
  
```cpp  
HRESULT Terminate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0c4b9-106">Note</span><span class="sxs-lookup"><span data-stu-id="0c4b9-106">Remarks</span></span>  
 <span data-ttu-id="0c4b9-107">`Terminate` necessario chiamare quando l'oggetto `ICorDebug` non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="0c4b9-107">`Terminate` must be called when the `ICorDebug` object is no longer needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c4b9-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="0c4b9-108">Requirements</span></span>  
 <span data-ttu-id="0c4b9-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c4b9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c4b9-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c4b9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c4b9-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c4b9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c4b9-112">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c4b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4b9-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c4b9-113">See also</span></span>

- [<span data-ttu-id="0c4b9-114">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="0c4b9-114">ICorDebug Interface</span></span>](icordebug-interface.md)
