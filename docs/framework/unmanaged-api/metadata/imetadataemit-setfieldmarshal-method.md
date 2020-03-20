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
ms.openlocfilehash: 1037cd4210605192870d43d88979b89af6536380
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175655"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="aef02-102">Metodo IMetaDataEmit::SetFieldMarshal</span><span class="sxs-lookup"><span data-stu-id="aef02-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="aef02-103">Imposta le informazioni di marshalling PInvoke per il campo, il metodo restituito o il parametro del metodo a cui fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="aef02-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aef02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aef02-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,
    [in]  PCCOR_SIGNATURE  pvNativeType,
    [in]  ULONG            cbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aef02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aef02-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="aef02-106">[in] Token per l'elemento di dati di destinazione.</span><span class="sxs-lookup"><span data-stu-id="aef02-106">[in] The token for target data item.</span></span> <span data-ttu-id="aef02-107">Si tratta `mdFieldDef` di `mdParamDef` un o un token.</span><span class="sxs-lookup"><span data-stu-id="aef02-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="aef02-108">[in] Firma per il tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="aef02-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="aef02-109">[in] Numero di byte `pvNativeType`in .</span><span class="sxs-lookup"><span data-stu-id="aef02-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aef02-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aef02-110">Requirements</span></span>  
 <span data-ttu-id="aef02-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aef02-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aef02-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aef02-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aef02-113">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aef02-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aef02-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aef02-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aef02-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aef02-115">See also</span></span>

- [<span data-ttu-id="aef02-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="aef02-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="aef02-117">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="aef02-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
