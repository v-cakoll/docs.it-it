---
title: Metodo ICorDebugModule2::ApplyChanges
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ApplyChanges
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type:
- apiref
ms.openlocfilehash: 99824e9a7fd759fb30bfa377156fc28eb934a2b4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212217"
---
# <a name="icordebugmodule2applychanges-method"></a><span data-ttu-id="cf34a-102">Metodo ICorDebugModule2::ApplyChanges</span><span class="sxs-lookup"><span data-stu-id="cf34a-102">ICorDebugModule2::ApplyChanges Method</span></span>
<span data-ttu-id="cf34a-103">Applica le modifiche nei metadati e le modifiche nel codice MSIL (Microsoft Intermediate Language) al processo in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="cf34a-103">Applies the changes in the metadata and the changes in the Microsoft intermediate language (MSIL) code to the running process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf34a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cf34a-104">Syntax</span></span>  
  
```cpp  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf34a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cf34a-105">Parameters</span></span>  
 `cbMetadata`  
 <span data-ttu-id="cf34a-106">in Dimensione, in byte, dei metadati delta.</span><span class="sxs-lookup"><span data-stu-id="cf34a-106">[in] Size, in bytes, of the delta metadata.</span></span>  
  
 `pbMetadata`  
 <span data-ttu-id="cf34a-107">in Buffer contenente i metadati delta.</span><span class="sxs-lookup"><span data-stu-id="cf34a-107">[in] Buffer that contains the delta metadata.</span></span> <span data-ttu-id="cf34a-108">L'indirizzo del buffer viene restituito dal metodo [IMetaDataEmit2:: SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cf34a-108">The address of the buffer is returned from the [IMetaDataEmit2::SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md) method.</span></span>  
  
 <span data-ttu-id="cf34a-109">Gli indirizzi virtuali relativi (RVA) nei metadati devono essere relativi all'inizio del codice MSIL.</span><span class="sxs-lookup"><span data-stu-id="cf34a-109">The relative virtual addresses (RVAs) in the metadata should be relative to the start of the MSIL code.</span></span>  
  
 `cbIL`  
 <span data-ttu-id="cf34a-110">in Dimensione, in byte, del codice MSIL delta.</span><span class="sxs-lookup"><span data-stu-id="cf34a-110">[in] Size, in bytes, of the delta MSIL code.</span></span>  
  
 `pbIL`  
 <span data-ttu-id="cf34a-111">in Buffer che contiene il codice MSIL aggiornato.</span><span class="sxs-lookup"><span data-stu-id="cf34a-111">[in] Buffer that contains the updated MSIL code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf34a-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cf34a-112">Remarks</span></span>  
 <span data-ttu-id="cf34a-113">Il `pbMetadata` parametro è in un formato di metadati delta speciale (come output di [IMetaDataEmit2:: SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md)).</span><span class="sxs-lookup"><span data-stu-id="cf34a-113">The `pbMetadata` parameter is in a special delta metadata format (as output by [IMetaDataEmit2::SaveDeltaToMemory](../metadata/imetadataemit2-savedeltatomemory-method.md)).</span></span> <span data-ttu-id="cf34a-114">`pbMetadata`accetta i metadati precedenti come base e descrive le singole modifiche da applicare a tale base.</span><span class="sxs-lookup"><span data-stu-id="cf34a-114">`pbMetadata` takes previous metadata as a base and describes individual changes to apply to that base.</span></span>  
  
 <span data-ttu-id="cf34a-115">Al contrario, il `pbIL[` parametro] contiene il nuovo codice MSIL per il metodo aggiornato ed è destinato a sostituire completamente il codice MSIL precedente per tale metodo</span><span class="sxs-lookup"><span data-stu-id="cf34a-115">In contrast, the `pbIL[`] parameter contains the new MSIL for the updated method, and is meant to completely replace the previous MSIL for that method</span></span>  
  
 <span data-ttu-id="cf34a-116">Quando il codice MSIL delta e i metadati sono stati creati nella memoria del debugger, il debugger chiama `ApplyChanges` per inviare le modifiche nel Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="cf34a-116">When the delta MSIL and the metadata have been created in the debugger’s memory, the debugger calls `ApplyChanges` to send the changes into the common language runtime (CLR).</span></span> <span data-ttu-id="cf34a-117">Il runtime aggiorna le tabelle di metadati, inserisce il nuovo codice MSIL nel processo e configura una compilazione JIT (just-in-Time) del nuovo MSIL.</span><span class="sxs-lookup"><span data-stu-id="cf34a-117">The runtime updates its metadata tables, places the new MSIL into the process, and sets up a just-in-time (JIT) compilation of the new MSIL.</span></span> <span data-ttu-id="cf34a-118">Una volta applicate le modifiche, il debugger deve chiamare [IMetaDataEmit2:: ResetENCLog](../metadata/imetadataemit2-resetenclog-method.md) per prepararsi alla successiva sessione di modifica.</span><span class="sxs-lookup"><span data-stu-id="cf34a-118">When the changes have been applied, the debugger should call [IMetaDataEmit2::ResetENCLog](../metadata/imetadataemit2-resetenclog-method.md) to prepare for the next editing session.</span></span> <span data-ttu-id="cf34a-119">Il debugger può quindi continuare il processo.</span><span class="sxs-lookup"><span data-stu-id="cf34a-119">The debugger may then continue the process.</span></span>  
  
 <span data-ttu-id="cf34a-120">Ogni volta che il debugger chiama `ApplyChanges` su un modulo con metadati delta, deve chiamare anche il metodo [IMetaDataEmit:: ApplyEditAndContinue](../metadata/imetadataemit-applyeditandcontinue-method.md) con gli stessi metadati delta in tutte le copie dei metadati del modulo, tranne la copia utilizzata per emettere le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cf34a-120">Whenever the debugger calls `ApplyChanges` on a module that has delta metadata, it should also call [IMetaDataEmit::ApplyEditAndContinue](../metadata/imetadataemit-applyeditandcontinue-method.md) with the same delta metadata on all of its copies of that module’s metadata except for the copy used to emit the changes.</span></span> <span data-ttu-id="cf34a-121">Se una copia dei metadati diventa in qualche modo non sincronizzata con i metadati effettivi, il debugger può sempre eliminare la copia e ottenere una nuova copia.</span><span class="sxs-lookup"><span data-stu-id="cf34a-121">If a copy of the metadata somehow becomes out-of-sync with the actual metadata, the debugger can always throw away that copy and obtain a new copy.</span></span>  
  
 <span data-ttu-id="cf34a-122">Se il `ApplyChanges` metodo ha esito negativo, la sessione di debug si trova in uno stato non valido e deve essere riavviata.</span><span class="sxs-lookup"><span data-stu-id="cf34a-122">If the `ApplyChanges` method fails, the debug session is in an invalid state and must be restarted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf34a-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cf34a-123">Requirements</span></span>  
 <span data-ttu-id="cf34a-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf34a-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf34a-125">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf34a-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf34a-126">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf34a-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf34a-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf34a-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
