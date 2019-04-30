---
title: Metodo IMetaDataImport2::EnumMethodSpecs
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a3641fcda33a497293dbf87b419c8606847dc296
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049843"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="366d6-102">Metodo IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="366d6-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="366d6-103">Ottiene un enumeratore per una matrice dei token MethodSpec Neobsahuje associati MethodDef specificato o MemberRef token.</span><span class="sxs-lookup"><span data-stu-id="366d6-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="366d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="366d6-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="366d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="366d6-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="366d6-106">[in, out] Un puntatore all'enumeratore per `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="366d6-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="366d6-107">[in] Il token MethodDef o MemberRef che rappresenta il metodo il cui token MethodSpec Neobsahuje sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="366d6-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="366d6-108">Se il valore di `tk` è 0 (zero), verranno enumerati tutti i token MethodSpec Neobsahuje nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="366d6-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="366d6-109">[out] Matrice dei token MethodSpec Neobsahuje da enumerare.</span><span class="sxs-lookup"><span data-stu-id="366d6-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="366d6-110">[in] Il numero massimo di richiesto di token da inserire `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="366d6-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="366d6-111">[out] Il numero restituito dei token inserito in `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="366d6-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="366d6-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="366d6-112">Return Value</span></span>  
  
|<span data-ttu-id="366d6-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="366d6-113">HRESULT</span></span>|<span data-ttu-id="366d6-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="366d6-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="366d6-115">`EnumMethodSpecs` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="366d6-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="366d6-116">`phEnum` non ha membro elementi.</span><span class="sxs-lookup"><span data-stu-id="366d6-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="366d6-117">In questo caso, `pcMethodSpecs` è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="366d6-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="366d6-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="366d6-118">Requirements</span></span>  
 <span data-ttu-id="366d6-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="366d6-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="366d6-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="366d6-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="366d6-121">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="366d6-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="366d6-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="366d6-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="366d6-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="366d6-123">See also</span></span>

- [<span data-ttu-id="366d6-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="366d6-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="366d6-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="366d6-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
