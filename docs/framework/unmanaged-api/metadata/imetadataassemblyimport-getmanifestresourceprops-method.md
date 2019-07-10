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
ms.openlocfilehash: e47b1807e51427487d6af2f96ff5af437c4653eb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760954"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="06517-102">Metodo IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="06517-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="06517-103">Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="06517-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06517-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="06517-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="06517-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="06517-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="06517-106">[in] Un `mdManifestResource` token che rappresenta la risorsa per cui ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="06517-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="06517-107">[out] Il nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="06517-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="06517-108">[in] Le dimensioni, in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="06517-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="06517-109">[out] Un puntatore al numero di caratteri wide effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="06517-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="06517-110">[out] Un puntatore a un `mdFile` token o un `mdAssemblyRef` token che rappresenta il file o l'assembly, rispettivamente, che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="06517-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="06517-111">[out] Puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="06517-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="06517-112">[out] Puntatore al flag che descrivono i metadati applicati a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="06517-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="06517-113">Il valore dei flag è una combinazione di uno o più [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="06517-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06517-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="06517-114">Requirements</span></span>  
 <span data-ttu-id="06517-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06517-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06517-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06517-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06517-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="06517-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06517-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06517-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06517-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06517-119">See also</span></span>

- [<span data-ttu-id="06517-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="06517-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
