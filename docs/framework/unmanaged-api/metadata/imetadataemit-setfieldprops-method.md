---
title: Metodo IMetaDataEmit::SetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ba607669b4b1ca68294470cf1cc4fb27464d28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097655"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="d95fc-102">Metodo IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="d95fc-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="d95fc-103">Imposta o aggiorna il valore predefinito per il campo fa riferimento il token specificato.</span><span class="sxs-lookup"><span data-stu-id="d95fc-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d95fc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d95fc-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d95fc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d95fc-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="d95fc-106">[in] Il token per il campo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d95fc-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="d95fc-107">[in] Attributi di campo.</span><span class="sxs-lookup"><span data-stu-id="d95fc-107">[in] Field attributes.</span></span> <span data-ttu-id="d95fc-108">Si tratta di una maschera di bit delle `CorFieldAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="d95fc-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="d95fc-109">[in] Il `ELEMENT_TYPE_` *\** per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="d95fc-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="d95fc-110">Si tratta di un `CorElementType` valore.</span><span class="sxs-lookup"><span data-stu-id="d95fc-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="d95fc-111">Se non è definita una costante, impostare questo valore su `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="d95fc-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="d95fc-112">[in] Il valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="d95fc-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="d95fc-113">[in] Le dimensioni, in caratteri Unicode, di `pValue`.</span><span class="sxs-lookup"><span data-stu-id="d95fc-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d95fc-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d95fc-114">Requirements</span></span>  
 <span data-ttu-id="d95fc-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d95fc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d95fc-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d95fc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d95fc-117">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d95fc-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d95fc-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d95fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d95fc-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d95fc-119">See also</span></span>

- [<span data-ttu-id="d95fc-120">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d95fc-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d95fc-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d95fc-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
