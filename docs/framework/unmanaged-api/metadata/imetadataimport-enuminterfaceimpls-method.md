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
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338057"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="38435-102">Metodo IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="38435-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="38435-103">Enumera tutte le interfacce implementate dal `TypeDef`specificato.</span><span class="sxs-lookup"><span data-stu-id="38435-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="38435-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38435-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38435-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38435-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="38435-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="38435-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="38435-107">in Token del TypeDef i cui token MethodDef che rappresentano le implementazioni dell'interfaccia devono essere enumerati.</span><span class="sxs-lookup"><span data-stu-id="38435-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="38435-108">out Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="38435-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="38435-109">in Lunghezza massima della matrice di `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="38435-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="38435-110">out Numero effettivo di token restituiti in `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="38435-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38435-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="38435-111">Return Value</span></span>  
  
|<span data-ttu-id="38435-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38435-112">HRESULT</span></span>|<span data-ttu-id="38435-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38435-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="38435-114">`EnumInterfaceImpls` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="38435-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="38435-115">Nessun token MethodDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="38435-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="38435-116">In tal caso, `pcImpls` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="38435-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="38435-117">Note</span><span class="sxs-lookup"><span data-stu-id="38435-117">Remarks</span></span>

<span data-ttu-id="38435-118">L'enumerazione restituisce una raccolta di token di `mdInterfaceImpl` per ogni interfaccia implementata dalla `TypeDef`specificata.</span><span class="sxs-lookup"><span data-stu-id="38435-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="38435-119">I token di interfaccia vengono restituiti nell'ordine in cui sono state specificate le interfacce (tramite `DefineTypeDef` o `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="38435-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="38435-120">È possibile eseguire query sulle proprietà dei token `mdInterfaceImpl` restituiti usando [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span><span class="sxs-lookup"><span data-stu-id="38435-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="38435-121">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="38435-121">Requirements</span></span>  
 <span data-ttu-id="38435-122">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38435-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38435-123">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="38435-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38435-124">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="38435-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38435-125">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38435-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38435-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38435-126">See also</span></span>

- [<span data-ttu-id="38435-127">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="38435-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="38435-128">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="38435-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
