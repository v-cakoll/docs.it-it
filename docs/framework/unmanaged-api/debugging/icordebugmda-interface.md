---
title: Interfaccia ICorDebugMDA
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 550b39445dfe4d97e712e9a4c73aa0f497b3fce5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420966"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="f0fc7-102">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="f0fc7-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="f0fc7-103">Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).</span><span class="sxs-lookup"><span data-stu-id="f0fc7-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f0fc7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f0fc7-104">Methods</span></span>  
  
|<span data-ttu-id="f0fc7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f0fc7-105">Method</span></span>|<span data-ttu-id="f0fc7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f0fc7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0fc7-107">Metodo GetDescription</span><span class="sxs-lookup"><span data-stu-id="f0fc7-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="f0fc7-108">Ottiene una stringa contenente una descrizione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f0fc7-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="f0fc7-109">Metodo GetFlags</span><span class="sxs-lookup"><span data-stu-id="f0fc7-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="f0fc7-110">Ottiene i flag associati a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f0fc7-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="f0fc7-111">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="f0fc7-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="f0fc7-112">Ottiene una stringa contenente il nome di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f0fc7-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="f0fc7-113">Metodo GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="f0fc7-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="f0fc7-114">Ottiene l'identificatore del thread del sistema operativo in cui è in esecuzione questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f0fc7-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="f0fc7-115">Metodo GetXML</span><span class="sxs-lookup"><span data-stu-id="f0fc7-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="f0fc7-116">Ottiene il flusso XML completo associato a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f0fc7-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0fc7-117">Note</span><span class="sxs-lookup"><span data-stu-id="f0fc7-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0fc7-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="f0fc7-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0fc7-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f0fc7-119">Requirements</span></span>  
 <span data-ttu-id="f0fc7-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0fc7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0fc7-121">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="f0fc7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0fc7-122">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="f0fc7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0fc7-123">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0fc7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fc7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0fc7-124">See Also</span></span>  
 [<span data-ttu-id="f0fc7-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f0fc7-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="f0fc7-126">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="f0fc7-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
