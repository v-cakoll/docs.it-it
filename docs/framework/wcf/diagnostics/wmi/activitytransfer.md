---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="activitytransfer"></a>ActivityTransfer
Evento trasferimento attività  
  
## <a name="syntax"></a>Sintassi  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ActivityTransfer non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ActivityTransfer dispone delle proprietà seguenti:  
  
### <a name="activityid"></a>ActivityID  
  
-   Tipo di dati: oggetto  
    Tipo di accesso: sola lettura  
  
-   ID attività  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
-   Tipo di dati: oggetto  
    Tipo di accesso: sola lettura  
  
-   ID attività correlata  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel.|
