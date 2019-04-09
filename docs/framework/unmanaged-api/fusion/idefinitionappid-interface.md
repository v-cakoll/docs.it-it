---
title: Interfaccia IDefinitionAppId
ms.date: 03/30/2017
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bd705ef549de3a8018efe731ef8735ef7b6b915
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083179"
---
# <a name="idefinitionappid-interface"></a>Interfaccia IDefinitionAppId
Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Ottiene una stringa formattata che rappresenta il codice riportato in questa `IDefinitionAppId` oggetto.|  
|`IDefinitionAppId::put_Codebase`|Imposta il codice di questo `IDefinitionAppId` valore della stringa formattata di oggetti specificata.|  
|`IDefinitionAppId::EnumAppPath`|Ottiene un puntatore a interfaccia a un [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) oggetto che contiene gli assembly nel percorso dell'applicazione corrente.|  
|`IDefinitionAppId::SetAppPath`|Imposta il percorso dell'applicazione per l'assembly nell'ambito corrente sul valore specificato fa riferimento [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) oggetto.|  
|`IDefinitionAppId::get_SubscriptionId`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a questo `IDefinitionAppId` oggetto.|  
|`IDefinitionAppId::put_SubscriptionId`|Imposta l'identificatore del token per una sottoscrizione a questo `IDefinitionAppId` oggetto con il valore di stringa specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
