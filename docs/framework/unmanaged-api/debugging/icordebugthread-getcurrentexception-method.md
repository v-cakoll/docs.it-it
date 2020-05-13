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
ms.openlocfilehash: 3a4da6f958407c0b704ffb7372a77b7f022fc824
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379761"
---
# <a name="icordebugthreadgetcurrentexception-method"></a><span data-ttu-id="1e10e-102">Metodo ICorDebugThread::GetCurrentException</span><span class="sxs-lookup"><span data-stu-id="1e10e-102">ICorDebugThread::GetCurrentException Method</span></span>
<span data-ttu-id="1e10e-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugValue che rappresenta un'eccezione attualmente generata dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1e10e-103">Gets an interface pointer to an ICorDebugValue object that represents an exception that is currently being thrown by managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e10e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e10e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e10e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e10e-105">Parameters</span></span>  
 `ppExceptionObject`  
 <span data-ttu-id="1e10e-106">out Puntatore all'indirizzo di un `ICorDebugValue` oggetto che rappresenta l'eccezione generata attualmente dal codice gestito.</span><span class="sxs-lookup"><span data-stu-id="1e10e-106">[out] A pointer to the address of an `ICorDebugValue` object that represents the exception that is currently being thrown by managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e10e-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1e10e-107">Remarks</span></span>  
 <span data-ttu-id="1e10e-108">L'oggetto Exception sarà presente dal momento in cui viene generata l'eccezione fino alla fine del `catch` blocco.</span><span class="sxs-lookup"><span data-stu-id="1e10e-108">The exception object will exist from the time the exception is thrown until the end of the `catch` block.</span></span> <span data-ttu-id="1e10e-109">Una valutazione della funzione, eseguita dai metodi ICorDebugEval, eliminerà l'oggetto eccezione durante l'installazione e lo ripristinerà al completamento.</span><span class="sxs-lookup"><span data-stu-id="1e10e-109">A function evaluation, which is performed by the ICorDebugEval methods, will clear out the exception object on setup and restore it on completion.</span></span>  
  
 <span data-ttu-id="1e10e-110">È possibile nidificare le eccezioni, ad esempio se un'eccezione viene generata in un filtro o in una valutazione di funzione, quindi potrebbero esserci più eccezioni in attesa in un singolo thread.</span><span class="sxs-lookup"><span data-stu-id="1e10e-110">Exceptions can be nested (for example, if an exception is thrown in a filter or in a function evaluation), so there may be multiple outstanding exceptions on a single thread.</span></span> <span data-ttu-id="1e10e-111">`GetCurrentException`Restituisce l'eccezione più recente.</span><span class="sxs-lookup"><span data-stu-id="1e10e-111">`GetCurrentException` returns the most current exception.</span></span>  
  
 <span data-ttu-id="1e10e-112">L'oggetto eccezione e il tipo possono cambiare per tutta la durata dell'eccezione.</span><span class="sxs-lookup"><span data-stu-id="1e10e-112">The exception object and type may change throughout the life of the exception.</span></span> <span data-ttu-id="1e10e-113">Ad esempio, dopo che è stata generata un'eccezione di tipo x, il Common Language Runtime (CLR) potrebbe esaurire la memoria e innalzarlo di livello a un'eccezione di memoria insufficiente.</span><span class="sxs-lookup"><span data-stu-id="1e10e-113">For example, after an exception of type x is thrown, the common language runtime (CLR) may run out of memory and promote it to an out-of-memory exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e10e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e10e-114">Requirements</span></span>  
 <span data-ttu-id="1e10e-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e10e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e10e-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e10e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e10e-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e10e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e10e-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e10e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
