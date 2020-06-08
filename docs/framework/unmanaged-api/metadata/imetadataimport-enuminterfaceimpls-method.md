---
title: Metodo IMetaDataImport::EnumInterfaceImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: 910c40413075131765a37e00703ac892e3f39641
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492200"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="431a3-102">Metodo IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="431a3-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="431a3-103">Enumera tutte le interfacce implementate dall'oggetto specificato `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="431a3-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="431a3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="431a3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="431a3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="431a3-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="431a3-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="431a3-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="431a3-107">in Token del TypeDef i cui token MethodDef che rappresentano le implementazioni dell'interfaccia devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="431a3-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="431a3-108">out Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="431a3-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="431a3-109">in Lunghezza massima della `rImpls` matrice.</span><span class="sxs-lookup"><span data-stu-id="431a3-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="431a3-110">out Numero effettivo di token restituiti in `rImpls` .</span><span class="sxs-lookup"><span data-stu-id="431a3-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="431a3-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="431a3-111">Return Value</span></span>  
  
|<span data-ttu-id="431a3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="431a3-112">HRESULT</span></span>|<span data-ttu-id="431a3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="431a3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="431a3-114">`EnumInterfaceImpls`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="431a3-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="431a3-115">Nessun token MethodDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="431a3-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="431a3-116">In tal caso, `pcImpls` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="431a3-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="431a3-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="431a3-117">Remarks</span></span>

<span data-ttu-id="431a3-118">L'enumerazione restituisce una raccolta di `mdInterfaceImpl` token per ogni interfaccia implementata dall'oggetto specificato `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="431a3-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="431a3-119">I token di interfaccia vengono restituiti nell'ordine in cui sono state specificate le interfacce (tramite `DefineTypeDef` o `SetTypeDefProps` ).</span><span class="sxs-lookup"><span data-stu-id="431a3-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="431a3-120">`mdInterfaceImpl`È possibile eseguire query sulle proprietà dei token restituiti usando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="431a3-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="431a3-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="431a3-121">Requirements</span></span>  
 <span data-ttu-id="431a3-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="431a3-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="431a3-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="431a3-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="431a3-124">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="431a3-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="431a3-125">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="431a3-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="431a3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="431a3-126">See also</span></span>

- [<span data-ttu-id="431a3-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="431a3-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="431a3-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="431a3-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
