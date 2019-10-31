---
title: Metodo ICorDebugManagedCallback3::CustomNotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback3.CustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback3::CustomNotification
helpviewer_keywords:
- ICorDebugManagedCallback3::CustomNotification method [.NET Framework debugging]
- CustomNotification method [.NET Framework debugging]
ms.assetid: 5e5422ac-afa1-403d-a894-2d7348673e38
topic_type:
- apiref
ms.openlocfilehash: 83192fd2d24e740ab470988531db823b34df4494
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131429"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="f19c8-102">Metodo ICorDebugManagedCallback3::CustomNotification</span><span class="sxs-lookup"><span data-stu-id="f19c8-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="f19c8-103">Indica che è stata generata una notifica del debugger personalizzata.</span><span class="sxs-lookup"><span data-stu-id="f19c8-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19c8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f19c8-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f19c8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f19c8-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="f19c8-106">in Puntatore al thread che ha generato la notifica.</span><span class="sxs-lookup"><span data-stu-id="f19c8-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="f19c8-107">in Puntatore al dominio dell'applicazione che contiene il thread che ha generato la notifica.</span><span class="sxs-lookup"><span data-stu-id="f19c8-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f19c8-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f19c8-108">Return Value</span></span>  
 <span data-ttu-id="f19c8-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="f19c8-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f19c8-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f19c8-110">HRESULT</span></span>|<span data-ttu-id="f19c8-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f19c8-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f19c8-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f19c8-112">S_OK</span></span>|<span data-ttu-id="f19c8-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f19c8-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="f19c8-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="f19c8-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f19c8-115">Note</span><span class="sxs-lookup"><span data-stu-id="f19c8-115">Remarks</span></span>  
 <span data-ttu-id="f19c8-116">Una chiamata successiva al metodo [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) recupera l'oggetto thread passato al metodo <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f19c8-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f19c8-117">Il tipo dell'oggetto thread deve essere stato precedentemente abilitato chiamando il metodo [ICorDebugProcess3:: SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f19c8-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="f19c8-118">Il debugger può leggere i parametri specifici del tipo dai campi dell'oggetto thread e può archiviare le risposte nei campi.</span><span class="sxs-lookup"><span data-stu-id="f19c8-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="f19c8-119">L'interfaccia [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) non impone alcun criterio sui tipi di notifiche o il relativo contenuto e la semantica delle notifiche è esclusivamente un contratto tra i debugger, le applicazioni e il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f19c8-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f19c8-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f19c8-120">Requirements</span></span>  
 <span data-ttu-id="f19c8-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f19c8-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f19c8-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f19c8-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f19c8-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f19c8-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f19c8-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f19c8-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19c8-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f19c8-125">See also</span></span>

- [<span data-ttu-id="f19c8-126">Interfaccia ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="f19c8-126">ICorDebugManagedCallback3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="f19c8-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="f19c8-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f19c8-128">Debug</span><span class="sxs-lookup"><span data-stu-id="f19c8-128">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
