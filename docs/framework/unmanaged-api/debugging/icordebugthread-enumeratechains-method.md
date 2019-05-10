---
title: Metodo ICorDebugThread::EnumerateChains
ms.date: 03/30/2017
api_name:
- ICorDebugThread.EnumerateChains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f131f7566376d6474f3189d5eb612b30bec2e2b7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648429"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="f1419-102">Metodo ICorDebugThread::EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="f1419-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="f1419-103">Ottiene un puntatore a interfaccia per un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f1419-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1419-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1419-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1419-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f1419-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="f1419-106">[out] Un puntatore all'indirizzo di un `ICorDebugChainEnum` oggetto che consente l'enumerazione di tutti i stack concatenato in questo thread, a partire da quella attiva (ovvero, il più recente).</span><span class="sxs-lookup"><span data-stu-id="f1419-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1419-107">Note</span><span class="sxs-lookup"><span data-stu-id="f1419-107">Remarks</span></span>  
 <span data-ttu-id="f1419-108">La catena dello stack rappresenta lo stack di chiamate fisico per il thread.</span><span class="sxs-lookup"><span data-stu-id="f1419-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="f1419-109">Le circostanze seguenti creare un limite di catena dello stack:</span><span class="sxs-lookup"><span data-stu-id="f1419-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="f1419-110">Una transizione da gestito o non gestito a gestito.</span><span class="sxs-lookup"><span data-stu-id="f1419-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="f1419-111">Un cambio di contesto.</span><span class="sxs-lookup"><span data-stu-id="f1419-111">A context switch.</span></span>  
  
- <span data-ttu-id="f1419-112">Un Hijack di un thread di utente del debugger.</span><span class="sxs-lookup"><span data-stu-id="f1419-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="f1419-113">Nel caso più semplice per un thread che esegue codice gestito esclusivamente in un singolo contesto, sarà presente una corrispondenza uno a uno tra thread e catene dello stack.</span><span class="sxs-lookup"><span data-stu-id="f1419-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="f1419-114">Un debugger potrebbe essere necessario modificare gli stack di chiamate fisico di tutti i thread in stack di chiamate logici.</span><span class="sxs-lookup"><span data-stu-id="f1419-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="f1419-115">Ciò comporta l'ordinamento di catene di tutti i thread per le relative relazioni chiamante/chiamato e il relativo raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="f1419-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1419-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f1419-116">Requirements</span></span>  
 <span data-ttu-id="f1419-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1419-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1419-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1419-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1419-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1419-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1419-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1419-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
