---
title: Metodo ICorDebugThread::EnumerateChains
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.EnumerateChains
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::EnumerateChains
helpviewer_keywords:
- EnumerateChains method [.NET Framework debugging]
- ICorDebugThread::EnumerateChains method [.NET Framework debugging]
ms.assetid: ec00bc21-117e-4acd-9301-2cfafd5be8d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 67b5a5da0a0053536ab4331e9d134464a4330500
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="54dea-102">Metodo ICorDebugThread::EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="54dea-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="54dea-103">Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum contenente tutte le catene dello stack di questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="54dea-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54dea-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="54dea-104">Syntax</span></span>  
  
```  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54dea-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="54dea-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="54dea-106">[out] Un puntatore all'indirizzo di un `ICorDebugChainEnum` oggetto che consente l'enumerazione dello stack di concatenato in questo thread, a partire da quella attiva (ovvero, la più recente).</span><span class="sxs-lookup"><span data-stu-id="54dea-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54dea-107">Note</span><span class="sxs-lookup"><span data-stu-id="54dea-107">Remarks</span></span>  
 <span data-ttu-id="54dea-108">La catena dello stack rappresenta lo stack di chiamate fisico per il thread.</span><span class="sxs-lookup"><span data-stu-id="54dea-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="54dea-109">Le seguenti circostanze creare un limite di catena dello stack:</span><span class="sxs-lookup"><span data-stu-id="54dea-109">The following circumstances create a stack chain boundary:</span></span>  
  
-   <span data-ttu-id="54dea-110">Una transizione da gestito o non gestito a gestito.</span><span class="sxs-lookup"><span data-stu-id="54dea-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
-   <span data-ttu-id="54dea-111">Un cambio di contesto.</span><span class="sxs-lookup"><span data-stu-id="54dea-111">A context switch.</span></span>  
  
-   <span data-ttu-id="54dea-112">Un Hijack di un thread di utente del debugger.</span><span class="sxs-lookup"><span data-stu-id="54dea-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="54dea-113">Nel caso più semplice per un thread che esegue codice gestito esclusivamente in un contesto singolo, sarà presente una corrispondenza tra thread e catene dello stack.</span><span class="sxs-lookup"><span data-stu-id="54dea-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="54dea-114">Un debugger potrebbe essere necessario modificare gli stack di chiamate fisico di tutti i thread in stack di chiamata logico.</span><span class="sxs-lookup"><span data-stu-id="54dea-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="54dea-115">Ciò comporta l'ordinamento di catene di tutti i thread per le relative relazioni chiamante/chiamato e il relativo raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="54dea-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54dea-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="54dea-116">Requirements</span></span>  
 <span data-ttu-id="54dea-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54dea-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54dea-118">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="54dea-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54dea-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54dea-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54dea-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54dea-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
