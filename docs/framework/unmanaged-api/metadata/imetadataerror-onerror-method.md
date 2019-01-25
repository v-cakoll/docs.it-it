---
title: Metodo IMetaDataError::OnError
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ebb7fdbcf8c17991928df2dc621ec651b9cd4f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678720"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="0f40e-102">Metodo IMetaDataError::OnError</span><span class="sxs-lookup"><span data-stu-id="0f40e-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="0f40e-103">Fornisce la notifica degli errori che si verificano durante il merge dei metadati.</span><span class="sxs-lookup"><span data-stu-id="0f40e-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f40e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f40e-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f40e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f40e-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="0f40e-106">[in] Il valore di errore HRESULT restituito al metodo di chiamata.</span><span class="sxs-lookup"><span data-stu-id="0f40e-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="0f40e-107">[in] Il token di metadati dell'oggetto di codice che è stato unito quando si è verificato l'errore.</span><span class="sxs-lookup"><span data-stu-id="0f40e-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f40e-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f40e-108">Requirements</span></span>  
 <span data-ttu-id="0f40e-109">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f40e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f40e-110">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0f40e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f40e-111">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="0f40e-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f40e-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f40e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f40e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f40e-113">See also</span></span>
- [<span data-ttu-id="0f40e-114">Interfaccia IMetaDataError</span><span class="sxs-lookup"><span data-stu-id="0f40e-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
