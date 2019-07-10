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
ms.openlocfilehash: a4185ec41fc9f7d1d919a79b57c02625210ad72a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777185"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="83368-102">Metodo IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="83368-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="83368-103">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="83368-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83368-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83368-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83368-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83368-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="83368-106">[in] Un token per il metodo di cui creare l'istanza generica.</span><span class="sxs-lookup"><span data-stu-id="83368-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="83368-107">Il token deve essere di tipo `mdMethodDef` o `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="83368-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="83368-108">[in] Puntatore alla firma binaria COM+ del metodo.</span><span class="sxs-lookup"><span data-stu-id="83368-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="83368-109">[in] Le dimensioni, in byte, di `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="83368-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="83368-110">[out] Un token per la definizione di firma dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="83368-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83368-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83368-111">Requirements</span></span>  
 <span data-ttu-id="83368-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83368-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83368-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83368-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83368-114">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="83368-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83368-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83368-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83368-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83368-116">See also</span></span>

- [<span data-ttu-id="83368-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="83368-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="83368-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="83368-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
