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
ms.openlocfilehash: f79320d5b7d2ad4ad44a79fae063ce6718490a70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431958"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="7219c-102">Metodo IMetaDataAssemblyEmit::SetAssemblyProps</span><span class="sxs-lookup"><span data-stu-id="7219c-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="7219c-103">Modifica la struttura dei metadati `Assembly` specificata.</span><span class="sxs-lookup"><span data-stu-id="7219c-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7219c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7219c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7219c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7219c-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="7219c-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span><span class="sxs-lookup"><span data-stu-id="7219c-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="7219c-107">[in] A pointer to the public key of the publisher of the assembly.</span><span class="sxs-lookup"><span data-stu-id="7219c-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="7219c-108">[in] The size in bytes of `pbPublicKey`.</span><span class="sxs-lookup"><span data-stu-id="7219c-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="7219c-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span><span class="sxs-lookup"><span data-stu-id="7219c-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="7219c-110">[in] The human-readable text name of the assembly.</span><span class="sxs-lookup"><span data-stu-id="7219c-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="7219c-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span><span class="sxs-lookup"><span data-stu-id="7219c-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="7219c-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span><span class="sxs-lookup"><span data-stu-id="7219c-112">[in] A bitwise combination of [AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7219c-113">Note</span><span class="sxs-lookup"><span data-stu-id="7219c-113">Remarks</span></span>  
 <span data-ttu-id="7219c-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span><span class="sxs-lookup"><span data-stu-id="7219c-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7219c-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7219c-115">Requirements</span></span>  
 <span data-ttu-id="7219c-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7219c-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7219c-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7219c-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7219c-118">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7219c-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7219c-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7219c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7219c-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7219c-120">See also</span></span>

- [<span data-ttu-id="7219c-121">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="7219c-121">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
