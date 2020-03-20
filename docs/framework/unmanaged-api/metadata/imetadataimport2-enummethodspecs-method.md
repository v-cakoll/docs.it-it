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
ms.openlocfilehash: 2df53ba53c64e042abc54a1d2ac043d301acdde9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177179"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="a2821-102">Metodo IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="a2821-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="a2821-103">Ottiene un enumeratore per una matrice di token MethodSpec associati al token MethodDef o MemberRef specificato.</span><span class="sxs-lookup"><span data-stu-id="a2821-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2821-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2821-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="a2821-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a2821-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a2821-106">[in, out] Puntatore all'enumeratore per `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="a2821-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="a2821-107">[in] Token MemberRef o MethodDef che rappresenta il metodo i cui token MethodSpec devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="a2821-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="a2821-108">Se il `tk` valore di è 0 (zero), tutti i token MethodSpec nell'ambito verranno enumerati.</span><span class="sxs-lookup"><span data-stu-id="a2821-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="a2821-109">[fuori] Matrice di token MethodSpec da enumerare.</span><span class="sxs-lookup"><span data-stu-id="a2821-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a2821-110">[in] Numero massimo richiesto di token `rMethodSpecs`da inserire in .</span><span class="sxs-lookup"><span data-stu-id="a2821-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="a2821-111">[fuori] Numero restituito di token inseriti in `rMethodSpecs`.</span><span class="sxs-lookup"><span data-stu-id="a2821-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2821-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a2821-112">Return Value</span></span>  
  
|<span data-ttu-id="a2821-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a2821-113">HRESULT</span></span>|<span data-ttu-id="a2821-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a2821-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a2821-115">`EnumMethodSpecs`restituito con successo.</span><span class="sxs-lookup"><span data-stu-id="a2821-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a2821-116">`phEnum`non ha elementi membro.</span><span class="sxs-lookup"><span data-stu-id="a2821-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="a2821-117">In questo `pcMethodSpecs` caso, è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a2821-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2821-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a2821-118">Requirements</span></span>  
 <span data-ttu-id="a2821-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2821-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2821-120">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a2821-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2821-121">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2821-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2821-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2821-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2821-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2821-123">See also</span></span>

- [<span data-ttu-id="a2821-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="a2821-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="a2821-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="a2821-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
