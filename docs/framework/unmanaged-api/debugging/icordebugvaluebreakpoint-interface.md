---
title: Interfaccia ICorDebugValueBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint
helpviewer_keywords:
- ICorDebugValueBreakpoint interface [.NET Framework debugging]
ms.assetid: c02338fe-da6c-467f-9567-70ebb387e901
topic_type:
- apiref
ms.openlocfilehash: 1183f9f6d1ac221b20767f0a1bab15b3e9665a61
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396604"
---
# <a name="icordebugvaluebreakpoint-interface"></a><span data-ttu-id="cd9b6-102">Interfaccia ICorDebugValueBreakpoint</span><span class="sxs-lookup"><span data-stu-id="cd9b6-102">ICorDebugValueBreakpoint Interface</span></span>
<span data-ttu-id="cd9b6-103">Estende l'interfaccia ICorDebugBreakpoint per fornire l'accesso a valori specifici.</span><span class="sxs-lookup"><span data-stu-id="cd9b6-103">Extends the ICorDebugBreakpoint interface to provide access to specific values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd9b6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="cd9b6-104">Methods</span></span>  
  
|<span data-ttu-id="cd9b6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="cd9b6-105">Method</span></span>|<span data-ttu-id="cd9b6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cd9b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd9b6-107">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="cd9b6-107">GetValue Method</span></span>](icordebugvaluebreakpoint-getvalue-method.md)|<span data-ttu-id="cd9b6-108">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta il valore dell'oggetto su cui è impostato il punto di interruzione.</span><span class="sxs-lookup"><span data-stu-id="cd9b6-108">Gets an interface pointer to an ICorDebugValue object that represents the value of the object upon which the breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cd9b6-109">Commenti</span><span class="sxs-lookup"><span data-stu-id="cd9b6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cd9b6-110">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="cd9b6-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd9b6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cd9b6-111">Requirements</span></span>  
 <span data-ttu-id="cd9b6-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd9b6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd9b6-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd9b6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd9b6-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd9b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd9b6-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd9b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9b6-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="cd9b6-116">See also</span></span>

- [<span data-ttu-id="cd9b6-117">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="cd9b6-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
