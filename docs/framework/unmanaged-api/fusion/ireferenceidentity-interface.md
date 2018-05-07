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
ms.openlocfilehash: 4708fa173725e4c91a13f5b92cdbb1fdf8a8a4d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ireferenceidentity-interface"></a>Interfaccia IReferenceIdentity
Rappresenta un riferimento alla firma univoca di un oggetto di codice.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|Ottiene un puntatore a interfaccia a un nuovo `IReferenceIdentity` istanza è uguale a `IReferenceIdentity`, tranne le modifiche di attributo specificato.|  
|`IReferenceIdentity::EnumAttributes`|Ottiene un puntatore a interfaccia a un `IEnumIDENTITY_ATTRIBUTE` istanza che contiene gli attributi associati a questo `IReferenceIdentity`.|  
|`IReferenceIdentity::GetAttribute`|Ottiene il valore dell'attributo nello spazio dei nomi specificato con il nome specificato.|  
|`IReferenceIdentity::SetAttribute`|Imposta l'attributo con lo spazio dei nomi specificato e il nome specificato per il valore specificato.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [Interfaccia IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
