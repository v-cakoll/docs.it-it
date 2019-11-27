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
ms.openlocfilehash: 125a63638a41707b8eed918253cb1f93abb907eb
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434331"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="78fdc-102">Metodo IMetaDataEmit::GetSaveSize</span><span class="sxs-lookup"><span data-stu-id="78fdc-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="78fdc-103">Ottiene la dimensione binaria stimata dell'assembly e i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="78fdc-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78fdc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="78fdc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78fdc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="78fdc-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="78fdc-106">in Valore dell'enumerazione [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) che specifica se ottenere una dimensione accurata o approssimativa.</span><span class="sxs-lookup"><span data-stu-id="78fdc-106">[in] A value of the [CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="78fdc-107">Sono validi solo tre valori: cssAccurate, cssQuick e cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="78fdc-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="78fdc-108">cssAccurate restituisce le dimensioni esatte del salvataggio, ma richiede più tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="78fdc-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="78fdc-109">cssQuick restituisce una dimensione, riempita per la sicurezza, ma richiede meno tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="78fdc-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="78fdc-110">cssDiscardTransientCAs indica `GetSaveSize` che è possibile eliminare gli attributi personalizzati scartabili.</span><span class="sxs-lookup"><span data-stu-id="78fdc-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="78fdc-111">out Un puntatore alla dimensione necessaria per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="78fdc-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78fdc-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="78fdc-112">Remarks</span></span>  
 <span data-ttu-id="78fdc-113">`GetSaveSize` calcola lo spazio necessario, in byte, per salvare l'assembly e tutti i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="78fdc-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="78fdc-114">Una chiamata al metodo [IMetaDataEmit:: SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) emetterebbe questo numero di byte.</span><span class="sxs-lookup"><span data-stu-id="78fdc-114">(A call to the [IMetaDataEmit::SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="78fdc-115">Se il chiamante implementa l'interfaccia [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) (tramite [IMetaDataEmit:: FileHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) o [IMetaDataEmit:: merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` eseguirà due passaggi sui metadati per ottimizzarlo e comprimerlo.</span><span class="sxs-lookup"><span data-stu-id="78fdc-115">If the caller implements the [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="78fdc-116">In caso contrario, non viene eseguita alcuna ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="78fdc-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="78fdc-117">Se viene eseguita l'ottimizzazione, il primo passaggio Ordina semplicemente le strutture dei metadati per ottimizzare le prestazioni delle ricerche in fase di importazione.</span><span class="sxs-lookup"><span data-stu-id="78fdc-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="78fdc-118">Questo passaggio comporta in genere lo spostamento dei record, con l'effetto collaterale che i token conservati dallo strumento per riferimento futuro vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="78fdc-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="78fdc-119">I metadati non informano il chiamante di queste modifiche del token fino a dopo il secondo passaggio, tuttavia.</span><span class="sxs-lookup"><span data-stu-id="78fdc-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="78fdc-120">Nel secondo passaggio vengono eseguite diverse ottimizzazioni destinate a ridurre le dimensioni complessive dei metadati, ad esempio l'ottimizzazione (associazione anticipata) `mdTypeRef` e i token `mdMemberRef` quando il riferimento è a un tipo o a un membro dichiarato nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="78fdc-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="78fdc-121">In questo passaggio viene eseguito un altro ciclo di mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="78fdc-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="78fdc-122">Dopo questo passaggio, il motore dei metadati invia una notifica al chiamante, tramite la relativa interfaccia `IMapToken`, di tutti i valori di token modificati.</span><span class="sxs-lookup"><span data-stu-id="78fdc-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78fdc-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="78fdc-123">Requirements</span></span>  
 <span data-ttu-id="78fdc-124">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78fdc-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78fdc-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="78fdc-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="78fdc-126">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="78fdc-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="78fdc-127">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78fdc-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78fdc-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="78fdc-128">See also</span></span>

- [<span data-ttu-id="78fdc-129">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="78fdc-129">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="78fdc-130">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="78fdc-130">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
