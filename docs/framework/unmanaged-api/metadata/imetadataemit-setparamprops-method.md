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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b7cfba90edab44a0053fdfc759417ee7f074401
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132034"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="1c87e-102">Metodo IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="1c87e-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="1c87e-103">Imposta o modifica le funzionalità di un parametro del metodo che è stato definito da una chiamata precedente a [DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="1c87e-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c87e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c87e-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c87e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c87e-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="1c87e-106">[in] Il token per il parametro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1c87e-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="1c87e-107">[in] Il nome del parametro in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="1c87e-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="1c87e-108">[in] I flag per il parametro.</span><span class="sxs-lookup"><span data-stu-id="1c87e-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="1c87e-109">[in] L'ELEMENT_TYPE _ \* per il valore costante.</span><span class="sxs-lookup"><span data-stu-id="1c87e-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="1c87e-110">[in] Il valore costante per il parametro.</span><span class="sxs-lookup"><span data-stu-id="1c87e-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="1c87e-111">[in] La dimensione in caratteri (Unicode) della `pValue`.</span><span class="sxs-lookup"><span data-stu-id="1c87e-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c87e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c87e-112">Requirements</span></span>  
 <span data-ttu-id="1c87e-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c87e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c87e-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1c87e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c87e-115">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="1c87e-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c87e-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c87e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c87e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c87e-117">See also</span></span>

- [<span data-ttu-id="1c87e-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1c87e-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1c87e-119">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1c87e-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
