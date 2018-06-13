---
title: Metodo ICorDebugThread::GetCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 82686fdd14783257987ec5bf9a24db7d87049d42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421746"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="930c0-102">Metodo ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="930c0-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="930c0-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="930c0-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="930c0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="930c0-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="930c0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="930c0-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="930c0-106">[out] Un puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta l'eccezione generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="930c0-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="930c0-107">Note</span><span class="sxs-lookup"><span data-stu-id="930c0-107">Remarks</span></span>  
 <span data-ttu-id="930c0-108">L'oggetto eccezione esisterà dal momento in cui viene generata l'eccezione fino alla fine del `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="930c0-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="930c0-109">Una valutazione della funzione, che viene eseguita dai metodi ICorDebugEval, cancellerà l'oggetto eccezione della configurazione e ripristinarlo al completamento.</span><span class="sxs-lookup"><span data-stu-id="930c0-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="930c0-110">Le eccezioni possono essere annidate (ad esempio, se viene generata un'eccezione in un filtro o in una valutazione della funzione), pertanto potrebbero essere presenti più eccezioni in attesa su un thread singolo.</span><span class="sxs-lookup"><span data-stu-id="930c0-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="930c0-111">`GetCurrentException` Restituisce l'eccezione più recente.</span><span class="sxs-lookup"><span data-stu-id="930c0-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="930c0-112">L'oggetto eccezione e il tipo può variare per tutta la durata dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="930c0-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="930c0-113">Ad esempio, dopo che viene generata un'eccezione di tipo x, common language runtime (CLR) può memoria insufficiente e convertirlo in un'eccezione di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="930c0-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="930c0-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="930c0-114">Requirements</span></span>  
 <span data-ttu-id="930c0-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="930c0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="930c0-116">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="930c0-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="930c0-117">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="930c0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="930c0-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="930c0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
