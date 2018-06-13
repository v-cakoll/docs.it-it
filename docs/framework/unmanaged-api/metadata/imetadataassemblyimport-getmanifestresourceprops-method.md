---
title: Metodo IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07237794ca45b16b1ae1ca95b1d62889f095350f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448159"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="23f05-102">Metodo IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="23f05-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="23f05-103">Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="23f05-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23f05-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23f05-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="23f05-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="23f05-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="23f05-106">[in] Un `mdManifestResource` token che rappresenta la risorsa per cui ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="23f05-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="23f05-107">[out] Il nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="23f05-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="23f05-108">[in] La dimensione in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="23f05-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="23f05-109">[out] Un puntatore al numero di caratteri "wide" effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="23f05-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="23f05-110">[out] Un puntatore a un `mdFile` token o un `mdAssemblyRef` token che rappresenta i file di assembly, rispettivamente, che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="23f05-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="23f05-111">[out] Un puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="23f05-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="23f05-112">[out] Puntatore a flag che descrivono i metadati applicati a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="23f05-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="23f05-113">Il valore del flag è una combinazione di uno o più [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="23f05-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23f05-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23f05-114">Requirements</span></span>  
 <span data-ttu-id="23f05-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23f05-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23f05-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="23f05-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23f05-117">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="23f05-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23f05-118">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23f05-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23f05-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23f05-119">See Also</span></span>  
 [<span data-ttu-id="23f05-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="23f05-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
