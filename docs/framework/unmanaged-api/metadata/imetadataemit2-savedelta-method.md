---
title: Metodo IMetaDataEmit2::SaveDelta
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a1963221942134d148d5417ebafea97a26aead5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494285"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="942d6-102">Metodo IMetaDataEmit2::SaveDelta</span><span class="sxs-lookup"><span data-stu-id="942d6-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="942d6-103">Salva le modifiche dalla sessione corrente di modifica e continuazione per il file specificato.</span><span class="sxs-lookup"><span data-stu-id="942d6-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="942d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="942d6-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="942d6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="942d6-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="942d6-106">[in] Il nome del file in cui salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="942d6-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="942d6-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="942d6-107">[in] Reserved.</span></span> <span data-ttu-id="942d6-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="942d6-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="942d6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="942d6-109">Requirements</span></span>  
 <span data-ttu-id="942d6-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="942d6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="942d6-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="942d6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="942d6-112">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="942d6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="942d6-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="942d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="942d6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="942d6-114">See also</span></span>
- [<span data-ttu-id="942d6-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="942d6-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="942d6-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="942d6-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
