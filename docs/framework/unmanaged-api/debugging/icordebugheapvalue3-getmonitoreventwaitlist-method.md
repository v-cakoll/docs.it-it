---
title: Metodo ICorDebugHeapValue3::GetMonitorEventWaitList
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetMonitorEventWaitList
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList
helpviewer_keywords:
- ICorDebugHeapValue3::GetMonitorEventWaitList method [.NET Framework debugging]
- GetMonitorEventWaitList method [.NET Framework debugging]
ms.assetid: 035a9035-ac66-4953-b48a-99652b42b7fe
topic_type:
- apiref
ms.openlocfilehash: 923e9b0821788143fff59eafe10d1802583df7a6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210423"
---
# <a name="icordebugheapvalue3getmonitoreventwaitlist-method"></a><span data-ttu-id="5f7cf-102">Metodo ICorDebugHeapValue3::GetMonitorEventWaitList</span><span class="sxs-lookup"><span data-stu-id="5f7cf-102">ICorDebugHeapValue3::GetMonitorEventWaitList Method</span></span>
<span data-ttu-id="5f7cf-103">Fornisce un elenco ordinato di thread accodati per l'evento associato a un blocco di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-103">Provides an ordered list of threads that are queued on the event that is associated with a monitor lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f7cf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f7cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorEventWaitList (  
    [out] ICorDebugThreadEnum **ppThreadEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f7cf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5f7cf-105">Parameters</span></span>  
 `ppThreadEnum`  
 <span data-ttu-id="5f7cf-106">out Enumeratore ICorDebugThreadEnum che fornisce l'elenco ordinato di thread.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-106">[out] The ICorDebugThreadEnum enumerator that provides the ordered list of threads.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f7cf-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5f7cf-107">Return Value</span></span>  
 <span data-ttu-id="5f7cf-108">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5f7cf-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f7cf-109">HRESULT</span></span>|<span data-ttu-id="5f7cf-110">Description</span><span class="sxs-lookup"><span data-stu-id="5f7cf-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f7cf-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f7cf-111">S_OK</span></span>|<span data-ttu-id="5f7cf-112">The list is not empty.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-112">The list is not empty.</span></span>|  
|<span data-ttu-id="5f7cf-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5f7cf-113">S_FALSE</span></span>|<span data-ttu-id="5f7cf-114">L'elenco è vuoto.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-114">The list is empty.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="5f7cf-115">Eccezioni</span><span class="sxs-lookup"><span data-stu-id="5f7cf-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f7cf-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5f7cf-116">Remarks</span></span>  
 <span data-ttu-id="5f7cf-117">Il primo thread nell'elenco è il primo thread rilasciato dalla chiamata successiva a <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="5f7cf-117">The first thread in the list is the first thread that is released by the next call to <xref:System.Threading.Monitor.Pulse%28System.Object%29?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5f7cf-118">Il thread successivo nell'elenco viene rilasciato nella chiamata seguente e così via.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-118">The next thread in the list is released on the following call, and so on.</span></span>  
  
 <span data-ttu-id="5f7cf-119">Se l'elenco non è vuoto, questo metodo restituisce S_OK.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-119">If the list is not empty, this method returns S_OK.</span></span> <span data-ttu-id="5f7cf-120">Se l'elenco è vuoto, il metodo restituisce S_FALSE; in questo caso, l'enumerazione è ancora valida, anche se è vuota.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-120">If the list is empty, the method returns S_FALSE; in this case, the enumeration is still valid, although it is empty.</span></span>  
  
 <span data-ttu-id="5f7cf-121">In entrambi i casi, l'interfaccia di enumerazione è utilizzabile solo per la durata dello stato sincronizzato corrente.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-121">In either case, the enumeration interface is usable only for the duration of the current synchronized state.</span></span> <span data-ttu-id="5f7cf-122">Tuttavia, le interfacce del thread da esso disposte sono valide fino alla chiusura del thread.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-122">However, the thread's interfaces dispensed from it are valid until the thread exits.</span></span>  
  
 <span data-ttu-id="5f7cf-123">Se `ppThreadEnum` non è un puntatore valido, il risultato è indefinito.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-123">If `ppThreadEnum` is not a valid pointer, the result is undefined.</span></span>  
  
 <span data-ttu-id="5f7cf-124">Se si verifica un errore in modo che non possa essere determinato quale, se presente, i thread sono in attesa del monitoraggio, il metodo restituisce un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="5f7cf-124">If an error occurs such that it cannot be determined which, if any, threads are waiting for the monitor, the method returns an HRESULT that indicates failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f7cf-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f7cf-125">Requirements</span></span>  
 <span data-ttu-id="5f7cf-126">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f7cf-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f7cf-127">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f7cf-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f7cf-128">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f7cf-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f7cf-129">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f7cf-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f7cf-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f7cf-130">See also</span></span>

- [<span data-ttu-id="5f7cf-131">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="5f7cf-131">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5f7cf-132">Debug</span><span class="sxs-lookup"><span data-stu-id="5f7cf-132">Debugging</span></span>](index.md)
