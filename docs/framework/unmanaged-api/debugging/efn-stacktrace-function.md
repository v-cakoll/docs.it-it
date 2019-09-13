---
title: Funzione _EFN_StackTrace
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9035d9a53c4b0c8822b79e641aef092b4a48c418
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70895039"
---
# <a name="_efn_stacktrace-function"></a><span data-ttu-id="fe46f-102">\_AAPN\_(funzione StackTrace)</span><span class="sxs-lookup"><span data-stu-id="fe46f-102">\_EFN\_StackTrace Function</span></span>
<span data-ttu-id="fe46f-103">Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.</span><span class="sxs-lookup"><span data-stu-id="fe46f-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe46f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fe46f-104">Syntax</span></span>  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe46f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fe46f-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="fe46f-106">in Client di cui è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="fe46f-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="fe46f-107">out Rappresentazione testuale della traccia dello stack.</span><span class="sxs-lookup"><span data-stu-id="fe46f-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="fe46f-108">out Puntatore al numero di caratteri in `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="fe46f-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="fe46f-109">out Matrice di contesti di transizione.</span><span class="sxs-lookup"><span data-stu-id="fe46f-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="fe46f-110">out Puntatore al numero di contesti di transizione nella matrice.</span><span class="sxs-lookup"><span data-stu-id="fe46f-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="fe46f-111">in Dimensione della struttura del contesto.</span><span class="sxs-lookup"><span data-stu-id="fe46f-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="fe46f-112">in Impostare su 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) per visualizzare il registro EBP e il puntatore di stack di immissione (ESP) davanti a ogni `module!functionname` riga.</span><span class="sxs-lookup"><span data-stu-id="fe46f-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe46f-113">Note</span><span class="sxs-lookup"><span data-stu-id="fe46f-113">Remarks</span></span>  
 <span data-ttu-id="fe46f-114">La `_EFN_StackTrace` struttura può essere chiamata da un'interfaccia WinDbg a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="fe46f-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="fe46f-115">I parametri vengono usati come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="fe46f-115">Parameters are used as follows:</span></span>  
  
- <span data-ttu-id="fe46f-116">Se `wszTextOut` è null e `puiTextLength` non è null, la funzione restituisce la lunghezza della stringa `puiTextLength`in.</span><span class="sxs-lookup"><span data-stu-id="fe46f-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
- <span data-ttu-id="fe46f-117">Se `wszTextOut` non è null, la funzione archivia il `wszTextOut` testo fino alla posizione indicata da `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="fe46f-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="fe46f-118">Restituisce correttamente se lo spazio disponibile nel buffer è sufficiente oppure restituisce E_OUTOFMEMORY se il buffer non era sufficientemente lungo.</span><span class="sxs-lookup"><span data-stu-id="fe46f-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
- <span data-ttu-id="fe46f-119">La parte della funzione di transizione viene ignorata `pTransitionContexts` se `puiTransitionContextCount` e sono entrambi null.</span><span class="sxs-lookup"><span data-stu-id="fe46f-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="fe46f-120">In questo caso, la funzione fornisce ai chiamanti l'output di testo solo dei nomi di funzione.</span><span class="sxs-lookup"><span data-stu-id="fe46f-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
- <span data-ttu-id="fe46f-121">Se `pTransitionContexts` è null e `puiTransitionContextCount` non è null, la funzione restituisce il numero necessario di voci di contesto `puiTransitionContextCount`in.</span><span class="sxs-lookup"><span data-stu-id="fe46f-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
- <span data-ttu-id="fe46f-122">Se `pTransitionContexts` non è null, la funzione lo considera come una matrice di strutture di lunghezza `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="fe46f-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="fe46f-123">Le dimensioni della struttura sono fornite `uiSizeOfContext`da e devono essere le dimensioni di [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` per l'architettura.</span><span class="sxs-lookup"><span data-stu-id="fe46f-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
- <span data-ttu-id="fe46f-124">`wszTextOut`viene scritto nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="fe46f-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- <span data-ttu-id="fe46f-125">Se l'offset in esadecimale è 0x0, non viene scritto alcun offset.</span><span class="sxs-lookup"><span data-stu-id="fe46f-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
- <span data-ttu-id="fe46f-126">Se non è presente codice gestito nel thread attualmente nel contesto, la funzione restituisce SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="fe46f-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
- <span data-ttu-id="fe46f-127">Il `Flags` parametro è 0 o SOS_STACKTRACE_SHOWADDRESSES per vedere EBP ed ESP davanti a ogni `module!functionname` riga.</span><span class="sxs-lookup"><span data-stu-id="fe46f-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="fe46f-128">Per impostazione predefinita, è 0.</span><span class="sxs-lookup"><span data-stu-id="fe46f-128">By default, it is 0.</span></span>  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="fe46f-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fe46f-129">Requirements</span></span>  
 <span data-ttu-id="fe46f-130">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe46f-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe46f-131">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="fe46f-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="fe46f-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe46f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe46f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe46f-133">See also</span></span>

- [<span data-ttu-id="fe46f-134">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="fe46f-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
