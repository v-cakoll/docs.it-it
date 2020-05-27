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
ms.openlocfilehash: 220556ec130c7bff7c413405820c4fee0582b051
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008014"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="5911c-102">Metodo IMetaDataEmit::SetFieldProps</span><span class="sxs-lookup"><span data-stu-id="5911c-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="5911c-103">Imposta o aggiorna il valore predefinito per il campo a cui fa riferimento il token di campo specificato.</span><span class="sxs-lookup"><span data-stu-id="5911c-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5911c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5911c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5911c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5911c-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="5911c-106">in Token per il campo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5911c-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="5911c-107">in Attributi di campo.</span><span class="sxs-lookup"><span data-stu-id="5911c-107">[in] Field attributes.</span></span> <span data-ttu-id="5911c-108">Si tratta di una maschera di maschera di `CorFieldAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="5911c-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5911c-109">in Oggetto `ELEMENT_TYPE_` *\** per il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="5911c-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="5911c-110">Si tratta di un `CorElementType` valore.</span><span class="sxs-lookup"><span data-stu-id="5911c-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="5911c-111">Se una costante non viene definita, impostare questo valore su `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="5911c-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5911c-112">in Valore costante per il campo.</span><span class="sxs-lookup"><span data-stu-id="5911c-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5911c-113">in Dimensione, in caratteri Unicode, di `pValue` .</span><span class="sxs-lookup"><span data-stu-id="5911c-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5911c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5911c-114">Requirements</span></span>  
 <span data-ttu-id="5911c-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5911c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5911c-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5911c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5911c-117">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5911c-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5911c-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5911c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5911c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5911c-119">See also</span></span>

- [<span data-ttu-id="5911c-120">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="5911c-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5911c-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="5911c-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
