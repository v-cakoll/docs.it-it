---
title: Metodo IMetaDataImport2::GetMethodSpecProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c35212e7d261a5b385823fdaa345f6fbd638571c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079344"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="ddc5b-102">Metodo IMetaDataImport2::GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="ddc5b-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="ddc5b-103">Ottiene il token di firma dei metadati del metodo fa riferimento il MethodSpec Neobsahuje specificato.</span><span class="sxs-lookup"><span data-stu-id="ddc5b-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddc5b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ddc5b-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ddc5b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ddc5b-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="ddc5b-106">[in] Token MethodSpec Neobsahuje che rappresenta la creazione dell'istanza del metodo.</span><span class="sxs-lookup"><span data-stu-id="ddc5b-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="ddc5b-107">[out] Puntatore al token MethodDef o MethodRef che rappresenta la definizione del metodo.</span><span class="sxs-lookup"><span data-stu-id="ddc5b-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="ddc5b-108">[out] Un puntatore per la firma binaria dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="ddc5b-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="ddc5b-109">[out] Le dimensioni, in byte, di `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="ddc5b-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddc5b-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ddc5b-110">Requirements</span></span>  
 <span data-ttu-id="ddc5b-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddc5b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddc5b-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ddc5b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ddc5b-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="ddc5b-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="ddc5b-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ddc5b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ddc5b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ddc5b-115">See also</span></span>

- [<span data-ttu-id="ddc5b-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ddc5b-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="ddc5b-117">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ddc5b-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
