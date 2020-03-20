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
ms.openlocfilehash: 6ad6bbb8a4c69f575bbeba3a297c46e049a97325
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176045"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a><span data-ttu-id="17505-102">Metodo IMetaDataAssemblyEmit::SetAssemblyRefProps</span><span class="sxs-lookup"><span data-stu-id="17505-102">IMetaDataAssemblyEmit::SetAssemblyRefProps Method</span></span>
<span data-ttu-id="17505-103">Modifica la struttura dei metadati `AssemblyRef` specificata.</span><span class="sxs-lookup"><span data-stu-id="17505-103">Modifies the specified `AssemblyRef` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17505-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17505-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="17505-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="17505-105">Parameters</span></span>  
 `ar`  
 <span data-ttu-id="17505-106">[in] Token di metadati `AssemblyRef` che specifica la struttura dei metadati da modificare.</span><span class="sxs-lookup"><span data-stu-id="17505-106">[in] The metadata token that specifies the `AssemblyRef` metadata structure to be modified.</span></span>  
  
 `pbPublicKeyOrToken`  
 <span data-ttu-id="17505-107">[in] Chiave pubblica dell'editore dell'assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="17505-107">[in] The public key of the publisher of the referenced assembly.</span></span>  
  
 `cbPublicKeyOrToken`  
 <span data-ttu-id="17505-108">[in] Dimensione in byte `pbPublicKeyOrToken`di .</span><span class="sxs-lookup"><span data-stu-id="17505-108">[in] The size in bytes of `pbPublicKeyOrToken`.</span></span>  
  
 `szName`  
 <span data-ttu-id="17505-109">[in] Nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="17505-109">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="17505-110">[in] Puntatore a un'istanza assemblyMETADATA che contiene le informazioni sulla versione, sulla piattaforma e sulle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="17505-110">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="17505-111">[in] Puntatore ai dati hash associati all'assembly.</span><span class="sxs-lookup"><span data-stu-id="17505-111">[in] A pointer to the hash data associated with the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="17505-112">[in] Dimensione in byte `pbHashValue`di .</span><span class="sxs-lookup"><span data-stu-id="17505-112">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwAssemblyRefFlags`  
 <span data-ttu-id="17505-113">[in] Combinazione bit per bit di [assemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) valori che specificano gli attributi dell'assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="17505-113">[in] A bitwise combination of [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) values that specify attributes of the referenced assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17505-114">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="17505-114">Remarks</span></span>  
 <span data-ttu-id="17505-115">Per creare `AssemblyRef` una struttura dei metadati, utilizzare il metodo [IMetaDataAssemblyEmit::DefineAssemblyRef.](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)</span><span class="sxs-lookup"><span data-stu-id="17505-115">To create an `AssemblyRef` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssemblyRef](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17505-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17505-116">Requirements</span></span>  
 <span data-ttu-id="17505-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17505-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17505-118">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="17505-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="17505-119">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="17505-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="17505-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17505-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17505-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17505-121">See also</span></span>

- [<span data-ttu-id="17505-122">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="17505-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
