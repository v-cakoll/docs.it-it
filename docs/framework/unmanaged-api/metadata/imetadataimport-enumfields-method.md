---
title: Metodo IMetaDataImport::EnumFields
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumFields
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumFields
helpviewer_keywords:
- EnumFields method [.NET Framework metadata]
- IMetaDataImport::EnumFields method [.NET Framework metadata]
ms.assetid: 1d23247e-c58c-45db-afd8-83aa89cde18e
topic_type:
- apiref
ms.openlocfilehash: 1ff2dd64dc4797bc485550c30f7204644a3adb47
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492278"
---
# <a name="imetadataimportenumfields-method"></a><span data-ttu-id="6255c-102">Metodo IMetaDataImport::EnumFields</span><span class="sxs-lookup"><span data-stu-id="6255c-102">IMetaDataImport::EnumFields Method</span></span>
<span data-ttu-id="6255c-103">Enumera i token FieldDef per il tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="6255c-103">Enumerates FieldDef tokens for the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6255c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6255c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFields (
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [out]     mdFieldDef  rFields[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6255c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6255c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6255c-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="6255c-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="6255c-107">in Token TypeDef della classe i cui campi devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="6255c-107">[in] The TypeDef token of the class whose fields are to be enumerated.</span></span>  
  
 `rFields`  
 <span data-ttu-id="6255c-108">out Elenco di token FieldDef.</span><span class="sxs-lookup"><span data-stu-id="6255c-108">[out] The list of FieldDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6255c-109">[in] Dimensione massima della matrice `rFields`.</span><span class="sxs-lookup"><span data-stu-id="6255c-109">[in] The maximum size of the `rFields` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6255c-110">out Numero effettivo di token FieldDef restituiti in `rFields` .</span><span class="sxs-lookup"><span data-stu-id="6255c-110">[out] The actual number of FieldDef tokens returned in `rFields`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6255c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6255c-111">Return Value</span></span>  
  
|<span data-ttu-id="6255c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6255c-112">HRESULT</span></span>|<span data-ttu-id="6255c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6255c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6255c-114">`EnumFields`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="6255c-114">`EnumFields` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6255c-115">Nessun campo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="6255c-115">There are no fields to enumerate.</span></span> <span data-ttu-id="6255c-116">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="6255c-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6255c-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6255c-117">Requirements</span></span>  
 <span data-ttu-id="6255c-118">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6255c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6255c-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6255c-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6255c-120">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6255c-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6255c-121">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6255c-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6255c-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6255c-122">See also</span></span>

- [<span data-ttu-id="6255c-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="6255c-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6255c-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="6255c-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
