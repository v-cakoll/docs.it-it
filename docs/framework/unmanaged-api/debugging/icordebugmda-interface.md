---
title: Interfaccia ICorDebugMDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugMDA
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugMDA
helpviewer_keywords: ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c53e03acddc5d732a684cf825bce49a65bb4c31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="37233-102">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="37233-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="37233-103">Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).</span><span class="sxs-lookup"><span data-stu-id="37233-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="37233-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="37233-104">Methods</span></span>  
  
|<span data-ttu-id="37233-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="37233-105">Method</span></span>|<span data-ttu-id="37233-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="37233-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="37233-107">Metodo GetDescription</span><span class="sxs-lookup"><span data-stu-id="37233-107">GetDescription Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getdescription-method.md)|<span data-ttu-id="37233-108">Ottiene una stringa contenente una descrizione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="37233-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="37233-109">Metodo GetFlags</span><span class="sxs-lookup"><span data-stu-id="37233-109">GetFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getflags-method.md)|<span data-ttu-id="37233-110">Ottiene i flag associati a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="37233-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="37233-111">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="37233-111">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getname-method.md)|<span data-ttu-id="37233-112">Ottiene una stringa contenente il nome di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="37233-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="37233-113">Metodo GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="37233-113">GetOSThreadId Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getosthreadid-method.md)|<span data-ttu-id="37233-114">Ottiene l'identificatore del thread del sistema operativo in cui è in esecuzione questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="37233-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="37233-115">Metodo GetXML</span><span class="sxs-lookup"><span data-stu-id="37233-115">GetXML Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-getxml-method.md)|<span data-ttu-id="37233-116">Ottiene il flusso XML completo associato a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="37233-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37233-117">Note</span><span class="sxs-lookup"><span data-stu-id="37233-117">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37233-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="37233-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="37233-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="37233-119">Requirements</span></span>  
 <span data-ttu-id="37233-120">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37233-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37233-121">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="37233-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="37233-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="37233-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="37233-123">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37233-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37233-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="37233-124">See Also</span></span>  
 [<span data-ttu-id="37233-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="37233-125">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="37233-126">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="37233-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
