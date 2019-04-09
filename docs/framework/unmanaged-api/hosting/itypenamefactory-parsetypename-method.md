---
title: Metodo ITypeNameFactory::ParseTypeName
ms.date: 03/30/2017
api_name:
- ITypeNameFactory.ParseTypeName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe5f634a5d0580c7e58b03f318da98a0112fa6b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208085"
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="057d3-102">Metodo ITypeNameFactory::ParseTypeName</span><span class="sxs-lookup"><span data-stu-id="057d3-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="057d3-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="057d3-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="057d3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="057d3-104">Syntax</span></span>  
  
```  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="057d3-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="057d3-105">Requirements</span></span>  
 <span data-ttu-id="057d3-106">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="057d3-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="057d3-107">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="057d3-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="057d3-108">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="057d3-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="057d3-109">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="057d3-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="057d3-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="057d3-110">See also</span></span>

- [<span data-ttu-id="057d3-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="057d3-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
