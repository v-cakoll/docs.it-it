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
ms.openlocfilehash: 8e067dc4943e6847177c13a683703e3a649a49e4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503822"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="a2bfa-102">Metodo IMetaDataEmit2::DefineMethodSpec</span><span class="sxs-lookup"><span data-stu-id="a2bfa-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="a2bfa-103">Crea un'istanza generica di un metodo e ottiene un token per la definizione.</span><span class="sxs-lookup"><span data-stu-id="a2bfa-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2bfa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2bfa-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a2bfa-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2bfa-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="a2bfa-106">in Token per il metodo di cui creare l'istanza generica.</span><span class="sxs-lookup"><span data-stu-id="a2bfa-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="a2bfa-107">Il token deve essere di tipo `mdMethodDef` o `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="a2bfa-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="a2bfa-108">in Puntatore alla firma COM+ binaria del metodo.</span><span class="sxs-lookup"><span data-stu-id="a2bfa-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="a2bfa-109">in Dimensione, in byte, di `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="a2bfa-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="a2bfa-110">out Token per la definizione della firma dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="a2bfa-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2bfa-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2bfa-111">Requirements</span></span>  
 <span data-ttu-id="a2bfa-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2bfa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2bfa-113">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a2bfa-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2bfa-114">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a2bfa-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2bfa-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2bfa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2bfa-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2bfa-116">See also</span></span>

- [<span data-ttu-id="a2bfa-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="a2bfa-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="a2bfa-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="a2bfa-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
