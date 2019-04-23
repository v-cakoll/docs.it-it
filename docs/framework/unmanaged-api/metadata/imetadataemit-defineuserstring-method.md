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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f24dd3864be1bda454ac5e863f3fa2caf736bda9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59215222"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="acd33-102">Metodo IMetaDataEmit::DefineUserString</span><span class="sxs-lookup"><span data-stu-id="acd33-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="acd33-103">Ottiene i metadati di un token per la stringa letterale specificata.</span><span class="sxs-lookup"><span data-stu-id="acd33-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acd33-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="acd33-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acd33-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="acd33-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="acd33-106">[in] Stringa utente da archiviare.</span><span class="sxs-lookup"><span data-stu-id="acd33-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="acd33-107">[in] Il numero di caratteri "wide" in `szString`.</span><span class="sxs-lookup"><span data-stu-id="acd33-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="acd33-108">[out] Il token di stringa assegnato.</span><span class="sxs-lookup"><span data-stu-id="acd33-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acd33-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="acd33-109">Requirements</span></span>  
 <span data-ttu-id="acd33-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acd33-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acd33-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="acd33-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acd33-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="acd33-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acd33-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acd33-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd33-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acd33-114">See also</span></span>

- [<span data-ttu-id="acd33-115">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="acd33-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="acd33-116">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="acd33-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
