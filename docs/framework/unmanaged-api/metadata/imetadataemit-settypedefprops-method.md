---
title: Metodo IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447725"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="41423-102">Metodo IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="41423-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="41423-103">Imposta le funzionalità di un tipo definito da una chiamata precedente a [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="41423-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41423-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="41423-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41423-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="41423-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="41423-106">in Token `mdTypeDef` ottenuto dalla chiamata originale a [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="41423-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="41423-107">[in] attributi `TypeDef`.</span><span class="sxs-lookup"><span data-stu-id="41423-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="41423-108">Si tratta di una maschera di maschera dei valori `CorTypeAttr`.</span><span class="sxs-lookup"><span data-stu-id="41423-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="41423-109">in `mdToken` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="41423-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="41423-110">Ottenuta da una chiamata precedente a [IMetaDataEmit::D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)o `null`.</span><span class="sxs-lookup"><span data-stu-id="41423-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="41423-111">in Matrice di token per le interfacce implementate da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="41423-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="41423-112">Questi token di `mdTypeRef` vengono ottenuti utilizzando [IMetaDataEmit::D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="41423-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="41423-113">L'ultimo elemento della matrice deve essere `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="41423-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41423-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="41423-114">Requirements</span></span>  
 <span data-ttu-id="41423-115">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41423-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41423-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="41423-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="41423-117">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="41423-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="41423-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41423-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41423-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="41423-119">See also</span></span>

- [<span data-ttu-id="41423-120">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="41423-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="41423-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="41423-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
