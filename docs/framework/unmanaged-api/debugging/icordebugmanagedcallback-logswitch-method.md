---
title: Metodo ICorDebugManagedCallback::LogSwitch
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogSwitch
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogSwitch
helpviewer_keywords:
- LogSwitch method [.NET Framework debugging]
- ICorDebugManagedCallback::LogSwitch method [.NET Framework debugging]
ms.assetid: 0ac59d27-783f-4a87-b7a8-baa3ccc54582
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a011485453999b9d764716356eebb2a5462f7bb9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59078837"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="b7a1b-102">Metodo ICorDebugManagedCallback::LogSwitch</span><span class="sxs-lookup"><span data-stu-id="b7a1b-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="b7a1b-103">Notifica al debugger che un thread di common language runtime (CLR) gestito ha chiamato un metodo di <xref:System.Diagnostics.Switch> classe da creare, modificare o eliminare un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="b7a1b-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a1b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b7a1b-104">Syntax</span></span>  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7a1b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b7a1b-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="b7a1b-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito creato, modificato o eliminato un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="b7a1b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="b7a1b-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="b7a1b-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="b7a1b-108">[in] Un valore che indica il livello di gravità del messaggio descrittivo che è stato scritto nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="b7a1b-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="b7a1b-109">[in] Valore di [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumerazione che indica l'operazione eseguita sull'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="b7a1b-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="b7a1b-110">[in] Un puntatore al nome del commutatore debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="b7a1b-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="b7a1b-111">[in] Un puntatore al nome dell'elemento padre dell'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="b7a1b-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7a1b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b7a1b-112">Requirements</span></span>  
 <span data-ttu-id="b7a1b-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7a1b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a1b-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7a1b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7a1b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7a1b-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b7a1b-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b7a1b-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7a1b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7a1b-117">See also</span></span>

- [<span data-ttu-id="b7a1b-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="b7a1b-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
