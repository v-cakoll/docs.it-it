---
title: Metodo IMetaDataAssemblyEmit::DefineAssemblyRef
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssemblyRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 074e589b84e21de4ec3bcc3c54a865297587d383
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a><span data-ttu-id="c135b-102">Metodo IMetaDataAssemblyEmit::DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="c135b-102">IMetaDataAssemblyEmit::DefineAssemblyRef Method</span></span>
<span data-ttu-id="c135b-103">Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.</span><span class="sxs-lookup"><span data-stu-id="c135b-103">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c135b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c135b-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="c135b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c135b-105">Parameters</span></span>  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="c135b-106">[in] La chiave pubblica del server di pubblicazione dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c135b-106">[in] The public key of the publisher of the referenced assembly.</span></span> <span data-ttu-id="c135b-107">La funzione di supporto [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) può essere utilizzato per ottenere l'hash della chiave pubblica da passare come questo parametro.</span><span class="sxs-lookup"><span data-stu-id="c135b-107">The helper function [StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md) can be used to get the hash of the public key to pass as this parameter.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="c135b-108">[in] Le dimensioni in byte di `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="c135b-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="c135b-109">[in] Il nome di un testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="c135b-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="c135b-110">Questo valore non deve superare i 1024 caratteri.</span><span class="sxs-lookup"><span data-stu-id="c135b-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="c135b-111">[in] Un'istanza ASSEMBLYMETADATA che contiene le informazioni di versione, alla piattaforma e delle impostazioni locali dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c135b-111">[in] An ASSEMBLYMETADATA instance that contains the version, platform and locale information of the referenced assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="c135b-112">[in] I dati di hash associati all'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="c135b-112">[in] The hash data associated with the referenced assembly.</span></span> <span data-ttu-id="c135b-113">Parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="c135b-113">Optional.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="c135b-114">[in] Le dimensioni in byte di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="c135b-114">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="c135b-115">[in] Combinazione bit per bit di [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori che influenzano il comportamento del motore di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c135b-115">[in] A bitwise combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that influence the behavior of the execution engine.</span></span>  
  
 `pmdar`  
 <span data-ttu-id="c135b-116">[out] Un puntatore all'oggetto restituito `AssemblyRef` token di metadati.</span><span class="sxs-lookup"><span data-stu-id="c135b-116">[out] A pointer to the returned `AssemblyRef` metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c135b-117">Note</span><span class="sxs-lookup"><span data-stu-id="c135b-117">Remarks</span></span>  
 <span data-ttu-id="c135b-118">Una `AssemblyRef` struttura dei metadati deve essere definita per ogni assembly che fa riferimento questo assembly.</span><span class="sxs-lookup"><span data-stu-id="c135b-118">One `AssemblyRef` metadata structure must be defined for each assembly that this assembly references.</span></span>  
  
 <span data-ttu-id="c135b-119">In fase di esecuzione, vengono passati i dettagli di un assembly di riferimento per il resolver dell'assembly con un'indicazione che rappresentano le informazioni "così com'è"compilato.</span><span class="sxs-lookup"><span data-stu-id="c135b-119">At run time, the details of a referenced assembly are passed to the assembly resolver with an indication that they represent the "as built" information.</span></span> <span data-ttu-id="c135b-120">Il resolver dell'assembly applica quindi i criteri.</span><span class="sxs-lookup"><span data-stu-id="c135b-120">The assembly resolver then applies policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c135b-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c135b-121">Requirements</span></span>  
 <span data-ttu-id="c135b-122">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c135b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c135b-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c135b-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c135b-124">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c135b-124">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c135b-125">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c135b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c135b-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c135b-126">See Also</span></span>  
 [<span data-ttu-id="c135b-127">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c135b-127">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
