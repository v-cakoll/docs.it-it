---
title: Metodo IMetaDataAssemblyImport::GetFileProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetFileProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 55984c4adaf291e3b962514cdc3bea964d1c91bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="f9cbd-102">Metodo IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="f9cbd-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="f9cbd-103">Ottiene le proprietà del file con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9cbd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9cbd-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="f9cbd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f9cbd-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="f9cbd-106">[in] Il `mdFile` token di metadati che rappresenta il file per cui ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="f9cbd-107">[out] Il nome semplice del file.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="f9cbd-108">[in] La dimensione in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="f9cbd-109">[out] Numero di caratteri "wide" effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="f9cbd-110">[out] Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="f9cbd-111">Si tratta dell'hash, usando l'algoritmo SHA-1, del file.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="f9cbd-112">[out] Il numero di caratteri "wide" nel valore hash restituito.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="f9cbd-113">[out] Un puntatore per i flag che descrivono i metadati applicati a un file.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="f9cbd-114">Il valore del flag è una combinazione di uno o più [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="f9cbd-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9cbd-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f9cbd-115">Requirements</span></span>  
 <span data-ttu-id="f9cbd-116">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9cbd-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9cbd-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f9cbd-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9cbd-118">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f9cbd-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9cbd-119">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9cbd-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9cbd-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9cbd-120">See Also</span></span>  
 [<span data-ttu-id="f9cbd-121">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="f9cbd-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
