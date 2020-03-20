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
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177261"
---
# <a name="imetadataimportgeteventprops-method"></a><span data-ttu-id="41e17-102">Metodo IMetaDataImport::GetEventProps</span><span class="sxs-lookup"><span data-stu-id="41e17-102">IMetaDataImport::GetEventProps Method</span></span>
<span data-ttu-id="41e17-103">Ottiene informazioni sui metadati per l'evento rappresentato dal token di evento specificato, inclusi il tipo dichiarante, i metodi di aggiunta e rimozione per i delegati ed eventuali flag e altri dati associati.</span><span class="sxs-lookup"><span data-stu-id="41e17-103">Gets metadata information for the event represented by the specified event token, including the declaring type, the add and remove methods for delegates, and any flags and other associated data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41e17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41e17-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="41e17-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41e17-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="41e17-106">[in] Token dei metadati dell'evento che rappresenta l'evento per cui ottenere i metadati.</span><span class="sxs-lookup"><span data-stu-id="41e17-106">[in] The event metadata token representing the event to get metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="41e17-107">[fuori] Puntatore al token TypeDef che rappresenta la classe che dichiara l'evento.</span><span class="sxs-lookup"><span data-stu-id="41e17-107">[out] A pointer to the TypeDef token representing the class that declares the event.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="41e17-108">[fuori] Nome dell'evento a `ev`cui fa riferimento .</span><span class="sxs-lookup"><span data-stu-id="41e17-108">[out] The name of the event referenced by `ev`.</span></span>  
  
 `pchEvent`  
 <span data-ttu-id="41e17-109">[in] Lunghezza richiesta in caratteri `szEvent`di tipo "wide" di .</span><span class="sxs-lookup"><span data-stu-id="41e17-109">[in] The requested length in wide characters of `szEvent`.</span></span>  
  
 `pdwEventFlags`  
 <span data-ttu-id="41e17-110">[fuori] Lunghezza restituita in caratteri `szEvent`di tipo "wide" di .</span><span class="sxs-lookup"><span data-stu-id="41e17-110">[out] The returned length in wide characters of `szEvent`.</span></span>  
  
 `ptkEventType`  
 <span data-ttu-id="41e17-111">[fuori] Puntatore a un token di metadati <xref:System.Delegate> TypeRef o TypeDef che rappresenta il tipo dell'evento.</span><span class="sxs-lookup"><span data-stu-id="41e17-111">[out] A pointer to a TypeRef or TypeDef metadata token representing the <xref:System.Delegate> type of the event.</span></span>  
  
 `pmdAddOn`  
 <span data-ttu-id="41e17-112">[fuori] Puntatore al token di metadati che rappresenta il metodo che aggiunge gestori per l'evento.</span><span class="sxs-lookup"><span data-stu-id="41e17-112">[out] A pointer to the metadata token representing the method that adds handlers for the event.</span></span>  
  
 `pmdRemoveOn`  
 <span data-ttu-id="41e17-113">[fuori] Puntatore al token di metadati che rappresenta il metodo che rimuove i gestori per l'evento.</span><span class="sxs-lookup"><span data-stu-id="41e17-113">[out] A pointer to the metadata token representing the method that removes handlers for the event.</span></span>  
  
 `pmdFire`  
 <span data-ttu-id="41e17-114">[fuori] Puntatore al token di metadati che rappresenta il metodo che genera l'evento.</span><span class="sxs-lookup"><span data-stu-id="41e17-114">[out] A pointer to the metadata token representing the method that raises the event.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="41e17-115">[fuori] Matrice di puntatori token ad altri metodi associati all'evento.</span><span class="sxs-lookup"><span data-stu-id="41e17-115">[out] An array of token pointers to other methods associated with the event.</span></span>  
  
 `cMax`  
 <span data-ttu-id="41e17-116">[in] Dimensione massima della matrice `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="41e17-116">[in] The maximum size of the `rmdOtherMethod` array.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="41e17-117">[fuori] Numero di token restituiti `rmdOtherMethod`in .</span><span class="sxs-lookup"><span data-stu-id="41e17-117">[out] The number of tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41e17-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41e17-118">Requirements</span></span>  
 <span data-ttu-id="41e17-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41e17-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41e17-120">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="41e17-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41e17-121">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41e17-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="41e17-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41e17-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e17-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41e17-123">See also</span></span>

- [<span data-ttu-id="41e17-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="41e17-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="41e17-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="41e17-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
