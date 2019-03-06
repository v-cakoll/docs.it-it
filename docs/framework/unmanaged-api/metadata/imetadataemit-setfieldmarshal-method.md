---
title: Metodo IMetaDataEmit::SetFieldMarshal
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9842108e9a26d7cca621c06b8ae1713e17c97ebe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476360"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="83c07-102">Metodo IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="83c07-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="83c07-103">Imposta i PInvoke informazioni di marshalling per il parametro di metodo viene restituito, campo o metodo fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="83c07-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83c07-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83c07-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83c07-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83c07-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="83c07-106">[in] Il token per l'elemento di dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="83c07-106">[in] The token for target data item.</span></span> <span data-ttu-id="83c07-107">Questo è un `mdFieldDef` o un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="83c07-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="83c07-108">[in] La firma per il tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="83c07-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="83c07-109">[in] Il numero di byte in `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="83c07-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83c07-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83c07-110">Requirements</span></span>  
 <span data-ttu-id="83c07-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83c07-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83c07-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="83c07-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83c07-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="83c07-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83c07-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83c07-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83c07-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83c07-115">See also</span></span>
- [<span data-ttu-id="83c07-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="83c07-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="83c07-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="83c07-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
