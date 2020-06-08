---
title: Metodo IMetaDataImport::EnumMethodsWithName
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: 66a09baea1df2e2de418bdce8821672802f1f51f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491732"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="1762b-102">Metodo IMetaDataImport::EnumMethodsWithName</span><span class="sxs-lookup"><span data-stu-id="1762b-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="1762b-103">Enumera i metodi che hanno il nome specificato e che sono definiti dal tipo a cui fa riferimento il token TypeDef specificato.</span><span class="sxs-lookup"><span data-stu-id="1762b-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1762b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1762b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1762b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1762b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1762b-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="1762b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="1762b-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="1762b-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="1762b-108">in Token TypeDef che rappresenta il tipo di cui si desidera enumerare i metodi.</span><span class="sxs-lookup"><span data-stu-id="1762b-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="1762b-109">in Nome che limita l'ambito dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="1762b-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="1762b-110">out Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="1762b-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1762b-111">[in] Dimensione massima della matrice `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="1762b-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1762b-112">out Numero di token MethodDef restituiti in `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="1762b-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1762b-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="1762b-113">Remarks</span></span>  
 <span data-ttu-id="1762b-114">Questo metodo enumera i campi e i metodi, ma non le proprietà o gli eventi.</span><span class="sxs-lookup"><span data-stu-id="1762b-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="1762b-115">A differenza di [IMetaDataImport:: EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` Elimina tutti i token di metodo che non hanno il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="1762b-115">Unlike [IMetaDataImport::EnumMethods](imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1762b-116">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1762b-116">Return Value</span></span>  
  
|<span data-ttu-id="1762b-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1762b-117">HRESULT</span></span>|<span data-ttu-id="1762b-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1762b-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1762b-119">`EnumMethodsWithName`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="1762b-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1762b-120">Nessun token da enumerare.</span><span class="sxs-lookup"><span data-stu-id="1762b-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="1762b-121">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="1762b-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1762b-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1762b-122">Requirements</span></span>  
 <span data-ttu-id="1762b-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1762b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1762b-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1762b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1762b-125">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1762b-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1762b-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1762b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1762b-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1762b-127">See also</span></span>

- [<span data-ttu-id="1762b-128">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="1762b-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="1762b-129">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="1762b-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
