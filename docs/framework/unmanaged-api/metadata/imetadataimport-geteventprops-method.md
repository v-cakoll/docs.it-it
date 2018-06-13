---
title: Metodo IMetaDataImport::GetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6ac1ecb73257782888c963082953ed243177a86b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448804"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="15891-102">Metodo IMetaDataImport::GetEventProps</span><span class="sxs-lookup"><span data-stu-id="15891-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="15891-103">Ottiene informazioni sui metadati per l'evento rappresentato dal token specificato, inclusi il tipo dichiarante, add e Remove per delegati e i flag e altri dati associati.</span><span class="sxs-lookup"><span data-stu-id="15891-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15891-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15891-104">Syntax</span></span>  
  
```  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15891-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="15891-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="15891-106">[in] Token di metadati che rappresenta l'evento per ottenere i metadati.</span><span class="sxs-lookup"><span data-stu-id="15891-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="15891-107">[out] Un puntatore al token TypeDef che rappresenta la classe che dichiara l'evento.</span><span class="sxs-lookup"><span data-stu-id="15891-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="15891-108">[out] Il nome dell'evento a cui fa riferimento `ev`.</span><span class="sxs-lookup"><span data-stu-id="15891-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="15891-109">[in] La lunghezza in caratteri wide della richiesta `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="15891-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="15891-110">[out] La lunghezza restituita in caratteri wide di `szEvent`.</span><span class="sxs-lookup"><span data-stu-id="15891-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="15891-111">[out] Un puntatore a un TypeRef o TypeDef metadati token che rappresenta il <xref:System.Delegate> tipo dell'evento.</span><span class="sxs-lookup"><span data-stu-id="15891-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="15891-112">[out] Puntatore al token di metadati che rappresenta il metodo che consente di aggiungere gestori eventi per l'evento.</span><span class="sxs-lookup"><span data-stu-id="15891-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="15891-113">[out] Puntatore al token di metadati che rappresenta il metodo rimuove i gestori per l'evento.</span><span class="sxs-lookup"><span data-stu-id="15891-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="15891-114">[out] Puntatore al token di metadati che rappresenta il metodo che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="15891-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="15891-115">[out] Una matrice di puntatori token ad altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="15891-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="15891-116">[in] Dimensione massima della matrice `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="15891-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="15891-117">[out] Il numero di token restituiti in `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="15891-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15891-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15891-118">Requirements</span></span>  
 <span data-ttu-id="15891-119">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15891-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15891-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="15891-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15891-121">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="15891-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15891-122">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15891-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15891-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15891-123">See Also</span></span>  
 [<span data-ttu-id="15891-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="15891-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="15891-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="15891-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
