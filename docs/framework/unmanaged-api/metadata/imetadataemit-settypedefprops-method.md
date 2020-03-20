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
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177457"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="93e85-102">Metodo IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="93e85-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="93e85-103">Imposta le funzionalità di un tipo definito da una precedente chiamata a [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="93e85-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93e85-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="93e85-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93e85-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="93e85-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="93e85-106">[in] Token `mdTypeDef` ottenuto dalla chiamata originale a [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="93e85-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="93e85-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="93e85-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="93e85-108">Si tratta di `CorTypeAttr` una maschera di bit di valori.</span><span class="sxs-lookup"><span data-stu-id="93e85-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="93e85-109">[in] Oggetto `mdToken` della classe base.</span><span class="sxs-lookup"><span data-stu-id="93e85-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="93e85-110">Ottenuto da una precedente chiamata a [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), o `null`.</span><span class="sxs-lookup"><span data-stu-id="93e85-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="93e85-111">[in] Matrice di token per le interfacce implementate da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="93e85-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="93e85-112">Questi `mdTypeRef` token vengono ottenuti utilizzando [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="93e85-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="93e85-113">L'ultimo elemento della matrice `mdTokenNil`deve essere .</span><span class="sxs-lookup"><span data-stu-id="93e85-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93e85-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="93e85-114">Requirements</span></span>  
 <span data-ttu-id="93e85-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93e85-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93e85-116">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="93e85-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93e85-117">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="93e85-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="93e85-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93e85-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e85-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="93e85-119">See also</span></span>

- [<span data-ttu-id="93e85-120">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="93e85-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="93e85-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="93e85-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
