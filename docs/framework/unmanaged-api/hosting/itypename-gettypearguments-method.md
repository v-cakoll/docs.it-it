---
title: Metodo ITypeName::GetTypeArguments
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ITypeName.GetTypeArguments
api_location: mscoree.dll
api_type: COM
f1_keywords: GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c580a6ff78668bdddda01f4892c6bb425bb2cab7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="e06ce-102">Metodo ITypeName::GetTypeArguments</span><span class="sxs-lookup"><span data-stu-id="e06ce-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="e06ce-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="e06ce-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e06ce-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e06ce-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e06ce-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e06ce-105">Requirements</span></span>  
 <span data-ttu-id="e06ce-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e06ce-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e06ce-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e06ce-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e06ce-108">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e06ce-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e06ce-109">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e06ce-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e06ce-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e06ce-110">See Also</span></span>  
 [<span data-ttu-id="e06ce-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="e06ce-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
