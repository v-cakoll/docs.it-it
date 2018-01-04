---
title: Metodo IMetaDataEmit2::SaveDelta
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SaveDelta
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31b06f014a4638fd7f947e8188730c583183f176
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="b9869-102">Metodo IMetaDataEmit2::SaveDelta</span><span class="sxs-lookup"><span data-stu-id="b9869-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="b9869-103">Salva le modifiche dalla sessione di modifica e continuazione corrente nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="b9869-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9869-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9869-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9869-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9869-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="b9869-106">[in] Il nome del file in cui salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="b9869-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="b9869-107">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="b9869-107">[in] Reserved.</span></span> <span data-ttu-id="b9869-108">Deve essere zero.</span><span class="sxs-lookup"><span data-stu-id="b9869-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9869-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9869-109">Requirements</span></span>  
 <span data-ttu-id="b9869-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9869-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9869-111">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b9869-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9869-112">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9869-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9869-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9869-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9869-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9869-114">See Also</span></span>  
 [<span data-ttu-id="b9869-115">Interfaccia IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="b9869-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="b9869-116">Interfaccia IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="b9869-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
