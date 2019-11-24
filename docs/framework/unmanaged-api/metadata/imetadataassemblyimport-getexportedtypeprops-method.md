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
ms.openlocfilehash: 82302124828a2dab73b445128d7d847e112edd36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448214"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="d82a8-102">Metodo IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="d82a8-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="d82a8-103">Gets the set of properties of the exported type with the specified metadata signature.</span><span class="sxs-lookup"><span data-stu-id="d82a8-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d82a8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d82a8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d82a8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d82a8-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="d82a8-106">[in] An `mdExportedType` metadata token that represents the exported type.</span><span class="sxs-lookup"><span data-stu-id="d82a8-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="d82a8-107">[out] The name of the exported type.</span><span class="sxs-lookup"><span data-stu-id="d82a8-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d82a8-108">[in] The size, in wide characters, of `szName`.</span><span class="sxs-lookup"><span data-stu-id="d82a8-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d82a8-109">[out] The number of wide characters actually returned in `szName`</span><span class="sxs-lookup"><span data-stu-id="d82a8-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="d82a8-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span><span class="sxs-lookup"><span data-stu-id="d82a8-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="d82a8-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span><span class="sxs-lookup"><span data-stu-id="d82a8-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="d82a8-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span><span class="sxs-lookup"><span data-stu-id="d82a8-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="d82a8-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span><span class="sxs-lookup"><span data-stu-id="d82a8-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d82a8-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d82a8-114">Requirements</span></span>  
 <span data-ttu-id="d82a8-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d82a8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d82a8-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d82a8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d82a8-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d82a8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d82a8-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d82a8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d82a8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d82a8-119">See also</span></span>

- [<span data-ttu-id="d82a8-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="d82a8-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
