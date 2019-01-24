---
title: Metodo IMetaDataImport::GetMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a12310f1281da99706589894a4793c2a28c5b938
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745973"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="7b2ab-102">Metodo IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="7b2ab-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="7b2ab-103">Ottiene i flag che indica la relazione tra il metodo fa riferimento il token MethodDef specificato e l'associazione di proprietà ed eventi di cui viene fatto riferimento EventProp specificato token.</span><span class="sxs-lookup"><span data-stu-id="7b2ab-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b2ab-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b2ab-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b2ab-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b2ab-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="7b2ab-106">[in] Token MethodDef che rappresenta il metodo per ottenere le informazioni sui ruoli semantico.</span><span class="sxs-lookup"><span data-stu-id="7b2ab-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="7b2ab-107">[in] Un token che rappresenta l'associazione di proprietà ed eventi per cui ottenere il ruolo del metodo.</span><span class="sxs-lookup"><span data-stu-id="7b2ab-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="7b2ab-108">[out] Puntatore ai flag semantica associata.</span><span class="sxs-lookup"><span data-stu-id="7b2ab-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="7b2ab-109">Questo valore è una maschera di bit di [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumerazione.</span><span class="sxs-lookup"><span data-stu-id="7b2ab-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b2ab-110">Note</span><span class="sxs-lookup"><span data-stu-id="7b2ab-110">Remarks</span></span>  
 <span data-ttu-id="7b2ab-111">Il [DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) metodo imposta i flag di semantica del metodo.</span><span class="sxs-lookup"><span data-stu-id="7b2ab-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b2ab-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b2ab-112">Requirements</span></span>  
 <span data-ttu-id="7b2ab-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b2ab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b2ab-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7b2ab-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b2ab-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7b2ab-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7b2ab-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b2ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b2ab-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b2ab-117">See also</span></span>
- [<span data-ttu-id="7b2ab-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="7b2ab-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7b2ab-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="7b2ab-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
