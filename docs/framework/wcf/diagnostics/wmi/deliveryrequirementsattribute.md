---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: d294ba4f14472012b9e311ee53742633b5173f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Sintassi  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe DeliveryRequirementsAttribute non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe DeliveryRequirementsAttribute dispone delle proprietà seguenti:  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Specifica se l'associazione di un servizio supporta i contratti.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Specifica se l'associazione supporta i messaggi ordinati.  
  
### <a name="targetcontract"></a>TargetContract  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Contratto a cui viene applicato.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
