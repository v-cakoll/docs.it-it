---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40bdc27337daae02795137fc3ac67575787018c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
