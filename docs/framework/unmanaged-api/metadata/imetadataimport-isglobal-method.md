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
ms.openlocfilehash: d477976952d2c1875a620d1397fd43e5c5e2836f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503471"
---
# <a name="imetadataimportisglobal-method"></a><span data-ttu-id="69421-102">Metodo IMetaDataImport::IsGlobal</span><span class="sxs-lookup"><span data-stu-id="69421-102">IMetaDataImport::IsGlobal Method</span></span>
<span data-ttu-id="69421-103">Ottiene un valore che indica se il campo, il metodo o il tipo rappresentato dal token di metadati specificato ha ambito globale.</span><span class="sxs-lookup"><span data-stu-id="69421-103">Gets a value indicating whether the field, method, or type represented by the specified metadata token has global scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69421-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69421-104">Syntax</span></span>  
  
```cpp  
HRESULT IsGlobal (  
   [in]  mdToken     pd,  
   [out] int         *pbGlobal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69421-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69421-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="69421-106">in Token di metadati che rappresenta un tipo, un campo o un metodo.</span><span class="sxs-lookup"><span data-stu-id="69421-106">[in] A metadata token that represents a type, field, or method.</span></span>  
  
 `pbGlobal`  
 <span data-ttu-id="69421-107">[out] 1 se l'oggetto ha ambito globale; in caso contrario, 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="69421-107">[out] 1 if the object has global scope; otherwise, 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69421-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69421-108">Requirements</span></span>  
 <span data-ttu-id="69421-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69421-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69421-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="69421-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="69421-111">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="69421-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="69421-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69421-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69421-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69421-113">See also</span></span>

- [<span data-ttu-id="69421-114">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="69421-114">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="69421-115">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="69421-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
