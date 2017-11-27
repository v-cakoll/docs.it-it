---
title: Interfaccia IDefinitionAppId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionAppId
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionAppId
helpviewer_keywords: IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 382c82ff773d0ab1c046fc131fa87a4f74d19ea6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="idefinitionappid-interface"></a>Interfaccia IDefinitionAppId
Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Ottiene una stringa formattata che rappresenta il codice in questo `IDefinitionAppId` oggetto.|  
|`IDefinitionAppId::put_Codebase`|Imposta il codice di questo `IDefinitionAppId` valore di stringa formattato dell'oggetto specificato.|  
|`IDefinitionAppId::EnumAppPath`|Ottiene un puntatore a interfaccia a un [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) oggetto che contiene gli assembly nel percorso dell'applicazione corrente.|  
|`IDefinitionAppId::SetAppPath`|Imposta il percorso dell'applicazione per l'assembly nell'ambito corrente sul valore specificato fa riferimento [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) oggetto.|  
|`IDefinitionAppId::get_SubscriptionId`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore di token per una sottoscrizione a questo `IDefinitionAppId` oggetto.|  
|`IDefinitionAppId::put_SubscriptionId`|Imposta l'identificatore del token per una sottoscrizione a questo `IDefinitionAppId` oggetto con il valore di stringa specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Fusion (interfacce)](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
