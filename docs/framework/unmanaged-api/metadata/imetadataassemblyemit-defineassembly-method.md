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
ms.openlocfilehash: d53409e0be43dbf5d0cf7ba0fcbc170e2117f6a1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745817"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="4a715-102">Metodo IMetaDataAssemblyEmit::DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="4a715-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="4a715-103">Crea un `Assembly` struttura che contiene i metadati per l'assembly specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="4a715-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a715-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a715-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="4a715-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a715-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="4a715-106">[in] La chiave pubblica che identifica l'autore dell'assembly, o NULL se l'assembly non è sicuro.</span><span class="sxs-lookup"><span data-stu-id="4a715-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="4a715-107">[in] La dimensione in byte di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="4a715-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="4a715-108">[in] L'identificatore dell'algoritmo hash da usare per crittografare i file nell'assembly, o NULL per specificare l'algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="4a715-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="4a715-109">[in] Il nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a715-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="4a715-110">Questo valore non deve superare 1024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="4a715-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="4a715-111">[in] Un puntatore a un'istanza ASSEMBLYMETADATA che contiene le informazioni di versione, piattaforma e delle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a715-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="4a715-112">[in] Una combinazione di [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori che descrivono le funzionalità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="4a715-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="4a715-113">[out] Puntatore al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="4a715-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a715-114">Note</span><span class="sxs-lookup"><span data-stu-id="4a715-114">Remarks</span></span>  
 <span data-ttu-id="4a715-115">Un solo `Assembly` struttura dei metadati può essere definito all'interno di un manifesto.</span><span class="sxs-lookup"><span data-stu-id="4a715-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a715-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a715-116">Requirements</span></span>  
 <span data-ttu-id="4a715-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a715-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a715-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4a715-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a715-119">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4a715-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a715-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a715-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a715-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a715-121">See also</span></span>

- [<span data-ttu-id="4a715-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="4a715-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
