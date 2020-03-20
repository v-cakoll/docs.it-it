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
ms.openlocfilehash: dae4a36537eeac58ffb17ebc1b78d935ec807cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175980"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="59caa-102">Metodo IMetaDataAssemblyImport::GetFileProps</span><span class="sxs-lookup"><span data-stu-id="59caa-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="59caa-103">Ottiene le proprietà del file con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="59caa-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59caa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="59caa-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="59caa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="59caa-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="59caa-106">[in] Token `mdFile` di metadati che rappresenta il file per il quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="59caa-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="59caa-107">[fuori] Nome semplice del file.</span><span class="sxs-lookup"><span data-stu-id="59caa-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="59caa-108">[in] La dimensione, in caratteri `szName`ampi, di .</span><span class="sxs-lookup"><span data-stu-id="59caa-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="59caa-109">[fuori] Il numero di caratteri wide `szName`restituiti effettivamente in .</span><span class="sxs-lookup"><span data-stu-id="59caa-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="59caa-110">[fuori] Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="59caa-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="59caa-111">Questo è l'hash, utilizzando l'algoritmo SHA-1, del file.</span><span class="sxs-lookup"><span data-stu-id="59caa-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="59caa-112">[fuori] Numero di caratteri wide nel valore hash restituito.</span><span class="sxs-lookup"><span data-stu-id="59caa-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="59caa-113">[fuori] Puntatore ai flag che descrivono i metadati applicati a un file.</span><span class="sxs-lookup"><span data-stu-id="59caa-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="59caa-114">Il valore flags è una combinazione di uno o più [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="59caa-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59caa-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="59caa-115">Requirements</span></span>  
 <span data-ttu-id="59caa-116">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59caa-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59caa-117">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="59caa-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59caa-118">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59caa-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59caa-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59caa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59caa-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="59caa-120">See also</span></span>

- [<span data-ttu-id="59caa-121">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="59caa-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
