---
title: Metodo IMetaDataEmit::GetSaveSize
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7585f6adbca97b252fdad90276b0cd422d32c04a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="b13a8-102">Metodo IMetaDataEmit::GetSaveSize</span><span class="sxs-lookup"><span data-stu-id="b13a8-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="b13a8-103">Ottiene le dimensioni stimate binaria dell'assembly e i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="b13a8-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b13a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b13a8-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b13a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b13a8-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="b13a8-106">[in] Il valore di [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumerazione che specifica se ottenere le dimensioni precisa o approssimativa.</span><span class="sxs-lookup"><span data-stu-id="b13a8-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="b13a8-107">Sono validi solo tre valori: cssAccurate, cssQuick e cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="b13a8-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="b13a8-108">cssAccurate restituisce la dimensione di salvataggio, ma richiede più tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="b13a8-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="b13a8-109">cssQuick restituisce una dimensione, vengono aggiunti per sicurezza, ma richiede meno tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="b13a8-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="b13a8-110">cssDiscardTransientCAs indica `GetSaveSize` che possono essere generate da subito scaricabile attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="b13a8-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="b13a8-111">[out] Puntatore alle dimensioni necessarie per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="b13a8-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b13a8-112">Note</span><span class="sxs-lookup"><span data-stu-id="b13a8-112">Remarks</span></span>  
 <span data-ttu-id="b13a8-113">`GetSaveSize`Calcola lo spazio, espressa in byte, necessario per salvare l'assembly e tutti i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="b13a8-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="b13a8-114">(Una chiamata al [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) metodo genererebbe questo numero di byte.)</span><span class="sxs-lookup"><span data-stu-id="b13a8-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="b13a8-115">Se il chiamante implementa il [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaccia (tramite [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` eseguirà due passaggi sui metadati per ottimizzare e la compressione.</span><span class="sxs-lookup"><span data-stu-id="b13a8-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="b13a8-116">In caso contrario, non vengono eseguite ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="b13a8-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="b13a8-117">Se viene eseguita l'ottimizzazione, il primo passaggio ordina semplicemente le strutture di metadati per ottimizzare le prestazioni delle ricerche in fase di importazione.</span><span class="sxs-lookup"><span data-stu-id="b13a8-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="b13a8-118">Questo passaggio in genere comporta lo spostamento di record, con un effetto secondario che non vengono invalidati token mantenuti dallo strumento per riferimento futuro.</span><span class="sxs-lookup"><span data-stu-id="b13a8-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="b13a8-119">I metadati non informare il chiamante di queste modifiche token fino a dopo il secondo passaggio, tuttavia.</span><span class="sxs-lookup"><span data-stu-id="b13a8-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="b13a8-120">Nel secondo passaggio, vengono eseguite diverse ottimizzazioni allo scopo di ridurre la dimensione complessiva dei metadati, ad esempio ottimizzazione (associazione anticipata) `mdTypeRef` e `mdMemberRef` token se il riferimento a un tipo o un membro dichiarato nel ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="b13a8-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="b13a8-121">In questo passaggio, si verifica un altro round mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="b13a8-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="b13a8-122">Dopo questo passaggio, il motore dei metadati notifica al chiamante, tramite il relativo `IMapToken` interfaccia, di qualsiasi modificato i valori del token.</span><span class="sxs-lookup"><span data-stu-id="b13a8-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b13a8-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b13a8-123">Requirements</span></span>  
 <span data-ttu-id="b13a8-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b13a8-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b13a8-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b13a8-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b13a8-126">**Libreria:** usata come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b13a8-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b13a8-127">**Versioni di .NET framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b13a8-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13a8-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b13a8-128">See Also</span></span>  
 [<span data-ttu-id="b13a8-129">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b13a8-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="b13a8-130">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b13a8-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
