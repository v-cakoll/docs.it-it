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
ms.openlocfilehash: a5d9342b8bfe650106ccf9daf2a91dfbcd575446
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175539"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="2e78c-102">Metodo IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="2e78c-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="2e78c-103">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="2e78c-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e78c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e78c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e78c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e78c-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="2e78c-106">[in] Token per il metodo di cui creare l'istanza generica.</span><span class="sxs-lookup"><span data-stu-id="2e78c-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="2e78c-107">Il token deve `mdMethodDef` essere `mdMemberRef`di tipo o .</span><span class="sxs-lookup"><span data-stu-id="2e78c-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2e78c-108">[in] Un puntatore alla firma binaria COM.</span><span class="sxs-lookup"><span data-stu-id="2e78c-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="2e78c-109">[in] Dimensione, in byte, `pvSigBlob`di .</span><span class="sxs-lookup"><span data-stu-id="2e78c-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="2e78c-110">[fuori] Token per la definizione della firma dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="2e78c-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e78c-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e78c-111">Requirements</span></span>  
 <span data-ttu-id="2e78c-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e78c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e78c-113">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e78c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e78c-114">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e78c-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e78c-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e78c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e78c-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e78c-116">See also</span></span>

- [<span data-ttu-id="2e78c-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="2e78c-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2e78c-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2e78c-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
