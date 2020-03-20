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
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177652"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="75bc8-102">Metodo IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="75bc8-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="75bc8-103">Ottiene il set di proprietà della risorsa di manifesto con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="75bc8-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75bc8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75bc8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="75bc8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="75bc8-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="75bc8-106">[in] Token `mdManifestResource` che rappresenta la risorsa per la quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="75bc8-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="75bc8-107">[fuori] Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="75bc8-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="75bc8-108">[in] La dimensione, in caratteri `szName`ampi, di .</span><span class="sxs-lookup"><span data-stu-id="75bc8-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="75bc8-109">[fuori] Puntatore al numero di caratteri wide `szName`effettivamente restituiti in .</span><span class="sxs-lookup"><span data-stu-id="75bc8-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="75bc8-110">[fuori] Puntatore a `mdFile` un `mdAssemblyRef` token o a un token che rappresenta rispettivamente il file o l'assembly che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="75bc8-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="75bc8-111">[fuori] Puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="75bc8-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="75bc8-112">[fuori] Puntatore a flag che descrivono i metadati applicati a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="75bc8-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="75bc8-113">Il valore flags è una combinazione di uno o più [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="75bc8-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75bc8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75bc8-114">Requirements</span></span>  
 <span data-ttu-id="75bc8-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75bc8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75bc8-116">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75bc8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75bc8-117">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75bc8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75bc8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75bc8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75bc8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75bc8-119">See also</span></span>

- [<span data-ttu-id="75bc8-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="75bc8-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
