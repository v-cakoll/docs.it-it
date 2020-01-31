---
title: Metodo ICorDebugManagedCallback::LogMessage
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 4306c4ae44b0ae1ade2bf374981492fa1a4df76f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788375"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="3fb9d-102">Metodo ICorDebugManagedCallback::LogMessage</span><span class="sxs-lookup"><span data-stu-id="3fb9d-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="3fb9d-103">Notifica al debugger che un thread gestito di Common Language Runtime (CLR) ha chiamato un metodo nella classe <xref:System.Diagnostics.EventLog> per registrare un evento.</span><span class="sxs-lookup"><span data-stu-id="3fb9d-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3fb9d-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fb9d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3fb9d-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="3fb9d-106">in Puntatore a un oggetto ICorDebugAppDomain che rappresenta il dominio applicazione contenente il thread gestito che ha registrato l'evento.</span><span class="sxs-lookup"><span data-stu-id="3fb9d-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3fb9d-107">in Puntatore a un oggetto ICorDebugThread che rappresenta il thread gestito.</span><span class="sxs-lookup"><span data-stu-id="3fb9d-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="3fb9d-108">in Valore dell'enumerazione [LoggingLevelEnum](logginglevelenum-enumeration.md) che indica il livello di gravità del messaggio descrittivo che è stato scritto nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="3fb9d-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="3fb9d-109">in Puntatore al nome dell'opzione di traccia.</span><span class="sxs-lookup"><span data-stu-id="3fb9d-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="3fb9d-110">in Puntatore al messaggio scritto nel log eventi.</span><span class="sxs-lookup"><span data-stu-id="3fb9d-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb9d-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="3fb9d-111">Requirements</span></span>  
 <span data-ttu-id="3fb9d-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fb9d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb9d-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fb9d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fb9d-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fb9d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fb9d-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fb9d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fb9d-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fb9d-116">See also</span></span>

- [<span data-ttu-id="3fb9d-117">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="3fb9d-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
