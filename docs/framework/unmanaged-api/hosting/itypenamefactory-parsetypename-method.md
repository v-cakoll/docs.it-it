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
ms.openlocfilehash: adc72eb1b50369e5219798cdb99618abc5e08a00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440389"
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="3d9a1-102">Metodo ITypeNameFactory::ParseTypeName</span><span class="sxs-lookup"><span data-stu-id="3d9a1-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="3d9a1-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="3d9a1-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9a1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3d9a1-104">Syntax</span></span>  
  
```  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3d9a1-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3d9a1-105">Requirements</span></span>  
 <span data-ttu-id="3d9a1-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d9a1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9a1-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="3d9a1-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d9a1-108">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="3d9a1-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d9a1-109">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d9a1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d9a1-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d9a1-110">See Also</span></span>  
 [<span data-ttu-id="3d9a1-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="3d9a1-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
