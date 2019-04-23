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
ms.openlocfilehash: dfbdbb389f9945ffeea649bcddd45bee8caf2496
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119990"
---
# <a name="efnstacktrace-function"></a><span data-ttu-id="cea98-102">Funzione _EFN_StackTrace</span><span class="sxs-lookup"><span data-stu-id="cea98-102">_EFN_StackTrace Function</span></span>
<span data-ttu-id="cea98-103">Fornisce una rappresentazione testuale di una traccia dello stack gestito e una matrice di record `CONTEXT`, uno per ogni transizione tra codice non gestito e gestito.</span><span class="sxs-lookup"><span data-stu-id="cea98-103">Provides a text representation of a managed stack trace and an array of `CONTEXT` records, one for each transition between unmanaged and managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cea98-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cea98-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="cea98-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cea98-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="cea98-106">[in] Il client in fase di debug.</span><span class="sxs-lookup"><span data-stu-id="cea98-106">[in] The client being debugged.</span></span>  
  
 `wszTextOut`  
 <span data-ttu-id="cea98-107">[out] La rappresentazione testuale dell'analisi dello stack.</span><span class="sxs-lookup"><span data-stu-id="cea98-107">[out] The text representation of the stack trace.</span></span>  
  
 `puiTextLength`  
 <span data-ttu-id="cea98-108">[out] Un puntatore al numero di caratteri in `wszTextOut`.</span><span class="sxs-lookup"><span data-stu-id="cea98-108">[out] A pointer to the number of characters in `wszTextOut`.</span></span>  
  
 `pTransitionContexts`  
 <span data-ttu-id="cea98-109">[out] Matrice di contesti di transizione.</span><span class="sxs-lookup"><span data-stu-id="cea98-109">[out] The array of transition contexts.</span></span>  
  
 `puiTransitionContextCount`  
 <span data-ttu-id="cea98-110">[out] Puntatore al numero di contesti di transizione nella matrice.</span><span class="sxs-lookup"><span data-stu-id="cea98-110">[out] A pointer to the number of transition contexts in the array.</span></span>  
  
 `uiSizeOfContext`  
 <span data-ttu-id="cea98-111">[in] Le dimensioni della struttura scelta.</span><span class="sxs-lookup"><span data-stu-id="cea98-111">[in] The size of the context structure.</span></span>  
  
 `Flags`  
 <span data-ttu-id="cea98-112">[in] Impostato su 0 o SOS_STACKTRACE_SHOWADDRESSES (0x01) per visualizzare il registro EBP e il puntatore dello stack invio (ESP) davanti a ogni `module!functionname` riga.</span><span class="sxs-lookup"><span data-stu-id="cea98-112">[in] Set to either 0 or SOS_STACKTRACE_SHOWADDRESSES (0x01) to show the EBP register and the enter stack pointer (ESP) in front of each `module!functionname` line.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cea98-113">Note</span><span class="sxs-lookup"><span data-stu-id="cea98-113">Remarks</span></span>  
 <span data-ttu-id="cea98-114">Il `_EFN_StackTrace` struttura può essere chiamata da un'interfaccia programmatica di WinDbg.</span><span class="sxs-lookup"><span data-stu-id="cea98-114">The `_EFN_StackTrace` structure can be called from a WinDbg programmatic interface.</span></span> <span data-ttu-id="cea98-115">I parametri vengono usati come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cea98-115">Parameters are used as follows:</span></span>  
  
-   <span data-ttu-id="cea98-116">Se `wszTextOut` è null e `puiTextLength` è diverso da null, la funzione restituisce la lunghezza della stringa in `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="cea98-116">If `wszTextOut` is null and `puiTextLength` is not null, the function returns the string length in `puiTextLength`.</span></span>  
  
-   <span data-ttu-id="cea98-117">Se `wszTextOut` è diverso da null, la funzione Archivia testo nel `wszTextOut` fino alla posizione indicata da `puiTextLength`.</span><span class="sxs-lookup"><span data-stu-id="cea98-117">If `wszTextOut` is not null, the function stores text in `wszTextOut` up to the location indicated by `puiTextLength`.</span></span> <span data-ttu-id="cea98-118">Restituita correttamente se si è verificato un spazio sufficiente nel buffer, o restituisce E_OUTOFMEMORY se il buffer non è sufficiente.</span><span class="sxs-lookup"><span data-stu-id="cea98-118">It returns successfully if there was enough room in the buffer, or returns E_OUTOFMEMORY if the buffer was not long enough.</span></span>  
  
-   <span data-ttu-id="cea98-119">La parte relativa alla transizione della funzione viene ignorato se `pTransitionContexts` e `puiTransitionContextCount` sono entrambi null.</span><span class="sxs-lookup"><span data-stu-id="cea98-119">The transition portion of the function is ignored if `pTransitionContexts` and `puiTransitionContextCount` are both null.</span></span> <span data-ttu-id="cea98-120">In questo caso, la funzione fornisce i chiamanti con output di testo dei soli nomi di funzione.</span><span class="sxs-lookup"><span data-stu-id="cea98-120">In this case, the function provides callers with text output of only the function names.</span></span>  
  
-   <span data-ttu-id="cea98-121">Se `pTransitionContexts` è null e `puiTransitionContextCount` è non null, la funzione restituisce il numero necessario di voci di contesto nella `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="cea98-121">If `pTransitionContexts` is null and `puiTransitionContextCount` is not null, the function returns the necessary number of context entries in `puiTransitionContextCount`.</span></span>  
  
-   <span data-ttu-id="cea98-122">Se `pTransitionContexts` è non null, la funzione considera come una matrice di strutture di lunghezza `puiTransitionContextCount`.</span><span class="sxs-lookup"><span data-stu-id="cea98-122">If `pTransitionContexts` is not null, the function treats it as an array of structures of length `puiTransitionContextCount`.</span></span> <span data-ttu-id="cea98-123">La dimensione della struttura viene specificata dalla `uiSizeOfContext`, e deve essere il valore pari [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) o `CONTEXT` per l'architettura.</span><span class="sxs-lookup"><span data-stu-id="cea98-123">The structure size is given by `uiSizeOfContext`, and must be the size of [SimpleContext](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) or `CONTEXT` for the architecture.</span></span>  
  
-   <span data-ttu-id="cea98-124">`wszTextOut` viene scritto nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="cea98-124">`wszTextOut` is written in the following format:</span></span>  
  
    ```  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
-   <span data-ttu-id="cea98-125">Se l'offset in esadecimale 0x0, non viene scritto alcun offset.</span><span class="sxs-lookup"><span data-stu-id="cea98-125">If the offset in hex is 0x0, no offset is written.</span></span>  
  
-   <span data-ttu-id="cea98-126">Se non vi è nessun codice gestito sul thread attualmente nel contesto, la funzione restituisce SOS_E_NOMANAGEDCODE.</span><span class="sxs-lookup"><span data-stu-id="cea98-126">If there is no managed code on the thread currently in context, the function returns SOS_E_NOMANAGEDCODE.</span></span>  
  
-   <span data-ttu-id="cea98-127">Il `Flags` parametro è 0 o SOS_STACKTRACE_SHOWADDRESSES visualizzare EBP ed ESP davanti a ogni `module!functionname` riga.</span><span class="sxs-lookup"><span data-stu-id="cea98-127">The `Flags` parameter is either 0 or SOS_STACKTRACE_SHOWADDRESSES to see EBP and ESP in front of each `module!functionname` line.</span></span> <span data-ttu-id="cea98-128">Per impostazione predefinita è 0.</span><span class="sxs-lookup"><span data-stu-id="cea98-128">By default, it is 0.</span></span>  
  
    ```  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a><span data-ttu-id="cea98-129">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cea98-129">Requirements</span></span>  
 <span data-ttu-id="cea98-130">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cea98-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cea98-131">**Intestazione:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="cea98-131">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="cea98-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cea98-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cea98-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cea98-133">See also</span></span>

- [<span data-ttu-id="cea98-134">Funzioni statiche globali di debug</span><span class="sxs-lookup"><span data-stu-id="cea98-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
