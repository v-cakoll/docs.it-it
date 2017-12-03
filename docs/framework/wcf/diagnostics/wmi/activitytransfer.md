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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c1caf0ae27efce858328e5db88434253be61d50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
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
