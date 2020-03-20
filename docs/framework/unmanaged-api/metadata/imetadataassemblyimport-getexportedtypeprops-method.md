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
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177763"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="988a3-102">Metodo IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="988a3-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="988a3-103">Ottiene il set di proprietà del tipo esportato con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="988a3-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="988a3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="988a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="988a3-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="988a3-106">[in] Token `mdExportedType` di metadati che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="988a3-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="988a3-107">[fuori] Nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="988a3-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="988a3-108">[in] La dimensione, in caratteri `szName`larghi, di .</span><span class="sxs-lookup"><span data-stu-id="988a3-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="988a3-109">[fuori] Il numero di caratteri di larghezza effettivamente restituiti in`szName`</span><span class="sxs-lookup"><span data-stu-id="988a3-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="988a3-110">[fuori] Un `mdFile` `mdAssemblyRef`token `mdExportedType` , , o di metadati che contiene o consente l'accesso alle proprietà del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="988a3-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="988a3-111">[fuori] Puntatore a `mdTypeDef` un token che rappresenta un tipo nel file.</span><span class="sxs-lookup"><span data-stu-id="988a3-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="988a3-112">[fuori] Puntatore ai flag che descrivono i metadati applicati al tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="988a3-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="988a3-113">Il valore flags può essere uno o più [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="988a3-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="988a3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="988a3-114">Requirements</span></span>  
 <span data-ttu-id="988a3-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="988a3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="988a3-116">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="988a3-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="988a3-117">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="988a3-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="988a3-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="988a3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="988a3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="988a3-119">See also</span></span>

- [<span data-ttu-id="988a3-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="988a3-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
