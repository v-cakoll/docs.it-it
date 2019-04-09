---
title: Metodo IMetaDataEmit::TranslateSigWithScope
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 71029d6ebfb3248da791d4371dfe3e39589af443
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207643"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="3abde-102">Metodo IMetaDataEmit::TranslateSigWithScope</span><span class="sxs-lookup"><span data-stu-id="3abde-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="3abde-103">Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito unito.</span><span class="sxs-lookup"><span data-stu-id="3abde-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3abde-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3abde-104">Syntax</span></span>  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3abde-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3abde-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="3abde-106">[in] L'interfaccia per importare l'assembly (in cui è definita la firma).</span><span class="sxs-lookup"><span data-stu-id="3abde-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="3abde-107">[in] Il blob di hash per l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3abde-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="3abde-108">[in] Il numero di byte in `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="3abde-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="3abde-109">[in] L'interfaccia per l'ambito dei metadati di importazione.</span><span class="sxs-lookup"><span data-stu-id="3abde-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="3abde-110">[in] La firma da importare.</span><span class="sxs-lookup"><span data-stu-id="3abde-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="3abde-111">[in] Le dimensioni, in byte, di `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="3abde-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="3abde-112">[in] L'interfaccia per esportare l'assembly.</span><span class="sxs-lookup"><span data-stu-id="3abde-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="3abde-113">[in] L'interfaccia per l'ambito dei metadati di esportazione.</span><span class="sxs-lookup"><span data-stu-id="3abde-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="3abde-114">[out] Il buffer per mantenere il blob della firma tradotti.</span><span class="sxs-lookup"><span data-stu-id="3abde-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="3abde-115">[in] La capacità, in byte, di `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="3abde-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="3abde-116">[out] Il numero di byte effettivi nella firma tradotto.</span><span class="sxs-lookup"><span data-stu-id="3abde-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3abde-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3abde-117">Requirements</span></span>  
 <span data-ttu-id="3abde-118">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3abde-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3abde-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3abde-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3abde-120">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3abde-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3abde-121">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3abde-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3abde-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3abde-122">See also</span></span>

- [<span data-ttu-id="3abde-123">Interfaccia IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="3abde-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="3abde-124">Interfaccia IMetaDataAssemblyImport</span><span class="sxs-lookup"><span data-stu-id="3abde-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="3abde-125">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="3abde-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3abde-126">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="3abde-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3abde-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="3abde-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
