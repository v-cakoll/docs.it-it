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
ms.openlocfilehash: def77bb64e21b1421983cf263d488ecc1ddb9452
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009320"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="d6f02-102">Metodo IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="d6f02-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="d6f02-103">Ottiene un token di metadati per la stringa letterale specificata.</span><span class="sxs-lookup"><span data-stu-id="d6f02-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6f02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6f02-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineUserString (
    [in]  LPCWSTR     szString,
    [in]  ULONG       cchString,
    [out] mdString    *pstk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6f02-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d6f02-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="d6f02-106">in Stringa utente da archiviare.</span><span class="sxs-lookup"><span data-stu-id="d6f02-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="d6f02-107">in Numero di caratteri wide in `szString` .</span><span class="sxs-lookup"><span data-stu-id="d6f02-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="d6f02-108">out Token di stringa assegnato.</span><span class="sxs-lookup"><span data-stu-id="d6f02-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6f02-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6f02-109">Requirements</span></span>  
 <span data-ttu-id="d6f02-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6f02-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6f02-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d6f02-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6f02-112">**Libreria:** Usato come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d6f02-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6f02-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6f02-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f02-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6f02-114">See also</span></span>

- [<span data-ttu-id="d6f02-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="d6f02-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d6f02-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="d6f02-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
