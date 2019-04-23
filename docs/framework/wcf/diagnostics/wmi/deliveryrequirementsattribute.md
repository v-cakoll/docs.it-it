---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979212"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
  
 Tipo di accesso: Sola lettura  
  
 Specifica se l'associazione di un servizio supporta i contratti.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Specifica se l'associazione supporta i messaggi ordinati.  
  
### <a name="targetcontract"></a>TargetContract  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Contratto a cui viene applicato.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
