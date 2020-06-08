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
ms.openlocfilehash: 0a283c837e23ab1aafd3545df1dfe8a267de0557
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501287"
---
# <a name="imetadataemitgetsavesize-method"></a><span data-ttu-id="caecb-102">Metodo IMetaDataEmit::GetSaveSize</span><span class="sxs-lookup"><span data-stu-id="caecb-102">IMetaDataEmit::GetSaveSize Method</span></span>
<span data-ttu-id="caecb-103">Ottiene la dimensione binaria stimata dell'assembly e i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="caecb-103">Gets the estimated binary size of the assembly and its metadata in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caecb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="caecb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="caecb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="caecb-105">Parameters</span></span>  
 `fSave`  
 <span data-ttu-id="caecb-106">in Valore dell'enumerazione [CorSaveSize](corsavesize-enumeration.md) che specifica se ottenere una dimensione accurata o approssimativa.</span><span class="sxs-lookup"><span data-stu-id="caecb-106">[in] A value of the [CorSaveSize](corsavesize-enumeration.md) enumeration that specifies whether to get an accurate or approximate size.</span></span> <span data-ttu-id="caecb-107">Sono validi solo tre valori: cssAccurate, cssQuick e cssDiscardTransientCAs:</span><span class="sxs-lookup"><span data-stu-id="caecb-107">Only three values are valid: cssAccurate, cssQuick, and cssDiscardTransientCAs:</span></span>  
  
- <span data-ttu-id="caecb-108">cssAccurate restituisce le dimensioni esatte del salvataggio, ma richiede più tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="caecb-108">cssAccurate returns the exact save size but takes longer to calculate.</span></span>  
  
- <span data-ttu-id="caecb-109">cssQuick restituisce una dimensione, riempita per la sicurezza, ma richiede meno tempo per il calcolo.</span><span class="sxs-lookup"><span data-stu-id="caecb-109">cssQuick returns a size, padded for safety, but takes less time to calculate.</span></span>  
  
- <span data-ttu-id="caecb-110">cssDiscardTransientCAs indica `GetSaveSize` che è possibile eliminare gli attributi personalizzati scartabili.</span><span class="sxs-lookup"><span data-stu-id="caecb-110">cssDiscardTransientCAs tells `GetSaveSize` that it can throw away discardable custom attributes.</span></span>  
  
 `pdwSaveSize`  
 <span data-ttu-id="caecb-111">out Un puntatore alla dimensione necessaria per salvare il file.</span><span class="sxs-lookup"><span data-stu-id="caecb-111">[out] A pointer to the size that is required to save the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="caecb-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="caecb-112">Remarks</span></span>  
 <span data-ttu-id="caecb-113">`GetSaveSize`calcola lo spazio necessario, in byte, per salvare l'assembly e tutti i relativi metadati nell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="caecb-113">`GetSaveSize` calculates the space required, in bytes, to save the assembly and all its metadata in the current scope.</span></span> <span data-ttu-id="caecb-114">Una chiamata al metodo [IMetaDataEmit:: SaveToStream](imetadataemit-savetostream-method.md) emetterebbe questo numero di byte.</span><span class="sxs-lookup"><span data-stu-id="caecb-114">(A call to the [IMetaDataEmit::SaveToStream](imetadataemit-savetostream-method.md) method would emit this number of bytes.)</span></span>  
  
 <span data-ttu-id="caecb-115">Se il chiamante implementa l'interfaccia [IMapToken](imaptoken-interface.md) (tramite [IMetaDataEmit:: FileHandler](imetadataemit-sethandler-method.md) o [IMetaDataEmit:: merge](imetadataemit-merge-method.md)), eseguirà `GetSaveSize` due passaggi sui metadati per ottimizzarlo e comprimerlo.</span><span class="sxs-lookup"><span data-stu-id="caecb-115">If the caller implements the [IMapToken](imaptoken-interface.md) interface (through [IMetaDataEmit::SetHandler](imetadataemit-sethandler-method.md) or [IMetaDataEmit::Merge](imetadataemit-merge-method.md)), `GetSaveSize` will perform two passes over the metadata to optimize and compress it.</span></span> <span data-ttu-id="caecb-116">In caso contrario, non viene eseguita alcuna ottimizzazione.</span><span class="sxs-lookup"><span data-stu-id="caecb-116">Otherwise, no optimizations are performed.</span></span>  
  
 <span data-ttu-id="caecb-117">Se viene eseguita l'ottimizzazione, il primo passaggio Ordina semplicemente le strutture dei metadati per ottimizzare le prestazioni delle ricerche in fase di importazione.</span><span class="sxs-lookup"><span data-stu-id="caecb-117">If optimization is performed, the first pass simply sorts the metadata structures to tune the performance of import-time searches.</span></span> <span data-ttu-id="caecb-118">Questo passaggio comporta in genere lo spostamento dei record, con l'effetto collaterale che i token conservati dallo strumento per riferimento futuro vengono invalidati.</span><span class="sxs-lookup"><span data-stu-id="caecb-118">This step typically results in moving records around, with the side effect that tokens retained by the tool for future reference are invalidated.</span></span> <span data-ttu-id="caecb-119">I metadati non informano il chiamante di queste modifiche del token fino a dopo il secondo passaggio, tuttavia.</span><span class="sxs-lookup"><span data-stu-id="caecb-119">The metadata does not inform the caller of these token changes until after the second pass, however.</span></span> <span data-ttu-id="caecb-120">Nel secondo passaggio vengono eseguite diverse ottimizzazioni destinate a ridurre le dimensioni complessive dei metadati, ad esempio l'ottimizzazione (associazione anticipata) `mdTypeRef` e `mdMemberRef` i token quando il riferimento è a un tipo o a un membro dichiarato nell'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="caecb-120">In the second pass, various optimizations are performed that are intended to reduce the overall size of the metadata, such as optimizing away (early binding) `mdTypeRef` and `mdMemberRef` tokens when the reference is to a type or member that is declared in the current metadata scope.</span></span> <span data-ttu-id="caecb-121">In questo passaggio viene eseguito un altro ciclo di mapping dei token.</span><span class="sxs-lookup"><span data-stu-id="caecb-121">In this pass, another round of token mapping occurs.</span></span> <span data-ttu-id="caecb-122">Dopo questo passaggio, il motore dei metadati invia una notifica al chiamante, tramite la relativa `IMapToken` interfaccia, di tutti i valori di token modificati.</span><span class="sxs-lookup"><span data-stu-id="caecb-122">After this pass, the metadata engine notifies the caller, through its `IMapToken` interface, of any changed token values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caecb-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="caecb-123">Requirements</span></span>  
 <span data-ttu-id="caecb-124">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caecb-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caecb-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="caecb-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="caecb-126">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="caecb-126">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caecb-127">**Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caecb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caecb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="caecb-128">See also</span></span>

- [<span data-ttu-id="caecb-129">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="caecb-129">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="caecb-130">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="caecb-130">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
