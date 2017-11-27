---
title: Coclasse CLRRuntimeHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLRRuntimeHost Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CLRRuntimeHost
helpviewer_keywords: CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 372b2466baaa76ba47a6710447d93f9fa6bb967f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="clrruntimehost-coclass"></a>Coclasse CLRRuntimeHost
Fornisce interfacce per gestire l'esecuzione del codice dal runtime.  
  
## <a name="syntax"></a>Sintassi  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a>Interfacce  
  
|Interfaccia|Descrizione|  
|---------------|-----------------|  
|[ICLRRuntimeHost (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|Fornisce metodi per controllare l'esecuzione di applicazioni dal runtime.|  
|[ICLRValidator (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|Fornisce metodi per la convalida delle immagini di tipo PE e per la creazione di report dettagliati di errori di convalida.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Coclassi di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
