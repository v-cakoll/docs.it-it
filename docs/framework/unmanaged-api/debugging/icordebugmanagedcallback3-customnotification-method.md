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
ms.openlocfilehash: 8a4620e591cc80efb5c0fd53b0edf3a35849c421
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209760"
---
# <a name="icordebugmanagedcallback3customnotification-method"></a><span data-ttu-id="5fd79-102">Metodo ICorDebugManagedCallback3::CustomNotification</span><span class="sxs-lookup"><span data-stu-id="5fd79-102">ICorDebugManagedCallback3::CustomNotification Method</span></span>
<span data-ttu-id="5fd79-103">Indica che è stata generata una notifica del debugger personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5fd79-103">Indicates that a custom debugger notification has been raised.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fd79-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5fd79-104">Syntax</span></span>  
  
```cpp  
HRESULT CustomNotification(ICorDebugThread *    pThread,  
                           ICorDebugAppDomain * pAppDomain);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fd79-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5fd79-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="5fd79-106">in Puntatore al thread che ha generato la notifica.</span><span class="sxs-lookup"><span data-stu-id="5fd79-106">[in] A pointer to the thread that raised the notification.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="5fd79-107">in Puntatore al dominio dell'applicazione che contiene il thread che ha generato la notifica.</span><span class="sxs-lookup"><span data-stu-id="5fd79-107">[in] A pointer to the application domain that contains the thread that raised the notification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5fd79-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5fd79-108">Return Value</span></span>  
 <span data-ttu-id="5fd79-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="5fd79-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5fd79-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5fd79-110">HRESULT</span></span>|<span data-ttu-id="5fd79-111">Description</span><span class="sxs-lookup"><span data-stu-id="5fd79-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5fd79-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5fd79-112">S_OK</span></span>|<span data-ttu-id="5fd79-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="5fd79-113">The method completed successfully.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="5fd79-114">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="5fd79-114">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fd79-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5fd79-115">Remarks</span></span>  
 <span data-ttu-id="5fd79-116">Una chiamata successiva al metodo [ICorDebugThread4:: GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) recupera l'oggetto thread passato al <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="5fd79-116">A subsequent call to the [ICorDebugThread4::GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md) method retrieves the thread object that was passed to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5fd79-117">Il tipo dell'oggetto thread deve essere stato precedentemente abilitato chiamando il metodo [ICorDebugProcess3:: SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5fd79-117">The thread object's type must have been previously enabled by calling the [ICorDebugProcess3::SetEnableCustomNotification](icordebugprocess3-setenablecustomnotification-method.md) method.</span></span> <span data-ttu-id="5fd79-118">Il debugger può leggere i parametri specifici del tipo dai campi dell'oggetto thread e può archiviare le risposte nei campi.</span><span class="sxs-lookup"><span data-stu-id="5fd79-118">The debugger can read type-specific parameters from the fields of the thread object, and can store responses into fields.</span></span>  
  
 <span data-ttu-id="5fd79-119">L'interfaccia [ICorDebug](icordebug-interface.md) non impone alcun criterio sui tipi di notifiche o il relativo contenuto e la semantica delle notifiche è esclusivamente un contratto tra i debugger, le applicazioni e il .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5fd79-119">The [ICorDebug](icordebug-interface.md) interface imposes no policy on the types of notifications or their contents, and the semantics of the notifications are strictly a contract between debuggers, applications, and the .NET Framework.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fd79-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5fd79-120">Requirements</span></span>  
 <span data-ttu-id="5fd79-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fd79-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fd79-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fd79-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fd79-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fd79-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fd79-124">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fd79-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fd79-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5fd79-125">See also</span></span>

- [<span data-ttu-id="5fd79-126">Interfaccia ICorDebugManagedCallback3</span><span class="sxs-lookup"><span data-stu-id="5fd79-126">ICorDebugManagedCallback3 Interface</span></span>](icordebugmanagedcallback3-interface.md)
- [<span data-ttu-id="5fd79-127">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5fd79-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5fd79-128">Debug</span><span class="sxs-lookup"><span data-stu-id="5fd79-128">Debugging</span></span>](index.md)
