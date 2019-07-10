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
ms.openlocfilehash: 2a6d53ebfebb8c883065ce119c2338a2225f0472
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762487"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="33cf1-102">Metodo ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="33cf1-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="33cf1-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="33cf1-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cf1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="33cf1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33cf1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="33cf1-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="33cf1-106">[out] Un puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta l'eccezione generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="33cf1-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33cf1-107">Note</span><span class="sxs-lookup"><span data-stu-id="33cf1-107">Remarks</span></span>  
 <span data-ttu-id="33cf1-108">L'oggetto eccezione sarà disponibile dal momento in cui viene generata l'eccezione fino alla fine del `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="33cf1-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="33cf1-109">Una valutazione della funzione, che viene eseguita dai metodi ICorDebugEval, cancellerà l'oggetto eccezione nel programma di installazione e ripristinarlo quindi sul completamento.</span><span class="sxs-lookup"><span data-stu-id="33cf1-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="33cf1-110">Le eccezioni possono essere annidate (ad esempio, se viene generata un'eccezione in un filtro o in una funzione di valutazione), potrebbero essere presenti più eccezioni in sospeso in un unico thread.</span><span class="sxs-lookup"><span data-stu-id="33cf1-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="33cf1-111">`GetCurrentException` Restituisce l'eccezione più recente.</span><span class="sxs-lookup"><span data-stu-id="33cf1-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="33cf1-112">L'oggetto eccezione e il tipo può cambiare per tutta la durata dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="33cf1-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="33cf1-113">Ad esempio, dopo che viene generata un'eccezione di tipo x, common language runtime (CLR) può eseguire memoria insufficiente e alzato di livello un'eccezione di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="33cf1-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33cf1-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="33cf1-114">Requirements</span></span>  
 <span data-ttu-id="33cf1-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33cf1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33cf1-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33cf1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33cf1-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33cf1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33cf1-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33cf1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
