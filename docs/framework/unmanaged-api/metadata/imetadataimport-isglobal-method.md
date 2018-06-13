---
title: Metodo IMetaDataImport::IsGlobal
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsGlobal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsGlobal
helpviewer_keywords:
- IsGlobal method [.NET Framework metadata]
- IMetaDataImport::IsGlobal method [.NET Framework metadata]
ms.assetid: 44cf6908-f555-4ae8-b2cf-24bd974bf2fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4156c3507ccbd21d59893c5e03e15fe9b7322e48
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447798"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="f7c7c-102">Metodo IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="f7c7c-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="f7c7c-103">Ottiene un valore che indica se il campo, il metodo o il tipo rappresentato dal token di metadati specificato ha ambito globale.</span><span class="sxs-lookup"><span data-stu-id="f7c7c-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c7c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7c7c-104">Syntax</span></span>  
  
```  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7c7c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f7c7c-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="f7c7c-106">[in] Token di metadati che rappresenta un tipo, un campo o metodo.</span><span class="sxs-lookup"><span data-stu-id="f7c7c-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="f7c7c-107">[out] 1 se l'oggetto ha ambito globale. in caso contrario, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="f7c7c-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c7c-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7c7c-108">Requirements</span></span>  
 <span data-ttu-id="f7c7c-109">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7c7c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c7c-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f7c7c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7c7c-111">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f7c7c-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7c7c-112">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7c7c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7c7c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7c7c-113">See Also</span></span>  
 [<span data-ttu-id="f7c7c-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f7c7c-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f7c7c-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f7c7c-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
