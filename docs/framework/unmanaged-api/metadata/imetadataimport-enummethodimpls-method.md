---
title: Metodo IMetaDataImport::EnumMethodImpls
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: b8fabea78f85448e39fc6d31f0a7969458343877
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492009"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="ee4ca-102">Metodo IMetaDataImport::EnumMethodImpls</span><span class="sxs-lookup"><span data-stu-id="ee4ca-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="ee4ca-103">Enumera i token MethodBody e MethodDeclaration che rappresentano i metodi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee4ca-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee4ca-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee4ca-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee4ca-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ee4ca-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ee4ca-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="ee4ca-108">in Token TypeDef per il tipo di cui è necessario enumerare le implementazioni del metodo.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="ee4ca-109">out Matrice in cui archiviare i token MethodBody.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="ee4ca-110">out Matrice in cui archiviare i token MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ee4ca-111">in Dimensioni massime delle `rMethodBody` matrici e `rMethodDecl` .</span><span class="sxs-lookup"><span data-stu-id="ee4ca-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ee4ca-112">in Numero effettivo di metodi restituiti in `rMethodBody` e `rMethodDecl` .</span><span class="sxs-lookup"><span data-stu-id="ee4ca-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee4ca-113">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ee4ca-113">Return Value</span></span>  
  
|<span data-ttu-id="ee4ca-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ee4ca-114">HRESULT</span></span>|<span data-ttu-id="ee4ca-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ee4ca-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ee4ca-116">`EnumMethodImpls`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ee4ca-117">Nessun token di metodo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="ee4ca-118">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="ee4ca-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee4ca-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee4ca-119">Requirements</span></span>  
 <span data-ttu-id="ee4ca-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee4ca-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee4ca-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ee4ca-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ee4ca-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ee4ca-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ee4ca-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee4ca-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee4ca-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee4ca-124">See also</span></span>

- [<span data-ttu-id="ee4ca-125">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="ee4ca-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ee4ca-126">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="ee4ca-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
