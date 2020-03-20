---
title: Metodo IMetaDataEmit::DefineUserString
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
ms.openlocfilehash: a71d8694ec8c5bd35ecd3e98ed32e05bc7b382fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177623"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="e5665-102">Metodo IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="e5665-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="e5665-103">Ottiene un token di metadati per la stringa letterale specificata.</span><span class="sxs-lookup"><span data-stu-id="e5665-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5665-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e5665-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5665-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e5665-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="e5665-106">[in] Stringa utente da archiviare.</span><span class="sxs-lookup"><span data-stu-id="e5665-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="e5665-107">[in] Numero di caratteri `szString`di tipo "wide" in .</span><span class="sxs-lookup"><span data-stu-id="e5665-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="e5665-108">[fuori] Token di stringa assegnato.</span><span class="sxs-lookup"><span data-stu-id="e5665-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5665-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e5665-109">Requirements</span></span>  
 <span data-ttu-id="e5665-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5665-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5665-111">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e5665-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5665-112">**Biblioteca:** Utilizzato come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5665-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5665-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5665-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5665-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5665-114">See also</span></span>

- [<span data-ttu-id="e5665-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="e5665-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e5665-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="e5665-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
