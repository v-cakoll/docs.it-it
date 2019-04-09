---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 25d5e412dc52e4ce26995ff88454b33ccea64c89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110097"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="5a5ff-102">Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="5a5ff-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="5a5ff-103">Modifica la struttura dei metadati `AssemblyRef` specificata.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a5ff-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a5ff-104">Syntax</span></span>  
  
```  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,   
    [in] const ASSEMBLYMETADATA     *pMetaData,   
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a5ff-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a5ff-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="5a5ff-106">[in] Il token di metadati che specifica il `AssemblyRef` modifica della struttura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="5a5ff-107">[in] La chiave pubblica del server di pubblicazione dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="5a5ff-108">[in] La dimensione in byte di `pbPublicKeyOrToken`.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="5a5ff-109">[in] Il nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="5a5ff-110">[in] Un puntatore a un'istanza ASSEMBLYMETADATA che contiene le informazioni di versione, piattaforma e delle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="5a5ff-111">[in] Un puntatore per il valore hash dei dati associati all'assembly.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="5a5ff-112">[in] La dimensione in byte di `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="5a5ff-113">[in] Una combinazione bit per bit di [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) valori che specificano gli attributi dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="5a5ff-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a5ff-114">Note</span><span class="sxs-lookup"><span data-stu-id="5a5ff-114">Remarks</span></span>  
 <span data-ttu-id="5a5ff-115">Per creare un `AssemblyRef` struttura dei metadati, usare il [DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="5a5ff-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a5ff-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a5ff-116">Requirements</span></span>  
 <span data-ttu-id="5a5ff-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a5ff-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a5ff-118">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5a5ff-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a5ff-119">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5a5ff-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5a5ff-120">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5a5ff-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5a5ff-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a5ff-121">See also</span></span>

- [<span data-ttu-id="5a5ff-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="5a5ff-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
