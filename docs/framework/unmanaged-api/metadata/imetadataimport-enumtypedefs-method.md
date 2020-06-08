---
title: Metodo IMetaDataImport::EnumTypeDefs
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeDefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeDefs
helpviewer_keywords:
- EnumTypeDefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeDefs method [.NET Framework metadata]
ms.assetid: 4e508711-da92-4381-aaf8-6803075cdaa2
topic_type:
- apiref
ms.openlocfilehash: cdfd4e10236d546af2555b125d44233172849a21
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503731"
---
# <a name="imetadataimportenumtypedefs-method"></a><span data-ttu-id="4455c-102">Metodo IMetaDataImport::EnumTypeDefs</span><span class="sxs-lookup"><span data-stu-id="4455c-102">IMetaDataImport::EnumTypeDefs Method</span></span>
<span data-ttu-id="4455c-103">Enumera i token TypeDef che rappresentano tutti i tipi all'interno dell'ambito corrente.</span><span class="sxs-lookup"><span data-stu-id="4455c-103">Enumerates TypeDef tokens representing all types within the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4455c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4455c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeDefs (  
   [out] HCORENUM   *phEnum,
   [in]  mdTypeDef  rTypeDefs[],  
   [in]  ULONG      cMax,
   [out] ULONG      *pcTypeDefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4455c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4455c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4455c-106">out Puntatore al nuovo enumeratore.</span><span class="sxs-lookup"><span data-stu-id="4455c-106">[out] A pointer to the new enumerator.</span></span> <span data-ttu-id="4455c-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="4455c-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeDefs`  
 <span data-ttu-id="4455c-108">in Matrice utilizzata per archiviare i token TypeDef.</span><span class="sxs-lookup"><span data-stu-id="4455c-108">[in] The array used to store the TypeDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4455c-109">[in] Dimensione massima della matrice `rTypeDefs`.</span><span class="sxs-lookup"><span data-stu-id="4455c-109">[in] The maximum size of the `rTypeDefs` array.</span></span>  
  
 `pcTypeDefs`  
 <span data-ttu-id="4455c-110">out Numero di token TypeDef restituiti in `rTypeDefs` .</span><span class="sxs-lookup"><span data-stu-id="4455c-110">[out] The number of TypeDef tokens returned in `rTypeDefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4455c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4455c-111">Return Value</span></span>  
  
|<span data-ttu-id="4455c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4455c-112">HRESULT</span></span>|<span data-ttu-id="4455c-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4455c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4455c-114">`EnumTypeDefs`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="4455c-114">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4455c-115">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="4455c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4455c-116">In tal caso, `pcTypeDefs` è zero.</span><span class="sxs-lookup"><span data-stu-id="4455c-116">In that case, `pcTypeDefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4455c-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4455c-117">Remarks</span></span>  
 <span data-ttu-id="4455c-118">Il token TypeDef rappresenta un tipo come una classe o un'interfaccia, nonché qualsiasi tipo aggiunto tramite un meccanismo di estendibilità.</span><span class="sxs-lookup"><span data-stu-id="4455c-118">The TypeDef token represents a type such as a class or an interface, as well as any type added via an extensibility mechanism.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4455c-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4455c-119">Requirements</span></span>  
 <span data-ttu-id="4455c-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4455c-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4455c-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4455c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4455c-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4455c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4455c-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4455c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4455c-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4455c-124">See also</span></span>

- [<span data-ttu-id="4455c-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="4455c-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4455c-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="4455c-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
