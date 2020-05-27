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
ms.openlocfilehash: 944941c2356cae93ecc85f1714b4b29aefcb50ad
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008404"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="fad86-102">Metodo IMetaDataAssemblyImport::GetExportedTypeProps</span><span class="sxs-lookup"><span data-stu-id="fad86-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="fad86-103">Ottiene il set di proprietà del tipo esportato con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="fad86-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fad86-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fad86-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fad86-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fad86-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="fad86-106">in `mdExportedType`Token di metadati che rappresenta il tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="fad86-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="fad86-107">out Nome del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="fad86-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="fad86-108">in Dimensione, in caratteri wide, di `szName` .</span><span class="sxs-lookup"><span data-stu-id="fad86-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="fad86-109">out Numero di caratteri wide effettivamente restituiti in`szName`</span><span class="sxs-lookup"><span data-stu-id="fad86-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="fad86-110">out `mdFile` `mdAssemblyRef` `mdExportedType` Token di metadati, o che contiene o consente l'accesso alle proprietà del tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="fad86-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="fad86-111">out Puntatore a un `mdTypeDef` token che rappresenta un tipo nel file.</span><span class="sxs-lookup"><span data-stu-id="fad86-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="fad86-112">out Puntatore ai flag che descrivono i metadati applicati al tipo esportato.</span><span class="sxs-lookup"><span data-stu-id="fad86-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="fad86-113">Il valore dei flag può essere uno o più valori [CorTypeAttr](cortypeattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="fad86-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fad86-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fad86-114">Requirements</span></span>  
 <span data-ttu-id="fad86-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fad86-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fad86-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fad86-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fad86-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fad86-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fad86-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fad86-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fad86-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fad86-119">See also</span></span>

- [<span data-ttu-id="fad86-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="fad86-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
