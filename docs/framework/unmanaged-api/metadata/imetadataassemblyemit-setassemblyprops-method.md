---
title: Metodo IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34335321207e98a518ff3e0fdb5ea1dc3ac68b75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776260"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="a1bf5-102">Metodo IMetaDataAssemblyEmit::SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="a1bf5-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="a1bf5-103">Modifica la struttura dei metadati `Assembly` specificata.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bf5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a1bf5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1bf5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a1bf5-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="a1bf5-106">[in] Il token di metadati che specifica il `Assembly` modifica della struttura dei metadati.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="a1bf5-107">[in] Puntatore alla chiave pubblica del server di pubblicazione dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="a1bf5-108">[in] La dimensione in byte di `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="a1bf5-109">[in] L'identificatore per l'algoritmo hash usato per eseguire l'hashing i file di assembly.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="a1bf5-110">[in] Il nome di testo leggibile dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="a1bf5-111">[in] Puntatore a ASSEMBLYMETADATA che contiene le informazioni di versione, piattaforma e delle impostazioni locali per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="a1bf5-112">[in] Una combinazione bit per bit di [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) valori che specificano vari attributi dell'assembly.</span><span class="sxs-lookup"><span data-stu-id="a1bf5-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1bf5-113">Note</span><span class="sxs-lookup"><span data-stu-id="a1bf5-113">Remarks</span></span>  
 <span data-ttu-id="a1bf5-114">Per creare un `Assembly` struttura dei metadati, usare il [DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="a1bf5-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bf5-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a1bf5-115">Requirements</span></span>  
 <span data-ttu-id="a1bf5-116">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1bf5-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bf5-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a1bf5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1bf5-118">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="a1bf5-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1bf5-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bf5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bf5-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a1bf5-120">See also</span></span>

- [<span data-ttu-id="a1bf5-121">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="a1bf5-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
