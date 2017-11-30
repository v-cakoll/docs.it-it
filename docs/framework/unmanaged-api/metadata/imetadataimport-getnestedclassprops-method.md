---
title: Metodo IMetaDataImport::GetNestedClassProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNestedClassProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a538cea5267b32790a9c656df9584d5ea31f54c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="8b319-102">Metodo IMetaDataImport::GetNestedClassProps</span><span class="sxs-lookup"><span data-stu-id="8b319-102">IMetaDataImport::GetNestedClassProps Method</span></span>
<span data-ttu-id="8b319-103">Ottiene il token TypeDef per l'elemento padre <xref:System.Type> dell'oggetto di tipo annidato.</span><span class="sxs-lookup"><span data-stu-id="8b319-103">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b319-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8b319-104">Syntax</span></span>  
  
```  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b319-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8b319-105">Parameters</span></span>  
 `tdNestedClass`  
 <span data-ttu-id="8b319-106">[in] Token TypeDef che rappresenta il <xref:System.Type> per restituire la classe padre per.</span><span class="sxs-lookup"><span data-stu-id="8b319-106">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="8b319-107">[out] Un puntatore al token TypeDef per il <xref:System.Type> che `tdNestedClass` è annidata in.</span><span class="sxs-lookup"><span data-stu-id="8b319-107">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b319-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8b319-108">Requirements</span></span>  
 <span data-ttu-id="8b319-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b319-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b319-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8b319-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b319-111">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b319-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b319-112">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b319-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b319-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b319-113">See Also</span></span>  
 [<span data-ttu-id="8b319-114">IMetaDataImport (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b319-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="8b319-115">IMetaDataImport2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8b319-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
