---
title: Metodo IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e480c408c10eb9e135f260426750f7747e5d8ce5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59117352"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="8f797-102">Metodo IMetaDataAssemblyEmit::DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="8f797-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="8f797-103">Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="8f797-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f797-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f797-104">Syntax</span></span>  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f797-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8f797-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="8f797-106">[in] La chiave pubblica del server di pubblicazione dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="8f797-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="8f797-107">La funzione helper [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) utilizzabile per ottenere l'hash della chiave pubblica da passare come parametro.</span><span class="sxs-lookup"><span data-stu-id="8f797-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="8f797-108">[in] La dimensione in byte di `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="8f797-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="8f797-109">[in] Il nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="8f797-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="8f797-110">Questo valore non deve superare 1024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="8f797-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="8f797-111">[in] Istanza ASSEMBLYMETADATA che contiene le informazioni di versione, piattaforma e delle impostazioni locali dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="8f797-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="8f797-112">[in] I dati di hash associati con l'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="8f797-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="8f797-113">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8f797-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="8f797-114">[in] La dimensione in byte di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="8f797-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="8f797-115">[in] Una combinazione bit per bit di [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori che influenzano il comportamento del motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="8f797-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="8f797-116">[out] Un puntatore all'oggetto restituito `AssemblyRef` token di metadati.</span><span class="sxs-lookup"><span data-stu-id="8f797-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f797-117">Note</span><span class="sxs-lookup"><span data-stu-id="8f797-117">Remarks</span></span>  
 <span data-ttu-id="8f797-118">Uno `AssemblyRef` struttura dei metadati deve essere definita per ogni assembly che fa riferimento questo assembly.</span><span class="sxs-lookup"><span data-stu-id="8f797-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="8f797-119">In fase di esecuzione, i dettagli di un assembly di riferimento vengono passati al resolver di assembly con un valore che indica che essi rappresentano le informazioni "così come compilato".</span><span class="sxs-lookup"><span data-stu-id="8f797-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="8f797-120">Il resolver dell'assembly applica quindi i criteri.</span><span class="sxs-lookup"><span data-stu-id="8f797-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f797-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f797-121">Requirements</span></span>  
 <span data-ttu-id="8f797-122">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f797-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f797-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8f797-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f797-124">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="8f797-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f797-125">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f797-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f797-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f797-126">See also</span></span>

- [<span data-ttu-id="8f797-127">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="8f797-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
