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
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007819"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="64801-102">Metodo IMetaDataEmit::SetParamProps</span><span class="sxs-lookup"><span data-stu-id="64801-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="64801-103">Imposta o modifica le funzionalità di un parametro del metodo definito da una chiamata precedente a [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="64801-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64801-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64801-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="64801-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="64801-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="64801-106">in Token per il parametro di destinazione.</span><span class="sxs-lookup"><span data-stu-id="64801-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="64801-107">in Nome del parametro in formato Unicode.</span><span class="sxs-lookup"><span data-stu-id="64801-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="64801-108">in Flag per il parametro.</span><span class="sxs-lookup"><span data-stu-id="64801-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="64801-109">in ELEMENT_TYPE_ \* per il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="64801-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="64801-110">in Valore costante per il parametro.</span><span class="sxs-lookup"><span data-stu-id="64801-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="64801-111">in Dimensione in (Unicode) dei caratteri di `pValue` .</span><span class="sxs-lookup"><span data-stu-id="64801-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64801-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64801-112">Requirements</span></span>  
 <span data-ttu-id="64801-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64801-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64801-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="64801-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64801-115">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="64801-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64801-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64801-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64801-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64801-117">See also</span></span>

- [<span data-ttu-id="64801-118">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="64801-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="64801-119">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="64801-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
