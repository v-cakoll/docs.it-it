---
title: Interfaccia IDefinitionIdentity
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84c595bfdcca84ee43a53e2ea913cc978ae0953e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796533"
---
# <a name="idefinitionidentity-interface"></a>Interfaccia IDefinitionIdentity
Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Ottiene un puntatore a interfaccia a un `IDefinitionIdentity` nuovo oggetto identico `IDefinitionIdentity`a, ad eccezione delle modifiche di attributo specificate.|  
|`IDefinitionIdentity::EnumAttributes`|Ottiene un puntatore a interfaccia a un oggetto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) che contiene gli attributi associati `IDefinitionIdentity`all'oggetto.|  
|`IDefinitionIdentity::GetAttribute`|Ottiene il valore dell'attributo con il nome specificato nello spazio dei nomi specificato.|  
|`IDefinitionIdentity::SetAttribute`|Imposta l'attributo con il nome specificato nello spazio dei nomi specificato sul valore specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
