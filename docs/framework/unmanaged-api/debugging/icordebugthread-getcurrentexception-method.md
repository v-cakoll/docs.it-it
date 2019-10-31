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
ms.openlocfilehash: 8082b2a3654f1605f18f3b68f54464dc83c8e60a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133481"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="b0aeb-102">Metodo ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="b0aeb-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="b0aeb-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione attualmente generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0aeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b0aeb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0aeb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b0aeb-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="b0aeb-106">out Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta l'eccezione generata attualmente dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0aeb-107">Note</span><span class="sxs-lookup"><span data-stu-id="b0aeb-107">Remarks</span></span>  
 <span data-ttu-id="b0aeb-108">L'oggetto Exception sarà presente dal momento in cui viene generata l'eccezione fino alla fine del blocco `catch`.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="b0aeb-109">Una valutazione della funzione, eseguita dai metodi ICorDebugEval, eliminerà l'oggetto eccezione durante l'installazione e lo ripristinerà al completamento.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="b0aeb-110">È possibile nidificare le eccezioni, ad esempio se un'eccezione viene generata in un filtro o in una valutazione di funzione, quindi potrebbero esserci più eccezioni in attesa in un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="b0aeb-111">`GetCurrentException` restituisce l'eccezione più recente.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="b0aeb-112">L'oggetto eccezione e il tipo possono cambiare per tutta la durata dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="b0aeb-113">Ad esempio, dopo che è stata generata un'eccezione di tipo x, il Common Language Runtime (CLR) potrebbe esaurire la memoria e innalzarlo di livello a un'eccezione di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="b0aeb-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0aeb-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b0aeb-114">Requirements</span></span>  
 <span data-ttu-id="b0aeb-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0aeb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0aeb-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0aeb-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0aeb-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0aeb-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0aeb-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0aeb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
