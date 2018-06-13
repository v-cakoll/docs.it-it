---
title: Metodo ITypeName::GetTypeArguments
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77b3a898dd929a6eeadc466a04a0fdb10571ed7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440161"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="2c2b3-102">Metodo ITypeName::GetTypeArguments</span><span class="sxs-lookup"><span data-stu-id="2c2b3-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="2c2b3-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="2c2b3-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c2b3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c2b3-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2c2b3-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c2b3-105">Requirements</span></span>  
 <span data-ttu-id="2c2b3-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c2b3-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c2b3-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2c2b3-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c2b3-108">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2c2b3-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c2b3-109">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c2b3-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c2b3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c2b3-110">See Also</span></span>  
 [<span data-ttu-id="2c2b3-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="2c2b3-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
