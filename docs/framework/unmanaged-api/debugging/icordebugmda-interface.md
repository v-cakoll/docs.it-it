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
ms.openlocfilehash: a147aee1ebba57b86dbbf8a7648456b8d7494936
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793189"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="8d32e-102">Interfaccia ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="8d32e-102">ICorDebugMDA Interface</span></span>
<span data-ttu-id="8d32e-103">Rappresenta un messaggio relativo all'assistente al debug gestito (MDA, Managed Debugging Assistant).</span><span class="sxs-lookup"><span data-stu-id="8d32e-103">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d32e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="8d32e-104">Methods</span></span>  
  
|<span data-ttu-id="8d32e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="8d32e-105">Method</span></span>|<span data-ttu-id="8d32e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8d32e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d32e-107">Metodo GetDescription</span><span class="sxs-lookup"><span data-stu-id="8d32e-107">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="8d32e-108">Ottiene una stringa contenente una descrizione di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d32e-108">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="8d32e-109">Metodo GetFlags</span><span class="sxs-lookup"><span data-stu-id="8d32e-109">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="8d32e-110">Ottiene i flag associati a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d32e-110">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="8d32e-111">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="8d32e-111">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="8d32e-112">Ottiene una stringa contenente il nome di questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d32e-112">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="8d32e-113">Metodo GetOSThreadId</span><span class="sxs-lookup"><span data-stu-id="8d32e-113">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="8d32e-114">Ottiene l'identificatore del thread del sistema operativo su cui è in esecuzione questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d32e-114">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="8d32e-115">Metodo GetXML</span><span class="sxs-lookup"><span data-stu-id="8d32e-115">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="8d32e-116">Ottiene il flusso XML completo associato a questo assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="8d32e-116">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d32e-117">Note</span><span class="sxs-lookup"><span data-stu-id="8d32e-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d32e-118">Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.</span><span class="sxs-lookup"><span data-stu-id="8d32e-118">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d32e-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="8d32e-119">Requirements</span></span>  
 <span data-ttu-id="8d32e-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d32e-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d32e-121">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d32e-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d32e-122">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d32e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d32e-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d32e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d32e-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d32e-124">See also</span></span>

- [<span data-ttu-id="8d32e-125">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="8d32e-125">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="8d32e-126">Diagnostica degli errori tramite gli assistenti al debug gestito</span><span class="sxs-lookup"><span data-stu-id="8d32e-126">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
