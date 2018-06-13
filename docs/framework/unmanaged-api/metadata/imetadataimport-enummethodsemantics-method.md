---
title: Metodo IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00a28e0f7ab03af8d5f2fc0dda5274f9aaa4dca2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449095"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="97c0b-102">Metodo IMetaDataImport::EnumMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="97c0b-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="97c0b-103">Enumera le proprietà e gli eventi di modifica delle proprietà a cui è correlato il metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="97c0b-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97c0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97c0b-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97c0b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97c0b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="97c0b-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="97c0b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="97c0b-107">Per la prima chiamata di questo metodo deve essere NULL.</span><span class="sxs-lookup"><span data-stu-id="97c0b-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="97c0b-108">[in] Token MethodDef che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="97c0b-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="97c0b-109">[out] Matrice utilizzata per archiviare gli eventi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="97c0b-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="97c0b-110">[in] Dimensione massima della matrice `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="97c0b-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="97c0b-111">[out] Il numero di proprietà o eventi restituiti `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="97c0b-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97c0b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="97c0b-112">Return Value</span></span>  
  
|<span data-ttu-id="97c0b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="97c0b-113">HRESULT</span></span>|<span data-ttu-id="97c0b-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97c0b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="97c0b-115">`EnumMethodSemantics` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="97c0b-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="97c0b-116">Non esistono eventi o proprietà da enumerare.</span><span class="sxs-lookup"><span data-stu-id="97c0b-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="97c0b-117">In tal caso, `pcEventProp` è zero.</span><span class="sxs-lookup"><span data-stu-id="97c0b-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97c0b-118">Note</span><span class="sxs-lookup"><span data-stu-id="97c0b-118">Remarks</span></span>  
 <span data-ttu-id="97c0b-119">Definiscono molti tipi di common language runtime *proprietà* `Changed` gli eventi e `On` *proprietà* `Changed` metodi correlati alle rispettive proprietà.</span><span class="sxs-lookup"><span data-stu-id="97c0b-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="97c0b-120">Ad esempio, il <xref:System.Windows.Forms.Control?displayProperty=nameWithType> tipo definisce un <xref:System.Windows.Forms.Control.Font%2A> proprietà, un <xref:System.Windows.Forms.Control.FontChanged> evento e un <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="97c0b-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="97c0b-121">Il metodo di funzione di accesso set del <xref:System.Windows.Forms.Control.Font%2A> chiamate a proprietà <xref:System.Windows.Forms.Control.OnFontChanged%2A> metodo, che a sua volta genera il <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="97c0b-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="97c0b-122">Chiamare `EnumMethodSemantics` utilizzando MethodDef per <xref:System.Windows.Forms.Control.OnFontChanged%2A> per ottenere riferimenti al <xref:System.Windows.Forms.Control.Font%2A> proprietà e <xref:System.Windows.Forms.Control.FontChanged> evento.</span><span class="sxs-lookup"><span data-stu-id="97c0b-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97c0b-123">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97c0b-123">Requirements</span></span>  
 <span data-ttu-id="97c0b-124">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97c0b-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97c0b-125">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="97c0b-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="97c0b-126">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="97c0b-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="97c0b-127">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97c0b-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c0b-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97c0b-128">See Also</span></span>  
 [<span data-ttu-id="97c0b-129">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="97c0b-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="97c0b-130">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="97c0b-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
