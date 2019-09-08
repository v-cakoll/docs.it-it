---
title: Interfaccia IReferenceIdentity
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2bb151d7c77104d8e24acefaac2e1f109b67f168
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796363"
---
# <a name="ireferenceidentity-interface"></a>Interfaccia IReferenceIdentity
Rappresenta un riferimento alla firma univoca di un oggetto di codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ottiene un puntatore a interfaccia a una `IReferenceIdentity` nuova istanza identica a questa `IReferenceIdentity`, ad eccezione delle modifiche di attributo specificate.|  
|`IReferenceIdentity::EnumAttributes`|Ottiene un puntatore a interfaccia a `IEnumIDENTITY_ATTRIBUTE` un'istanza di che contiene gli attributi associati `IReferenceIdentity`a questo oggetto.|  
|`IReferenceIdentity::GetAttribute`|Ottiene il valore dell'attributo nello spazio dei nomi specificato, con il nome specificato.|  
|`IReferenceIdentity::SetAttribute`|Imposta l'attributo con lo spazio dei nomi specificato e il nome specificato sul valore specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce Fusion](fusion-interfaces.md)
- [Interfaccia IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md)
