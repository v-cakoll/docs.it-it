---
title: Metodo IMetaDataAssemblyImport::GetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74295b14e9c774aa8a61d9c2726a39a4e3f5f8cc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57477712"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="1f07d-102">Metodo IMetaDataAssemblyImport::GetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="1f07d-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="1f07d-103">Ottiene il set di proprietà per l'assembly con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="1f07d-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f07d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f07d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f07d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1f07d-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="1f07d-106">[in].</span><span class="sxs-lookup"><span data-stu-id="1f07d-106">[in].</span></span> <span data-ttu-id="1f07d-107">Il `mdAssembly` token di metadati che rappresenta l'assembly per cui ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="1f07d-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="1f07d-108">[out] Puntatore alla chiave pubblica o token di metadati.</span><span class="sxs-lookup"><span data-stu-id="1f07d-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="1f07d-109">[out] Il numero di byte nella chiave pubblica restituita.</span><span class="sxs-lookup"><span data-stu-id="1f07d-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="1f07d-110">[out] Un puntatore all'algoritmo utilizzato per eseguire l'hashing i file nell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1f07d-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="1f07d-111">[out] Il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1f07d-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1f07d-112">[in] Le dimensioni, in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="1f07d-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="1f07d-113">[out] Numero di caratteri wide effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="1f07d-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="1f07d-114">[out] Un puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="1f07d-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="1f07d-115">[out] Flag che descrivono i metadati applicati a un assembly.</span><span class="sxs-lookup"><span data-stu-id="1f07d-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="1f07d-116">Questo valore è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="1f07d-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f07d-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1f07d-117">Requirements</span></span>  
 <span data-ttu-id="1f07d-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f07d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f07d-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1f07d-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f07d-120">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1f07d-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1f07d-121">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1f07d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f07d-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f07d-122">See also</span></span>
- [<span data-ttu-id="1f07d-123">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="1f07d-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
