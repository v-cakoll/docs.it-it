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
ms.openlocfilehash: 13f8a50f3fcbe9d6e7602ca3bbeb36587ecff32c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778795"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="fdb96-102">Metodo IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="fdb96-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="fdb96-103">Ottiene un valore che indica se il campo, il metodo o il tipo rappresentato dal token di metadati specificato ha ambito globale.</span><span class="sxs-lookup"><span data-stu-id="fdb96-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdb96-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fdb96-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fdb96-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fdb96-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="fdb96-106">[in] Un token di metadati che rappresenta un tipo, un campo o metodo.</span><span class="sxs-lookup"><span data-stu-id="fdb96-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="fdb96-107">[out] 1 se l'oggetto ha un ambito globale; in caso contrario, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="fdb96-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdb96-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fdb96-108">Requirements</span></span>  
 <span data-ttu-id="fdb96-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdb96-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdb96-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fdb96-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fdb96-111">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="fdb96-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fdb96-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdb96-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb96-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdb96-113">See also</span></span>

- [<span data-ttu-id="fdb96-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="fdb96-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="fdb96-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="fdb96-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
