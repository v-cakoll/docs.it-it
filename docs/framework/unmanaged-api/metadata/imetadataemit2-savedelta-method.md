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
ms.openlocfilehash: 7098bceee6bf60cd7781606ffc889b6af9c3e3cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445335"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="7c1ee-102">Metodo IMetaDataEmit2::SaveDelta</span><span class="sxs-lookup"><span data-stu-id="7c1ee-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="7c1ee-103">Salva le modifiche dalla sessione di modifica e continuazione corrente nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c1ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c1ee-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c1ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c1ee-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="7c1ee-106">[in] Il nome del file in cui salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="7c1ee-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-107">[in] Reserved.</span></span> <span data-ttu-id="7c1ee-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="7c1ee-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c1ee-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7c1ee-109">Requirements</span></span>  
 <span data-ttu-id="7c1ee-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c1ee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c1ee-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7c1ee-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7c1ee-112">**Libreria:** usata come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7c1ee-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7c1ee-113">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c1ee-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c1ee-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c1ee-114">See Also</span></span>  
 [<span data-ttu-id="7c1ee-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="7c1ee-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="7c1ee-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="7c1ee-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
