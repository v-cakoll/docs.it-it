---
title: Metodo IMetaDataImport2::EnumGenericParams
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
ms.openlocfilehash: 093e3edf0a3c06222ebc56a4876fca08d1b7578f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490729"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="c263f-102">Metodo IMetaDataImport2::EnumGenericParams</span><span class="sxs-lookup"><span data-stu-id="c263f-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="c263f-103">Ottiene un enumeratore per una matrice di token di parametro generici associati al token TypeDef o MethodDef specificato.</span><span class="sxs-lookup"><span data-stu-id="c263f-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c263f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c263f-104">Syntax</span></span>  
  
```cpp
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],
   [in]  ULONG            cMax,
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c263f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c263f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c263f-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c263f-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="c263f-107">in Token TypeDef o MethodDef i cui parametri generici devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="c263f-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="c263f-108">out Matrice di parametri generici da enumerare.</span><span class="sxs-lookup"><span data-stu-id="c263f-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c263f-109">in Numero massimo di token richiesto da inserire in `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="c263f-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="c263f-110">out Numero restituito di token inseriti in `rGenericParams` .</span><span class="sxs-lookup"><span data-stu-id="c263f-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c263f-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c263f-111">Return Value</span></span>  
  
|<span data-ttu-id="c263f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c263f-112">HRESULT</span></span>|<span data-ttu-id="c263f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c263f-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c263f-114">`EnumGenericParams`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c263f-114">`EnumGenericParams` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c263f-115">`phEnum`non contiene elementi Member.</span><span class="sxs-lookup"><span data-stu-id="c263f-115">`phEnum` has no member elements.</span></span> <span data-ttu-id="c263f-116">In questo caso, `pcGenericParams` è impostato su 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="c263f-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c263f-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c263f-117">Requirements</span></span>  
 <span data-ttu-id="c263f-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c263f-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c263f-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c263f-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c263f-120">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c263f-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c263f-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c263f-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c263f-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c263f-122">See also</span></span>

- [<span data-ttu-id="c263f-123">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c263f-123">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="c263f-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c263f-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
