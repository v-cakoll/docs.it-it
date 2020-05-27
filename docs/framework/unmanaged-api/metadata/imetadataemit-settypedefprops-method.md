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
ms.openlocfilehash: b05527f118de059c674ea659b1a22b7895126cf4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007767"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="4a716-102">Metodo IMetaDataEmit::SetTypeDefProps</span><span class="sxs-lookup"><span data-stu-id="4a716-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="4a716-103">Imposta le funzionalità di un tipo definito da una chiamata precedente a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="4a716-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a716-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a716-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a716-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a716-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="4a716-106">in `mdTypeDef`Token ottenuto dalla chiamata originale a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="4a716-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="4a716-107">[in] `TypeDef` attributi.</span><span class="sxs-lookup"><span data-stu-id="4a716-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="4a716-108">Si tratta di una maschera di maschera di `CorTypeAttr` valori.</span><span class="sxs-lookup"><span data-stu-id="4a716-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="4a716-109">in Oggetto `mdToken` della classe di base.</span><span class="sxs-lookup"><span data-stu-id="4a716-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="4a716-110">Ottenuta da una chiamata precedente a [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md), o `null` .</span><span class="sxs-lookup"><span data-stu-id="4a716-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="4a716-111">in Matrice di token per le interfacce implementate da questo tipo.</span><span class="sxs-lookup"><span data-stu-id="4a716-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="4a716-112">Questi `mdTypeRef` token vengono ottenuti utilizzando [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="4a716-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="4a716-113">L'ultimo elemento della matrice deve essere `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="4a716-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a716-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a716-114">Requirements</span></span>  
 <span data-ttu-id="4a716-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a716-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a716-116">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4a716-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a716-117">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a716-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a716-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a716-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a716-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a716-119">See also</span></span>

- [<span data-ttu-id="4a716-120">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="4a716-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4a716-121">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="4a716-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
