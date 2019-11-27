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
ms.openlocfilehash: 0542c518b64764ad27aa00b8d595be1191059436
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437454"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="86d7a-102">Metodo IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="86d7a-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="86d7a-103">Ottiene i flag che indicano la relazione tra il metodo a cui fa riferimento il token MethodDef specificato e la proprietà abbinata e l'evento a cui fa riferimento il token EventProp specificato.</span><span class="sxs-lookup"><span data-stu-id="86d7a-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86d7a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86d7a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86d7a-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="86d7a-106">in Token MethodDef che rappresenta il metodo per il quale ottenere le informazioni sul ruolo semantico.</span><span class="sxs-lookup"><span data-stu-id="86d7a-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="86d7a-107">in Token che rappresenta la proprietà abbinata e l'evento per il quale ottenere il ruolo del metodo.</span><span class="sxs-lookup"><span data-stu-id="86d7a-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="86d7a-108">out Puntatore ai flag di semantica associati.</span><span class="sxs-lookup"><span data-stu-id="86d7a-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="86d7a-109">Questo valore è una maschera di maschera dall'enumerazione [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="86d7a-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86d7a-110">Note</span><span class="sxs-lookup"><span data-stu-id="86d7a-110">Remarks</span></span>  
 <span data-ttu-id="86d7a-111">Il metodo [IMetaDataEmit::D efineproperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) imposta i flag di semantica di un metodo.</span><span class="sxs-lookup"><span data-stu-id="86d7a-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86d7a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86d7a-112">Requirements</span></span>  
 <span data-ttu-id="86d7a-113">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86d7a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86d7a-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="86d7a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86d7a-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="86d7a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86d7a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86d7a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d7a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86d7a-117">See also</span></span>

- [<span data-ttu-id="86d7a-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="86d7a-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="86d7a-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="86d7a-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
