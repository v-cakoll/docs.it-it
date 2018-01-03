---
title: Metodo ICorDebugModule2::ApplyChanges
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.ApplyChanges
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4855b7a42d471304d000465a0437f29bdff05494
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="d34f4-102">Metodo ICorDebugModule2::ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="d34f4-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="d34f4-103">Applica le modifiche nei metadati e le modifiche nel codice Microsoft intermediate language (MSIL) per il processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d34f4-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d34f4-104">Syntax</span></span>  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d34f4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d34f4-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="d34f4-106">[in] Dimensione, in byte, dei metadati delta.</span><span class="sxs-lookup"><span data-stu-id="d34f4-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="d34f4-107">[in] Buffer che contiene i metadati delta.</span><span class="sxs-lookup"><span data-stu-id="d34f4-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="d34f4-108">Viene restituito l'indirizzo del buffer dal [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="d34f4-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="d34f4-109">Gli indirizzi virtuali relativi (RVA) nei metadati devono essere relativo all'inizio del codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="d34f4-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="d34f4-110">[in] Dimensione, in byte, del codice MSIL delta.</span><span class="sxs-lookup"><span data-stu-id="d34f4-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="d34f4-111">[in] Buffer che contiene il codice MSIL aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d34f4-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d34f4-112">Note</span><span class="sxs-lookup"><span data-stu-id="d34f4-112">Remarks</span></span>  
 <span data-ttu-id="d34f4-113">Il `pbMetadata` parametro è in un formato di metadati delta speciale (come output da [IMetaDataEmit2:: SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="d34f4-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="d34f4-114">`pbMetadata`accetta i metadati precedenti come base e descrive le singole modifiche da applicare alla base.</span><span class="sxs-lookup"><span data-stu-id="d34f4-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="d34f4-115">Al contrario, il `pbIL[`] parametro contiene il nuovo codice MSIL per il metodo aggiornato ed è concepito per sostituire completamente il precedente codice MSIL per il metodo</span><span class="sxs-lookup"><span data-stu-id="d34f4-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="d34f4-116">Quando il codice MSIL delta e i metadati sono stati creati in memoria del debugger, il debugger chiama `ApplyChanges` per inviare le modifiche in common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d34f4-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="d34f4-117">Il runtime aggiorna le relative tabelle di metadati, inserisce il codice MSIL di nuovo il processo e consente di impostare una compilazione di just-in-time (JIT) di tale codice.</span><span class="sxs-lookup"><span data-stu-id="d34f4-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="d34f4-118">Una volta applicate le modifiche, il debugger deve chiamare [IMetaDataEmit2:: ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) per preparare per la sessione di modifica successiva.</span><span class="sxs-lookup"><span data-stu-id="d34f4-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="d34f4-119">Il debugger può quindi continuare il processo.</span><span class="sxs-lookup"><span data-stu-id="d34f4-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="d34f4-120">Ogni volta che il debugger chiama `ApplyChanges` su un modulo che contiene metadati delta, deve anche chiamare [IMetaDataEmit:: ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) con gli stessi metadati delta su tutte le copie dei metadati del modulo, ad eccezione della copia utilizzato per generare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="d34f4-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="d34f4-121">In caso di una copia dei metadati in qualche modo di sincronizzazione con i metadati effettivi, il debugger può sempre eliminare tale copia e ottenere una nuova copia.</span><span class="sxs-lookup"><span data-stu-id="d34f4-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="d34f4-122">Se il `ApplyChanges` metodo ha esito negativo, il debug della sessione è in uno stato non valido e deve essere riavviata.</span><span class="sxs-lookup"><span data-stu-id="d34f4-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d34f4-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d34f4-123">Requirements</span></span>  
 <span data-ttu-id="d34f4-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d34f4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d34f4-125">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="d34f4-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d34f4-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d34f4-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d34f4-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d34f4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
