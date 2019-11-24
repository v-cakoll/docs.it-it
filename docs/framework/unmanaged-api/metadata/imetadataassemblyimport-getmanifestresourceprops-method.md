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
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436326"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="c8cd3-102">Metodo IMetaDataAssemblyImport::GetManifestResourceProps</span><span class="sxs-lookup"><span data-stu-id="c8cd3-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>
<span data-ttu-id="c8cd3-103">Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8cd3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8cd3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="c8cd3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8cd3-105">Parameters</span></span>  
 `mdmr`  
 <span data-ttu-id="c8cd3-106">in Token `mdManifestResource` che rappresenta la risorsa per la quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="c8cd3-107">out Nome della risorsa.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="c8cd3-108">in Dimensione, in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="c8cd3-109">out Puntatore al numero di caratteri wide effettivamente restituiti in `szName`.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="c8cd3-110">out Puntatore a un token di `mdFile` o a un token di `mdAssemblyRef` che rappresenta il file o l'assembly, rispettivamente, che contiene la risorsa.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="c8cd3-111">out Puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="c8cd3-112">out Puntatore ai flag che descrivono i metadati applicati a una risorsa.</span><span class="sxs-lookup"><span data-stu-id="c8cd3-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="c8cd3-113">Il valore dei flag è una combinazione di uno o più valori [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="c8cd3-113">The flags value is a combination of one or more [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8cd3-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8cd3-114">Requirements</span></span>  
 <span data-ttu-id="c8cd3-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8cd3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8cd3-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c8cd3-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8cd3-117">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c8cd3-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8cd3-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8cd3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8cd3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8cd3-119">See also</span></span>

- [<span data-ttu-id="c8cd3-120">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="c8cd3-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
