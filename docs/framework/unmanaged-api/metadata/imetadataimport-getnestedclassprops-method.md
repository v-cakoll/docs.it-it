---
title: Metodo IMetaDataImport::GetNestedClassProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9e54b4c4b1b3184b6aa0d50f82a501312db6a8e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655660"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="b4319-102">Metodo IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="b4319-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="b4319-103">Ottiene il token TypeDef per l'elemento padre <xref:System.Type> specificato tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="b4319-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4319-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4319-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4319-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4319-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="b4319-106">[in] Token TypeDef che rappresentano il <xref:System.Type> per restituire la classe padre per token.</span><span class="sxs-lookup"><span data-stu-id="b4319-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="b4319-107">[out] Un puntatore al token TypeDef per il <xref:System.Type> che `tdNestedClass` è annidato all'interno.</span><span class="sxs-lookup"><span data-stu-id="b4319-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4319-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4319-108">Requirements</span></span>  
 <span data-ttu-id="b4319-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4319-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4319-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b4319-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4319-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="b4319-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4319-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4319-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4319-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4319-113">See also</span></span>
- [<span data-ttu-id="b4319-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="b4319-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b4319-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="b4319-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
