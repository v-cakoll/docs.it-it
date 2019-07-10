---
title: Metodo IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8dd1daf3528bbc642033e254a809c18c3662ff1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779192"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="616d6-102">Metodo IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="616d6-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="616d6-103">Ottiene il set di proprietà del tipo esportato con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="616d6-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="616d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="616d6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="616d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="616d6-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="616d6-106">[in] Un `mdExportedType` token di metadati che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="616d6-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="616d6-107">[out] Il nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="616d6-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="616d6-108">[in] Le dimensioni, in caratteri "wide", di `szName`.</span><span class="sxs-lookup"><span data-stu-id="616d6-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="616d6-109">[out] Il numero di caratteri "wide" è effettivamente restituiti nella `szName`</span><span class="sxs-lookup"><span data-stu-id="616d6-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="616d6-110">[out] Un' `mdFile`, `mdAssemblyRef`, o `mdExportedType` token di metadati che contiene o consente l'accesso alle proprietà del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="616d6-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="616d6-111">[out] Un puntatore a un `mdTypeDef` token che rappresenta un tipo nel file.</span><span class="sxs-lookup"><span data-stu-id="616d6-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="616d6-112">[out] Puntatore ai flag che descrivono i metadati applicati al tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="616d6-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="616d6-113">Il valore del flag può essere uno o più [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="616d6-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="616d6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="616d6-114">Requirements</span></span>  
 <span data-ttu-id="616d6-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="616d6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="616d6-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="616d6-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="616d6-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="616d6-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="616d6-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="616d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="616d6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="616d6-119">See also</span></span>

- [<span data-ttu-id="616d6-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="616d6-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
