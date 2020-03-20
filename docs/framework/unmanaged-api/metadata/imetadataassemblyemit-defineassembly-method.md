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
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177894"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="00230-102">Metodo IMetaDataAssemblyEmit::DefineAssembly</span><span class="sxs-lookup"><span data-stu-id="00230-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="00230-103">Crea `Assembly` una struttura contenente i metadati per l'assembly specificato e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="00230-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00230-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00230-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="00230-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00230-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="00230-106">[in] Chiave pubblica che identifica l'editore dell'assembly oppure NULL se l'assembly non ha un nome con nome sicuro.</span><span class="sxs-lookup"><span data-stu-id="00230-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="00230-107">[in] Dimensione in byte `pbPublicKey`di .</span><span class="sxs-lookup"><span data-stu-id="00230-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="00230-108">[in] Identificatore dell'algoritmo hash da utilizzare per crittografare i file nell'assembly oppure NULL per specificare l'algoritmo SHA-1.</span><span class="sxs-lookup"><span data-stu-id="00230-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="00230-109">[in] Nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="00230-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="00230-110">Questo valore non deve superare i 1024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="00230-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="00230-111">[in] Puntatore a un'istanza assemblyMETADATA che contiene le informazioni sulla versione, sulla piattaforma e sulle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="00230-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="00230-112">[in] Combinazione di valori [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) che descrivono le funzionalità dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="00230-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="00230-113">[fuori] Puntatore al token di metadati.</span><span class="sxs-lookup"><span data-stu-id="00230-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00230-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="00230-114">Remarks</span></span>  
 <span data-ttu-id="00230-115">È `Assembly` possibile definire una sola struttura di metadati all'interno di un manifesto.</span><span class="sxs-lookup"><span data-stu-id="00230-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00230-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00230-116">Requirements</span></span>  
 <span data-ttu-id="00230-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00230-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00230-118">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="00230-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00230-119">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="00230-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00230-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00230-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00230-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="00230-121">See also</span></span>

- [<span data-ttu-id="00230-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="00230-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
