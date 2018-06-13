---
title: Metodo IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9115657c52f31d9b7b7da3c843338670343da26c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446473"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="79a7c-102">Metodo IMetaDataAssemblyEmit::DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="79a7c-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="79a7c-103">Crea un `Assembly` struttura che contiene i metadati per l'assembly specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="79a7c-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79a7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="79a7c-104">Syntax</span></span>  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79a7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="79a7c-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="79a7c-106">[in] La chiave pubblica che identifica l'autore dell'assembly, o NULL se l'assembly non è sicuro.</span><span class="sxs-lookup"><span data-stu-id="79a7c-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="79a7c-107">[in] Le dimensioni in byte di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="79a7c-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="79a7c-108">[in] Identificatore dell'algoritmo hash da utilizzare per crittografare i file nell'assembly, o NULL per specificare l'algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="79a7c-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="79a7c-109">[in] Il nome di un testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="79a7c-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="79a7c-110">Questo valore non deve superare i 1024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="79a7c-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="79a7c-111">[in] Un puntatore a un'istanza ASSEMBLYMETADATA che contiene le informazioni sulla versione, piattaforma e delle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="79a7c-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="79a7c-112">[in] Una combinazione di [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori che descrivono le funzionalità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="79a7c-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="79a7c-113">[out] Puntatore al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="79a7c-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79a7c-114">Note</span><span class="sxs-lookup"><span data-stu-id="79a7c-114">Remarks</span></span>  
 <span data-ttu-id="79a7c-115">Un solo `Assembly` struttura dei metadati può essere definito all'interno di un manifesto.</span><span class="sxs-lookup"><span data-stu-id="79a7c-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79a7c-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="79a7c-116">Requirements</span></span>  
 <span data-ttu-id="79a7c-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79a7c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79a7c-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="79a7c-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79a7c-119">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="79a7c-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79a7c-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79a7c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79a7c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79a7c-121">See Also</span></span>  
 [<span data-ttu-id="79a7c-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="79a7c-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
