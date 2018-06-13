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
ms.openlocfilehash: 401c23e44cc473d0a27a82a00343852693cb0f2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429345"
---
# <a name="idefinitionidentity-interface"></a>Interfaccia IDefinitionIdentity
Rappresenta la firma univoca del codice che definisce l'applicazione nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|Ottiene un puntatore a interfaccia a un nuovo `IDefinitionIdentity` oggetto è uguale a `IDefinitionIdentity`, tranne le modifiche di attributo specificato.|  
|`IDefinitionIdentity::EnumAttributes`|Ottiene un puntatore a interfaccia a un [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) oggetto che contiene gli attributi associati a questo `IDefinitionIdentity`.|  
|`IDefinitionIdentity::GetAttribute`|Ottiene il valore dell'attributo con il nome specificato nello spazio dei nomi specificato.|  
|`IDefinitionIdentity::SetAttribute`|Imposta l'attributo con il nome specificato nello spazio dei nomi specificato al valore specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
