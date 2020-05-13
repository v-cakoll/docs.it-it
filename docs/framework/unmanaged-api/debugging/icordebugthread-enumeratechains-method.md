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
ms.openlocfilehash: 711fccd65379bc3e5e178869e7220dd84fd07fbe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379707"
---
# <a name="icordebugthreadenumeratechains-method"></a><span data-ttu-id="f227a-102">Metodo ICorDebugThread::EnumerateChains</span><span class="sxs-lookup"><span data-stu-id="f227a-102">ICorDebugThread::EnumerateChains Method</span></span>
<span data-ttu-id="f227a-103">Ottiene un puntatore a interfaccia a un enumeratore ICorDebugChainEnum che contiene tutte le catene dello stack in questo oggetto ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="f227a-103">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f227a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f227a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateChains (  
    [out] ICorDebugChainEnum **ppChains  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f227a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f227a-105">Parameters</span></span>  
 `ppChains`  
 <span data-ttu-id="f227a-106">out Puntatore all'indirizzo di un `ICorDebugChainEnum` oggetto che consente l'enumerazione di tutte le catene dello stack nel thread, a partire dalla catena attiva (ovvero la più recente).</span><span class="sxs-lookup"><span data-stu-id="f227a-106">[out] A pointer to the address of an `ICorDebugChainEnum` object that allows enumeration of all the stack chains in this thread, starting at the active (that is, the most recent) chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f227a-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f227a-107">Remarks</span></span>  
 <span data-ttu-id="f227a-108">La catena di stack rappresenta lo stack di chiamate fisico per il thread.</span><span class="sxs-lookup"><span data-stu-id="f227a-108">The stack chain represents the physical call stack for the thread.</span></span> <span data-ttu-id="f227a-109">Nelle circostanze seguenti viene creato un limite della catena dello stack:</span><span class="sxs-lookup"><span data-stu-id="f227a-109">The following circumstances create a stack chain boundary:</span></span>  
  
- <span data-ttu-id="f227a-110">Una transizione da gestita a non gestita o non gestita.</span><span class="sxs-lookup"><span data-stu-id="f227a-110">A managed-to-unmanaged or unmanaged-to-managed transition.</span></span>  
  
- <span data-ttu-id="f227a-111">Cambio di contesto.</span><span class="sxs-lookup"><span data-stu-id="f227a-111">A context switch.</span></span>  
  
- <span data-ttu-id="f227a-112">Hijack del debugger di un thread utente.</span><span class="sxs-lookup"><span data-stu-id="f227a-112">A debugger hijacking of a user thread.</span></span>  
  
 <span data-ttu-id="f227a-113">Nel caso semplice per un thread che esegue codice puramente gestito in un unico contesto, esiste una corrispondenza uno-a-uno tra i thread e le catene dello stack.</span><span class="sxs-lookup"><span data-stu-id="f227a-113">In the simple case for a thread that is running purely managed code in a single context, a one-to-one correspondence will exist between threads and stack chains.</span></span>  
  
 <span data-ttu-id="f227a-114">Un debugger potrebbe voler ridisporre gli stack di chiamate fisici di tutti i thread in stack di chiamate logiche.</span><span class="sxs-lookup"><span data-stu-id="f227a-114">A debugger may want to rearrange the physical call stacks of all threads into logical call stacks.</span></span> <span data-ttu-id="f227a-115">Questo comporterebbe l'ordinamento di tutte le catene dei thread in base alle relazioni chiamante/chiamato e al loro raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="f227a-115">This would involve sorting all the threads' chains by their caller/callee relationships and regrouping them.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f227a-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f227a-116">Requirements</span></span>  
 <span data-ttu-id="f227a-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f227a-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f227a-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f227a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f227a-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f227a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f227a-120">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f227a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
