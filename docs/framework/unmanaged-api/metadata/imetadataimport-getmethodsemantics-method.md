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
ms.openlocfilehash: 2cfb66203d8f2d69ea188f6913a5ef34dd74791e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503601"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="ec498-102">Metodo IMetaDataImport::GetMethodSemantics</span><span class="sxs-lookup"><span data-stu-id="ec498-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="ec498-103">Ottiene i flag che indicano la relazione tra il metodo a cui fa riferimento il token MethodDef specificato e la proprietà abbinata e l'evento a cui fa riferimento il token EventProp specificato.</span><span class="sxs-lookup"><span data-stu-id="ec498-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec498-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec498-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec498-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec498-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="ec498-106">in Token MethodDef che rappresenta il metodo per il quale ottenere le informazioni sul ruolo semantico.</span><span class="sxs-lookup"><span data-stu-id="ec498-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="ec498-107">in Token che rappresenta la proprietà abbinata e l'evento per il quale ottenere il ruolo del metodo.</span><span class="sxs-lookup"><span data-stu-id="ec498-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="ec498-108">out Puntatore ai flag di semantica associati.</span><span class="sxs-lookup"><span data-stu-id="ec498-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="ec498-109">Questo valore è una maschera di maschera dall'enumerazione [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ec498-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec498-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ec498-110">Remarks</span></span>  
 <span data-ttu-id="ec498-111">Il metodo [IMetaDataEmit::D efineproperty](imetadataemit-defineproperty-method.md) imposta i flag di semantica di un metodo.</span><span class="sxs-lookup"><span data-stu-id="ec498-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec498-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec498-112">Requirements</span></span>  
 <span data-ttu-id="ec498-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec498-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec498-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec498-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec498-115">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ec498-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec498-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec498-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec498-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec498-117">See also</span></span>

- [<span data-ttu-id="ec498-118">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ec498-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ec498-119">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ec498-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
