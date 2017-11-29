---
title: Metodo IMetaDataAssemblyImport::GetManifestResourceProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetManifestResourceProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 29458b0b7afa5a0c0be908915b4fc91c85d28c72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="a4e94-102">Metodo IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="a4e94-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="a4e94-103">Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="a4e94-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4e94-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4e94-104">Syntax</span></span>  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4e94-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4e94-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="a4e94-106">[in] Un `mdManifestResource` token che rappresenta la risorsa per cui ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="a4e94-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="a4e94-107">[out] Il nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="a4e94-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a4e94-108">[in] La dimensione in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="a4e94-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="a4e94-109">[out] Un puntatore al numero di caratteri "wide" effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="a4e94-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="a4e94-110">[out] Un puntatore a un `mdFile` token o un `mdAssemblyRef` token che rappresenta i file di assembly, rispettivamente, che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="a4e94-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="a4e94-111">[out] Un puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="a4e94-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="a4e94-112">[out] Puntatore a flag che descrivono i metadati applicati a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="a4e94-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="a4e94-113">Il valore del flag è una combinazione di uno o più [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="a4e94-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4e94-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4e94-114">Requirements</span></span>  
 <span data-ttu-id="a4e94-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4e94-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4e94-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a4e94-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4e94-117">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4e94-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4e94-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4e94-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4e94-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4e94-119">See Also</span></span>  
 [<span data-ttu-id="a4e94-120">IMetaDataAssemblyImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a4e94-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
