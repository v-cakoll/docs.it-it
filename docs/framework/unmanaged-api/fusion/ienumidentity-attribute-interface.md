---
title: Interfaccia IEnumIDENTITY_ATTRIBUTE
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da6462a320b1f090940473f566ade91d36e74780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="ienumidentityattribute-interface"></a>Interfaccia IEnumIDENTITY_ATTRIBUTE
Funge da un enumeratore per gli attributi dell'oggetto codice nell'ambito corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|Ottiene un puntatore a interfaccia a un nuovo `IEnumIDENTITY_ATTRIBUTE` che contiene gli stessi membri di questo `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|Scrive i dati contenuti negli elementi di questo `IEnumIDENTITY_ATTRIBUTE` al buffer di dati specificato.|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|Ottiene il numero specificato di attributi, a partire dalla posizione corrente.|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|Sposta il puntatore all'istruzione all'inizio di questo `IEnumIDENTITY_ATTRIBUTE`.|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|Sposta in avanti il puntatore all'istruzione per il numero specificato di elementi, a partire dalla posizione corrente.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Isolation. h  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
