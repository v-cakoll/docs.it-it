---
title: Metodo IMetaDataAssemblyImport::GetFileProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da38c04f5d67dc0220b1828ba0e5cdeb84346bb6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137943"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="9a23b-102">Metodo IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="9a23b-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="9a23b-103">Ottiene le proprietà del file con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="9a23b-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a23b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a23b-104">Syntax</span></span>  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a23b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a23b-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="9a23b-106">[in] Il `mdFile` token di metadati che rappresenta il file per cui ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="9a23b-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="9a23b-107">[out] Il nome semplice del file.</span><span class="sxs-lookup"><span data-stu-id="9a23b-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9a23b-108">[in] Le dimensioni, in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="9a23b-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="9a23b-109">[out] Numero di caratteri wide effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="9a23b-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="9a23b-110">[out] Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="9a23b-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="9a23b-111">Questo è l'hash, usando l'algoritmo SHA-1, del file.</span><span class="sxs-lookup"><span data-stu-id="9a23b-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="9a23b-112">[out] Il numero di caratteri wide nel valore restituito di hash.</span><span class="sxs-lookup"><span data-stu-id="9a23b-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="9a23b-113">[out] Puntatore al flag che descrivono i metadati applicati a un file.</span><span class="sxs-lookup"><span data-stu-id="9a23b-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="9a23b-114">Il valore dei flag è una combinazione di uno o più [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="9a23b-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a23b-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a23b-115">Requirements</span></span>  
 <span data-ttu-id="9a23b-116">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a23b-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a23b-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9a23b-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a23b-118">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="9a23b-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a23b-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a23b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a23b-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a23b-120">See also</span></span>

- [<span data-ttu-id="9a23b-121">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="9a23b-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
