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
ms.openlocfilehash: a55a8575a3f8ae04bcc4a148b588cd2361f81cf6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751503"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="be929-102">Metodo IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="be929-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="be929-103">Imposta i PInvoke informazioni di marshalling per il parametro di metodo viene restituito, campo o metodo fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="be929-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be929-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be929-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be929-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be929-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="be929-106">[in] Il token per l'elemento di dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="be929-106">[in] The token for target data item.</span></span> <span data-ttu-id="be929-107">Questo è un `mdFieldDef` o un `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="be929-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="be929-108">[in] La firma per il tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="be929-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="be929-109">[in] Il numero di byte in `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="be929-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be929-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be929-110">Requirements</span></span>  
 <span data-ttu-id="be929-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be929-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be929-112">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="be929-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be929-113">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="be929-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="be929-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be929-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be929-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be929-115">See also</span></span>

- [<span data-ttu-id="be929-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="be929-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="be929-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="be929-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
