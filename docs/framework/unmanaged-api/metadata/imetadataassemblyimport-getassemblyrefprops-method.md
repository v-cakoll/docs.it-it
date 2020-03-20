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
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175967"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="9d665-102">Metodo IMetaDataAssemblyImport::GetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="9d665-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="9d665-103">Ottiene il set di proprietà per il riferimento all'assembly con la firma dei metadati specificata.</span><span class="sxs-lookup"><span data-stu-id="9d665-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d665-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d665-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="9d665-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d665-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="9d665-106">[in] Token `mdAssemblyRef` di metadati che rappresenta il riferimento all'assembly per il quale ottenere le proprietà.</span><span class="sxs-lookup"><span data-stu-id="9d665-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="9d665-107">[fuori] Puntatore alla chiave pubblica o al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="9d665-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="9d665-108">[fuori] Numero di byte nella chiave pubblica o nel token restituito.</span><span class="sxs-lookup"><span data-stu-id="9d665-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="9d665-109">[fuori] Nome semplice dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d665-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="9d665-110">[in] La dimensione, in caratteri `szName`ampi, di .</span><span class="sxs-lookup"><span data-stu-id="9d665-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="9d665-111">[fuori] Puntatore al numero di caratteri wide `szName`effettivamente restituiti in .</span><span class="sxs-lookup"><span data-stu-id="9d665-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="9d665-112">[fuori] Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="9d665-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="9d665-113">[fuori] Puntatore al valore hash.</span><span class="sxs-lookup"><span data-stu-id="9d665-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="9d665-114">Si tratta dell'hash, utilizzando l'algoritmo `PublicKey` SHA-1, della proprietà dell'assembly a cui si fa riferimento, a meno che non sia impostato il flag arfFullOriginator dell'enumerazione [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="9d665-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="9d665-115">[fuori] Numero di caratteri wide nel valore hash restituito.</span><span class="sxs-lookup"><span data-stu-id="9d665-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="9d665-116">[fuori] Puntatore a flag che descrivono i metadati applicati a un assembly.</span><span class="sxs-lookup"><span data-stu-id="9d665-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="9d665-117">Il valore flags è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.</span><span class="sxs-lookup"><span data-stu-id="9d665-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d665-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9d665-118">Return Value</span></span>  
 <span data-ttu-id="9d665-119">Questo metodo restituisce S_OK se ha esito positivo; in caso contrario, restituisce uno dei codici di errore definiti nel file di intestazione Winerror.h.</span><span class="sxs-lookup"><span data-stu-id="9d665-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d665-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d665-120">Requirements</span></span>  
 <span data-ttu-id="9d665-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d665-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d665-122">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d665-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d665-123">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d665-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d665-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d665-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d665-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d665-125">See also</span></span>

- [<span data-ttu-id="9d665-126">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="9d665-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
