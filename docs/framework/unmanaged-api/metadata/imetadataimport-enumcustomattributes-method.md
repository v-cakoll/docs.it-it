---
title: Metodo IMetaDataImport::EnumCustomAttributes
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumCustomAttributes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumCustomAttributes
helpviewer_keywords:
- EnumCustomAttributes method [.NET Framework metadata]
- IMetaDataImport::EnumCustomAttributes method [.NET Framework metadata]
ms.assetid: 798513a0-68b1-4d04-bc5b-782a4445ea68
topic_type:
- apiref
ms.openlocfilehash: 9b0da8a06259fe99da52497da3011da94289d301
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492317"
---
# <a name="imetadataimportenumcustomattributes-method"></a><span data-ttu-id="0b156-102">Metodo IMetaDataImport::EnumCustomAttributes</span><span class="sxs-lookup"><span data-stu-id="0b156-102">IMetaDataImport::EnumCustomAttributes Method</span></span>
<span data-ttu-id="0b156-103">Enumera i token di definizione degli attributi personalizzati associati al tipo o al membro specificato.</span><span class="sxs-lookup"><span data-stu-id="0b156-103">Enumerates custom attribute-definition tokens associated with the specified type or member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b156-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b156-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumCustomAttributes (
   [in, out] HCORENUM      *phEnum,  
   [in]  mdToken            tk,
   [in]  mdToken            tkType,
   [out] mdCustomAttribute  rCustomAttributes[],
   [in]  ULONG              cMax,  
   [out, optional] ULONG   *pcCustomAttributes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b156-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b156-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0b156-106">[in, out] Puntatore all'enumeratore restituito.</span><span class="sxs-lookup"><span data-stu-id="0b156-106">[in, out] A pointer to the returned enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="0b156-107">in Token per l'ambito dell'enumerazione o zero per tutti gli attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0b156-107">[in] A token for the scope of the enumeration, or zero for all custom attributes.</span></span>  
  
 `tkType`  
 <span data-ttu-id="0b156-108">in Token per il costruttore del tipo degli attributi da enumerare o `null` per tutti i tipi.</span><span class="sxs-lookup"><span data-stu-id="0b156-108">[in] A token for the constructor of the type of the attributes to be enumerated, or `null` for all types.</span></span>  
  
 `rCustomAttributes`  
 <span data-ttu-id="0b156-109">out Matrice di token di attributi personalizzati.</span><span class="sxs-lookup"><span data-stu-id="0b156-109">[out] An array of custom attribute tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0b156-110">[in] Dimensione massima della matrice `rCustomAttributes`.</span><span class="sxs-lookup"><span data-stu-id="0b156-110">[in] The maximum size of the `rCustomAttributes` array.</span></span>  
  
 `pcCustomAttributes`  
 <span data-ttu-id="0b156-111">[out, facoltativo] Numero effettivo di valori di token restituiti in `rCustomAttributes` .</span><span class="sxs-lookup"><span data-stu-id="0b156-111">[out, optional] The actual number of token values returned in `rCustomAttributes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b156-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0b156-112">Return Value</span></span>  
  
|<span data-ttu-id="0b156-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0b156-113">HRESULT</span></span>|<span data-ttu-id="0b156-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b156-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0b156-115">`EnumCustomAttributes`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="0b156-115">`EnumCustomAttributes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0b156-116">Nessun attributo personalizzato da enumerare.</span><span class="sxs-lookup"><span data-stu-id="0b156-116">There are no custom attributes to enumerate.</span></span> <span data-ttu-id="0b156-117">In tal caso, `pcCustomAttributes` è zero.</span><span class="sxs-lookup"><span data-stu-id="0b156-117">In that case, `pcCustomAttributes` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b156-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b156-118">Requirements</span></span>  
 <span data-ttu-id="0b156-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b156-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b156-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0b156-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b156-121">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0b156-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b156-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b156-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b156-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b156-123">See also</span></span>

- [<span data-ttu-id="0b156-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="0b156-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0b156-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="0b156-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
