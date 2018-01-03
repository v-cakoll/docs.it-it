---
title: Metodo IMetaDataEmit2::DefineMethodSpec
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineMethodSpec
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 68b500a1a22b8efaedb4604351d91db03bb514cd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="bd454-102">Metodo IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="bd454-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="bd454-103">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="bd454-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd454-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bd454-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd454-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bd454-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="bd454-106">[in] Un token per il metodo di cui creare l'istanza generica.</span><span class="sxs-lookup"><span data-stu-id="bd454-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="bd454-107">Il token deve essere di tipo `mdMethodDef` o `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="bd454-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="bd454-108">[in] Puntatore a firma COM+ binaria del metodo.</span><span class="sxs-lookup"><span data-stu-id="bd454-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="bd454-109">[in] Le dimensioni, in byte, di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="bd454-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="bd454-110">[out] Un token di definizione dei metadati della firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="bd454-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd454-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bd454-111">Requirements</span></span>  
 <span data-ttu-id="bd454-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd454-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd454-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bd454-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd454-114">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd454-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd454-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd454-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd454-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bd454-116">See Also</span></span>  
 [<span data-ttu-id="bd454-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="bd454-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="bd454-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="bd454-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
