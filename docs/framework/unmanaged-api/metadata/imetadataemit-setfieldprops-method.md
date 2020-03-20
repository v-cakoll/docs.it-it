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
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177559"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="7b116-102">Metodo IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="7b116-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="7b116-103">Imposta o aggiorna il valore predefinito per il campo a cui fa riferimento il token di campo specificato.</span><span class="sxs-lookup"><span data-stu-id="7b116-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b116-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b116-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b116-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b116-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="7b116-106">[in] Token per il campo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7b116-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="7b116-107">[in] Attributi del campo.</span><span class="sxs-lookup"><span data-stu-id="7b116-107">[in] Field attributes.</span></span> <span data-ttu-id="7b116-108">Si tratta di `CorFieldAttr` una maschera di bit di valori.</span><span class="sxs-lookup"><span data-stu-id="7b116-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="7b116-109">[in] Oggetto `ELEMENT_TYPE_` *\** per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="7b116-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="7b116-110">Questo è `CorElementType` un valore.</span><span class="sxs-lookup"><span data-stu-id="7b116-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="7b116-111">Se non viene definita una costante, `ELEMENT_TYPE_END`impostare questo valore su .</span><span class="sxs-lookup"><span data-stu-id="7b116-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="7b116-112">[in] Valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="7b116-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="7b116-113">[in] La dimensione, in caratteri `pValue`Unicode, di .</span><span class="sxs-lookup"><span data-stu-id="7b116-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b116-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b116-114">Requirements</span></span>  
 <span data-ttu-id="7b116-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b116-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b116-116">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b116-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b116-117">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7b116-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7b116-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b116-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b116-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b116-119">See also</span></span>

- [<span data-ttu-id="7b116-120">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7b116-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7b116-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7b116-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
