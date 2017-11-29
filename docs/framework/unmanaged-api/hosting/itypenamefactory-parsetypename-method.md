---
title: Metodo ITypeNameFactory::ParseTypeName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ITypeNameFactory.ParseTypeName
api_location: mscoree.dll
api_type: COM
f1_keywords: ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f80778196bc23a8cdaa8aff9917265a0ad379c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="8f262-102">Metodo ITypeNameFactory::ParseTypeName</span><span class="sxs-lookup"><span data-stu-id="8f262-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="8f262-103">Questo metodo supporta l'infrastruttura .NET Framework e non può essere utilizzato direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="8f262-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f262-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8f262-104">Syntax</span></span>  
  
```  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8f262-105">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8f262-105">Requirements</span></span>  
 <span data-ttu-id="8f262-106">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f262-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f262-107">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8f262-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f262-108">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f262-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f262-109">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f262-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f262-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8f262-110">See Also</span></span>  
 [<span data-ttu-id="8f262-111">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8f262-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
