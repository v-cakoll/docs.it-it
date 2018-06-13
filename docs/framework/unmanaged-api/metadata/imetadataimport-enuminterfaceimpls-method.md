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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 824337a8a87282e59c9fc5df18c71800339e8d7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447459"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="561d4-102">Metodo IMetaDataImport::EnumInterfaceImpls</span><span class="sxs-lookup"><span data-stu-id="561d4-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="561d4-103">Enumera i token MethodDef che rappresentano le implementazioni dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="561d4-103">Enumerates MethodDef tokens representing interface implementations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="561d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="561d4-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="561d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="561d4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="561d4-106">[in, out] Un puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="561d4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="561d4-107">[in] Il token di TypeDef con token MethodDef che rappresentano le implementazioni di interfaccia sono da enumerare.</span><span class="sxs-lookup"><span data-stu-id="561d4-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="561d4-108">[out] Matrice utilizzata per archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="561d4-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="561d4-109">[in] Dimensione massima della matrice `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="561d4-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="561d4-110">[out] Il numero effettivo di token restituiti in `rImpls`.</span><span class="sxs-lookup"><span data-stu-id="561d4-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="561d4-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="561d4-111">Return Value</span></span>  
  
|<span data-ttu-id="561d4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="561d4-112">HRESULT</span></span>|<span data-ttu-id="561d4-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="561d4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="561d4-114">`EnumInterfaceImpls` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="561d4-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="561d4-115">Non sono presenti token MethodDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="561d4-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="561d4-116">In tal caso, `pcImpls` è impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="561d4-116">In that case, `pcImpls` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="561d4-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="561d4-117">Requirements</span></span>  
 <span data-ttu-id="561d4-118">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="561d4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="561d4-119">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="561d4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="561d4-120">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="561d4-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="561d4-121">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="561d4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="561d4-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="561d4-122">See Also</span></span>  
 [<span data-ttu-id="561d4-123">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="561d4-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="561d4-124">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="561d4-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
