---
title: Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91d21f51312eb812d253ba218eeeb99e5df1ff8e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730230"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="0ba91-102">Metodo IMetaDataAssemblyImport::GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="0ba91-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="0ba91-103">Ottiene il set di proprietà per il riferimento all'assembly con la firma dei metadati specificato.</span><span class="sxs-lookup"><span data-stu-id="0ba91-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ba91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ba91-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ba91-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0ba91-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="0ba91-106">[in] Il `mdAssemblyRef` token di metadati che rappresenta il riferimento all'assembly per cui ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="0ba91-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="0ba91-107">[out] Puntatore alla chiave pubblica o token di metadati.</span><span class="sxs-lookup"><span data-stu-id="0ba91-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="0ba91-108">[out] Il numero di byte restituito pubblico o un token.</span><span class="sxs-lookup"><span data-stu-id="0ba91-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="0ba91-109">[out] Il nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0ba91-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0ba91-110">[in] Le dimensioni, in caratteri wide, di `szName`.</span><span class="sxs-lookup"><span data-stu-id="0ba91-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="0ba91-111">[out] Un puntatore al numero di caratteri wide effettivamente restituiti nella `szName`.</span><span class="sxs-lookup"><span data-stu-id="0ba91-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="0ba91-112">[out] Un puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="0ba91-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="0ba91-113">[out] Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="0ba91-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="0ba91-114">Questo è l'hash, usando l'algoritmo SHA-1, del `PublicKey` proprietà dell'assembly a cui viene fatto riferimento, a meno che il flag arfFullOriginator del [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumerazione è impostato.</span><span class="sxs-lookup"><span data-stu-id="0ba91-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="0ba91-115">[out] Il numero di caratteri wide nel valore restituito di hash.</span><span class="sxs-lookup"><span data-stu-id="0ba91-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="0ba91-116">[out] Puntatore al flag che descrivono i metadati applicati a un assembly.</span><span class="sxs-lookup"><span data-stu-id="0ba91-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="0ba91-117">Il valore dei flag è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="0ba91-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ba91-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0ba91-118">Return Value</span></span>  
 <span data-ttu-id="0ba91-119">Questo metodo restituisce S_OK se riesce; in caso contrario, restituisce uno dei codici di errore definiti nel file di intestazione file Winerror. h.</span><span class="sxs-lookup"><span data-stu-id="0ba91-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ba91-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0ba91-120">Requirements</span></span>  
 <span data-ttu-id="0ba91-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ba91-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ba91-122">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0ba91-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ba91-123">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0ba91-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ba91-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ba91-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ba91-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ba91-125">See also</span></span>
- [<span data-ttu-id="0ba91-126">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="0ba91-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
