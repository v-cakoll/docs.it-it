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
ms.openlocfilehash: d711f36b4e2071dac9458a023e1d3cf4743e77b3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212633"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="e4b71-102">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="e4b71-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="e4b71-103">Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).</span><span class="sxs-lookup"><span data-stu-id="e4b71-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4b71-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e4b71-104">Methods</span></span>  
  
|<span data-ttu-id="e4b71-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e4b71-105">Method</span></span>|<span data-ttu-id="e4b71-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e4b71-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4b71-107">Metodo GetDescription</span><span class="sxs-lookup"><span data-stu-id="e4b71-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="e4b71-108">Ottiene una stringa contenente una descrizione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="e4b71-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="e4b71-109">Metodo GetFlags</span><span class="sxs-lookup"><span data-stu-id="e4b71-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="e4b71-110">Ottiene i flag associati a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="e4b71-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="e4b71-111">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="e4b71-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="e4b71-112">Ottiene una stringa contenente il nome di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="e4b71-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="e4b71-113">Metodo GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="e4b71-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="e4b71-114">Ottiene l'identificatore del thread del sistema operativo su cui è in esecuzione questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="e4b71-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="e4b71-115">Metodo GetXML</span><span class="sxs-lookup"><span data-stu-id="e4b71-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="e4b71-116">Ottiene il flusso XML completo associato a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="e4b71-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4b71-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e4b71-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4b71-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="e4b71-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4b71-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e4b71-119">Requirements</span></span>  
 <span data-ttu-id="e4b71-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4b71-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4b71-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4b71-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4b71-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4b71-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4b71-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4b71-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b71-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4b71-124">See also</span></span>

- [<span data-ttu-id="e4b71-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="e4b71-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e4b71-126">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="e4b71-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
