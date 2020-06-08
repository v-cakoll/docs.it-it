---
title: Metodo IMetaDataImport::EnumMethods
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 91ae326a89e463d26b39c1659d872130042557bf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492016"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="c52d7-102">Metodo IMetaDataImport::EnumMethods</span><span class="sxs-lookup"><span data-stu-id="c52d7-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="c52d7-103">Enumera i token MethodDef che rappresentano i metodi del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="c52d7-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c52d7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c52d7-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,
   [in]  mdTypeDef      cl,
   [out] mdMethodDef    rMethods[],
   [in]  ULONG          cMax,
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c52d7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c52d7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c52d7-106">[in, out] Puntatore all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="c52d7-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c52d7-107">Deve essere NULL per la prima chiamata di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="c52d7-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="c52d7-108">in Token TypeDef che rappresenta il tipo con i metodi da enumerare.</span><span class="sxs-lookup"><span data-stu-id="c52d7-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="c52d7-109">out Matrice in cui archiviare i token MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c52d7-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c52d7-110">in Dimensione massima della `rMethods` matrice MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c52d7-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c52d7-111">out Numero di token MethodDef restituiti in `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="c52d7-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c52d7-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c52d7-112">Return Value</span></span>  
  
|<span data-ttu-id="c52d7-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c52d7-113">HRESULT</span></span>|<span data-ttu-id="c52d7-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c52d7-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c52d7-115">`EnumMethods`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="c52d7-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c52d7-116">Nessun token MethodDef da enumerare.</span><span class="sxs-lookup"><span data-stu-id="c52d7-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="c52d7-117">In tal caso, `pcTokens` è zero.</span><span class="sxs-lookup"><span data-stu-id="c52d7-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c52d7-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c52d7-118">Requirements</span></span>  
 <span data-ttu-id="c52d7-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c52d7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c52d7-120">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c52d7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c52d7-121">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c52d7-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c52d7-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c52d7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c52d7-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c52d7-123">See also</span></span>

- [<span data-ttu-id="c52d7-124">Interfaccia IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="c52d7-124">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c52d7-125">Interfaccia IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="c52d7-125">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
