---
title: Metodo IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: b5af877c26c20bf64a27618bf24a7bce5b410419
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007780"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="4c160-102">Metodo IMetaDataEmit::SetPropertyProps</span><span class="sxs-lookup"><span data-stu-id="4c160-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="4c160-103">Imposta le funzionalità archiviate nei metadati per una proprietà definita da una chiamata precedente al [Metodo DefineProperty](imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="4c160-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c160-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c160-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c160-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c160-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="4c160-106">in Token per la proprietà da modificare</span><span class="sxs-lookup"><span data-stu-id="4c160-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="4c160-107">in Flag della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c160-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="4c160-108">in Tipo del valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c160-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="4c160-109">in Valore predefinito per la proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c160-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="4c160-110">in Numero di caratteri (Unicode) in `pValue` .</span><span class="sxs-lookup"><span data-stu-id="4c160-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="4c160-111">in Metodo che imposta il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c160-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="4c160-112">in Metodo che ottiene il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c160-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="4c160-113">in Matrice di altri metodi associati alla proprietà.</span><span class="sxs-lookup"><span data-stu-id="4c160-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="4c160-114">Termina la matrice con un `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="4c160-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c160-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c160-115">Requirements</span></span>  
 <span data-ttu-id="4c160-116">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c160-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c160-117">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4c160-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4c160-118">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4c160-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c160-119">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c160-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c160-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c160-120">See also</span></span>

- [<span data-ttu-id="4c160-121">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4c160-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4c160-122">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4c160-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
