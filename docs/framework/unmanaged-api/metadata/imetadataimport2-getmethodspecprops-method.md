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
ms.openlocfilehash: 3249ad76c428752c91540e135bc978d3fe835de1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448133"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="74f3c-102">Metodo IMetaDataImport2::GetMethodSpecProps</span><span class="sxs-lookup"><span data-stu-id="74f3c-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="74f3c-103">Ottiene la firma dei metadati del metodo di MethodSpec specificato a cui fa riferimento token.</span><span class="sxs-lookup"><span data-stu-id="74f3c-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f3c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="74f3c-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="74f3c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="74f3c-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="74f3c-106">[in] Un token di MethodSpec che rappresenta la creazione dell'istanza del metodo.</span><span class="sxs-lookup"><span data-stu-id="74f3c-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="74f3c-107">[out] Puntatore al token MethodDef o MethodRef che rappresenta la definizione di metodo.</span><span class="sxs-lookup"><span data-stu-id="74f3c-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="74f3c-108">[out] Un puntatore per la firma binaria dei metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="74f3c-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="74f3c-109">[out] Le dimensioni, in byte, di `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="74f3c-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74f3c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="74f3c-110">Requirements</span></span>  
 <span data-ttu-id="74f3c-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74f3c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74f3c-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="74f3c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74f3c-113">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="74f3c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74f3c-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74f3c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74f3c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74f3c-115">See Also</span></span>  
 [<span data-ttu-id="74f3c-116">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="74f3c-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="74f3c-117">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="74f3c-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
