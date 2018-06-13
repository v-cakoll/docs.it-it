---
title: Metodo IMetaDataEmit::GetSaveSize
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9a65f76aed00e2b848f8603f1fee4d6acc91f99
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449157"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="cb3ca-102">Metodo IMetaDataEmit::GetSaveSize</span><span class="sxs-lookup"><span data-stu-id="cb3ca-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="cb3ca-103">Ottiene le dimensioni stimate binaria dell'assembly e i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb3ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb3ca-104">Syntax</span></span>  
  
```  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb3ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb3ca-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="cb3ca-106">[in] Il valore di [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumerazione che specifica se ottenere le dimensioni precisa o approssimativa.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="cb3ca-107">Sono validi solo tre valori: cssAccurate, cssQuick e cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="cb3ca-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
-   <span data-ttu-id="cb3ca-108">cssAccurate restituisce la dimensione di salvataggio, ma richiede più tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
-   <span data-ttu-id="cb3ca-109">cssQuick restituisce una dimensione, vengono aggiunti per sicurezza, ma richiede meno tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
-   <span data-ttu-id="cb3ca-110">cssDiscardTransientCAs indica `GetSaveSize` che possono essere generate da subito scaricabile attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="cb3ca-111">[out] Puntatore alle dimensioni necessarie per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb3ca-112">Note</span><span class="sxs-lookup"><span data-stu-id="cb3ca-112">Remarks</span></span>  
 <span data-ttu-id="cb3ca-113">`GetSaveSize` Calcola lo spazio necessario, in byte, per salvare l'assembly e tutti i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="cb3ca-114">(Una chiamata al [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) metodo genererebbe questo numero di byte.)</span><span class="sxs-lookup"><span data-stu-id="cb3ca-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="cb3ca-115">Se il chiamante implementa il [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interfaccia (tramite [IMetaDataEmit:: SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` eseguirà due passaggi sui metadati per ottimizzare e la compressione.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="cb3ca-116">In caso contrario, non vengono eseguite ottimizzazioni.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="cb3ca-117">Se viene eseguita l'ottimizzazione, il primo passaggio ordina semplicemente le strutture di metadati per ottimizzare le prestazioni delle ricerche in fase di importazione.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="cb3ca-118">Questo passaggio in genere comporta lo spostamento di record, con un effetto secondario che non vengono invalidati token mantenuti dallo strumento per riferimento futuro.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="cb3ca-119">I metadati non informare il chiamante di queste modifiche token fino a dopo il secondo passaggio, tuttavia.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="cb3ca-120">Nel secondo passaggio, vengono eseguite diverse ottimizzazioni allo scopo di ridurre la dimensione complessiva dei metadati, ad esempio ottimizzazione (associazione anticipata) `mdTypeRef` e `mdMemberRef` token se il riferimento a un tipo o un membro dichiarato nel ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="cb3ca-121">In questo passaggio, si verifica un altro round mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="cb3ca-122">Dopo questo passaggio, il motore dei metadati notifica al chiamante, tramite il relativo `IMapToken` interfaccia, di qualsiasi modificato i valori del token.</span><span class="sxs-lookup"><span data-stu-id="cb3ca-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb3ca-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb3ca-123">Requirements</span></span>  
 <span data-ttu-id="cb3ca-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb3ca-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb3ca-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cb3ca-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cb3ca-126">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="cb3ca-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cb3ca-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb3ca-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb3ca-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb3ca-128">See Also</span></span>  
 [<span data-ttu-id="cb3ca-129">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="cb3ca-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="cb3ca-130">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="cb3ca-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
