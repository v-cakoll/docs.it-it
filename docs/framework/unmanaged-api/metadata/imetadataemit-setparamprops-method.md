---
title: Metodo IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: 13220dcfdd260688494d5aebc50f94abf8a82215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177501"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="38d5d-102">Metodo IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="38d5d-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="38d5d-103">Imposta o modifica le funzionalità di un parametro di metodo definito da una precedente chiamata a [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="38d5d-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38d5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38d5d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38d5d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38d5d-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="38d5d-106">[in] Token per il parametro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="38d5d-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="38d5d-107">[in] Nome del parametro in Unicode.</span><span class="sxs-lookup"><span data-stu-id="38d5d-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="38d5d-108">[in] Flag per il parametro.</span><span class="sxs-lookup"><span data-stu-id="38d5d-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="38d5d-109">[in] Il valore di ELEMENT_TYPE_ per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="38d5d-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="38d5d-110">[in] Valore costante per il parametro.</span><span class="sxs-lookup"><span data-stu-id="38d5d-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="38d5d-111">[in] La dimensione in caratteri `pValue`(Unicode) di .</span><span class="sxs-lookup"><span data-stu-id="38d5d-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38d5d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38d5d-112">Requirements</span></span>  
 <span data-ttu-id="38d5d-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38d5d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38d5d-114">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38d5d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38d5d-115">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="38d5d-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38d5d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38d5d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38d5d-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38d5d-117">See also</span></span>

- [<span data-ttu-id="38d5d-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="38d5d-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="38d5d-119">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="38d5d-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
