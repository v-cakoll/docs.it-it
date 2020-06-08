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
ms.openlocfilehash: 8f6fbc570e7ea85aca5b365611d58a1700fb27cd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490718"
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="e8a66-102">Metodo IMetaDataImport2::EnumMethodSpecs</span><span class="sxs-lookup"><span data-stu-id="e8a66-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="e8a66-103">Ottiene un enumeratore per una matrice di token MethodSpec associati al token MethodDef o MemberRef specificato.</span><span class="sxs-lookup"><span data-stu-id="e8a66-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a66-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8a66-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="e8a66-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8a66-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e8a66-106">[in, out] Puntatore all'enumeratore per `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="e8a66-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="e8a66-107">in Token MemberRef o MethodDef che rappresenta il metodo i cui token MethodSpec devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="e8a66-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="e8a66-108">Se il valore di `tk` è 0 (zero), verranno enumerati tutti i token MethodSpec nell'ambito.</span><span class="sxs-lookup"><span data-stu-id="e8a66-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="e8a66-109">out Matrice di token MethodSpec da enumerare.</span><span class="sxs-lookup"><span data-stu-id="e8a66-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e8a66-110">in Numero massimo di token richiesto da inserire in `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="e8a66-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="e8a66-111">out Numero restituito di token inseriti in `rMethodSpecs` .</span><span class="sxs-lookup"><span data-stu-id="e8a66-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8a66-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e8a66-112">Return Value</span></span>  
  
|<span data-ttu-id="e8a66-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e8a66-113">HRESULT</span></span>|<span data-ttu-id="e8a66-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e8a66-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e8a66-115">`EnumMethodSpecs`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="e8a66-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e8a66-116">`phEnum`non contiene elementi Member.</span><span class="sxs-lookup"><span data-stu-id="e8a66-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="e8a66-117">In questo caso, `pcMethodSpecs` è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="e8a66-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8a66-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8a66-118">Requirements</span></span>  
 <span data-ttu-id="e8a66-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8a66-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8a66-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e8a66-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8a66-121">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="e8a66-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8a66-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8a66-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a66-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8a66-123">See also</span></span>

- [<span data-ttu-id="e8a66-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="e8a66-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="e8a66-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="e8a66-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
