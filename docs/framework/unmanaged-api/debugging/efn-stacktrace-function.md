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
ms.openlocfilehash: 39a249108d10e5dc382775378e2d6b84bba87356
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33408086"
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="d8519-102">Funzione _EFN_StackTrace</span><span class="sxs-lookup"><span data-stu-id="d8519-102">_EFN_StackTrace Function</span></span>
<span data-ttu-id="d8519-103">Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.</span><span class="sxs-lookup"><span data-stu-id="d8519-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8519-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d8519-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="d8519-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d8519-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="d8519-106">[in] Il client è in corso il debug.</span><span class="sxs-lookup"><span data-stu-id="d8519-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="d8519-107">[out] La rappresentazione testo dell'analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="d8519-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="d8519-108">[out] Un puntatore al numero di caratteri in `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="d8519-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="d8519-109">[out] Matrice di contesti di transizione.</span><span class="sxs-lookup"><span data-stu-id="d8519-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="d8519-110">[out] Puntatore al numero di contesti di transizione nella matrice.</span><span class="sxs-lookup"><span data-stu-id="d8519-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="d8519-111">[in] Le dimensioni della struttura di contesto.</span><span class="sxs-lookup"><span data-stu-id="d8519-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="d8519-112">[in] Impostato su 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) per visualizzare il registro EBP e il puntatore dello stack invio (ESP) all'inizio di ogni `module!functionname` riga.</span><span class="sxs-lookup"><span data-stu-id="d8519-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8519-113">Note</span><span class="sxs-lookup"><span data-stu-id="d8519-113">Remarks</span></span>  
 <span data-ttu-id="d8519-114">Il `_EFN_StackTrace` struttura può essere chiamata da un'interfaccia programmatica WinDbg.</span><span class="sxs-lookup"><span data-stu-id="d8519-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="d8519-115">I parametri vengono utilizzati come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="d8519-115">Parameters are used as follows:</span></span>  
  
-   <span data-ttu-id="d8519-116">Se `wszTextOut` è null e `puiTextLength` è non null, la funzione restituisce la lunghezza della stringa in `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="d8519-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
-   <span data-ttu-id="d8519-117">Se `wszTextOut` è non null, la funzione archivia il testo in `wszTextOut` fino alla posizione indicata da `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="d8519-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="d8519-118">Restituisce correttamente se non c'era disponibile spazio sufficiente nel buffer o restituisce E_OUTOFMEMORY se il buffer non è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="d8519-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
-   <span data-ttu-id="d8519-119">La parte relativa alla transizione della funzione viene ignorato se `pTransitionContexts` e `puiTransitionContextCount` sono entrambi null.</span><span class="sxs-lookup"><span data-stu-id="d8519-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="d8519-120">In questo caso, la funzione fornisce un output di testo di solo i nomi di funzione.</span><span class="sxs-lookup"><span data-stu-id="d8519-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
-   <span data-ttu-id="d8519-121">Se `pTransitionContexts` è null e `puiTransitionContextCount` è non null, la funzione restituisce il numero necessario di voci di contesto in `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="d8519-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
-   <span data-ttu-id="d8519-122">Se `pTransitionContexts` è non null, la funzione considera come una matrice di strutture con lunghezza `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="d8519-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="d8519-123">La dimensione della struttura viene fornita dalla `uiSizeOfContext`, e deve essere pari [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` per l'architettura.</span><span class="sxs-lookup"><span data-stu-id="d8519-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
-   <span data-ttu-id="d8519-124">`wszTextOut` viene scritto nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="d8519-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   <span data-ttu-id="d8519-125">Se l'offset in esadecimale è 0x0, viene scritto alcun offset.</span><span class="sxs-lookup"><span data-stu-id="d8519-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
-   <span data-ttu-id="d8519-126">Se non è presente nessun codice gestito sul thread attualmente in contesto, la funzione restituisce SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="d8519-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
-   <span data-ttu-id="d8519-127">Il `Flags` parametro è 0 o SOS_STACKTRACE_SHOWADDRESSES per visualizzare EBP ed ESP all'inizio di ogni `module!functionname` riga.</span><span class="sxs-lookup"><span data-stu-id="d8519-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="d8519-128">Per impostazione predefinita è 0.</span><span class="sxs-lookup"><span data-stu-id="d8519-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="d8519-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d8519-129">Requirements</span></span>  
 <span data-ttu-id="d8519-130">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8519-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8519-131">**Intestazione:** SOS_Stacktrace. h</span><span class="sxs-lookup"><span data-stu-id="d8519-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="d8519-132">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8519-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8519-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d8519-133">See Also</span></span>  
 [<span data-ttu-id="d8519-134">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="d8519-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
