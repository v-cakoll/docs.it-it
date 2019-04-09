---
title: Metodo IMetaDataEmit2::DefineMethodSpec
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce6df232f3793b8b61d9fa7c18c9c90ca9fa3900
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184717"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="95d02-102">Metodo IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="95d02-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="95d02-103">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="95d02-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95d02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="95d02-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95d02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="95d02-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="95d02-106">[in] Un token per il metodo di cui creare l'istanza generica.</span><span class="sxs-lookup"><span data-stu-id="95d02-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="95d02-107">Il token deve essere di tipo `mdMethodDef` o `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="95d02-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="95d02-108">[in] Puntatore alla firma binaria COM+ del metodo.</span><span class="sxs-lookup"><span data-stu-id="95d02-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="95d02-109">[in] Le dimensioni, in byte, di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="95d02-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="95d02-110">[out] Un token per la definizione di firma dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="95d02-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95d02-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="95d02-111">Requirements</span></span>  
 <span data-ttu-id="95d02-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95d02-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95d02-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="95d02-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95d02-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="95d02-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="95d02-115">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="95d02-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95d02-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95d02-116">See also</span></span>

- [<span data-ttu-id="95d02-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="95d02-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="95d02-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="95d02-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
