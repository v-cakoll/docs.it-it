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
ms.openlocfilehash: 3d5284cf6072aa5c1c11cc83355a3e9fa5c96837
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415922"
---
# <a name="icordebugmanagedcallbacklogswitch-method"></a><span data-ttu-id="8c5a4-102">Metodo ICorDebugManagedCallback::LogSwitch</span><span class="sxs-lookup"><span data-stu-id="8c5a4-102">ICorDebugManagedCallback::LogSwitch Method</span></span>
<span data-ttu-id="8c5a4-103">Notifica al debugger che un thread di common language runtime (CLR) gestito ha chiamato un metodo di <xref:System.Diagnostics.Switch> classe per creare, modificare o eliminare un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="8c5a4-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.Switch> class to create, modify, or delete a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5a4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8c5a4-104">Syntax</span></span>  
  
```  
HRESULT LogSwitch (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] ULONG                ulReason,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pParentName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8c5a4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8c5a4-105">Parameters</span></span>  
 `PAppDomain`  
 <span data-ttu-id="8c5a4-106">[in] Un puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio dell'applicazione contenente il thread gestito che creato, modificato o eliminato un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="8c5a4-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that created, modified, or deleted a debugging/tracing switch.</span></span>  
  
 `pThread`  
 <span data-ttu-id="8c5a4-107">[in] Un puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="8c5a4-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="8c5a4-108">[in] Un valore che indica il livello di gravità del messaggio descrittivo scritto nel registro eventi.</span><span class="sxs-lookup"><span data-stu-id="8c5a4-108">[in] A value that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `ulReason`  
 <span data-ttu-id="8c5a4-109">[in] Il valore di [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumerazione che indica l'operazione eseguita sull'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="8c5a4-109">[in] A value of the [LogSwitchCallReason](../../../../docs/framework/unmanaged-api/debugging/logswitchcallreason-enumeration.md) enumeration that indicates the operation performed on the debugging/tracing switch.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="8c5a4-110">[in] Un puntatore al nome dell'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="8c5a4-110">[in] A pointer to the name of the debugging/tracing switch.</span></span>  
  
 `pParentName`  
 <span data-ttu-id="8c5a4-111">[in] Un puntatore al nome dell'elemento padre dell'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="8c5a4-111">[in] A pointer to the name of the parent of the debugging/tracing switch.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c5a4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8c5a4-112">Requirements</span></span>  
 <span data-ttu-id="8c5a4-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c5a4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c5a4-114">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="8c5a4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c5a4-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8c5a4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c5a4-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c5a4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5a4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c5a4-117">See Also</span></span>  
 [<span data-ttu-id="8c5a4-118">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="8c5a4-118">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
