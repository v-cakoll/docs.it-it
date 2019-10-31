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
ms.openlocfilehash: 5114f74e80da925c7a153b9e481c54067152eaec
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108208"
---
# <a name="idefinitionappid-interface"></a>Interfaccia IDefinitionAppId
Rappresenta un identificatore univoco per il codice che definisce l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|Ottiene una stringa formattata che rappresenta il codice in questo oggetto `IDefinitionAppId`.|  
|`IDefinitionAppId::put_Codebase`|Imposta il codice di questo oggetto `IDefinitionAppId` sul valore stringa formattato specificato.|  
|`IDefinitionAppId::EnumAppPath`|Ottiene un puntatore a interfaccia a un oggetto [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) che contiene gli assembly nel percorso dell'applicazione corrente.|  
|`IDefinitionAppId::SetAppPath`|Imposta il percorso dell'applicazione per l'assembly nell'ambito corrente sul valore a cui fa riferimento l'oggetto [IDefinitionIdentity](idefinitionidentity-interface.md) specificato.|  
|`IDefinitionAppId::get_SubscriptionId`|Ottiene un puntatore a una rappresentazione di stringa dell'identificatore del token per una sottoscrizione a questo oggetto `IDefinitionAppId`.|  
|`IDefinitionAppId::put_SubscriptionId`|Imposta l'identificatore del token per una sottoscrizione a questo oggetto `IDefinitionAppId` sul valore stringa specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
