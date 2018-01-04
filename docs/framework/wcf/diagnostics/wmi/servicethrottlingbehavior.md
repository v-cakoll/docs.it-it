---
title: ServiceThrottlingBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ccf1c167c4d1a072737f725de2fa0c132ca686f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceThrottlingBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceThrottlingBehavior dispone delle proprietà seguenti:  
  
### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di messaggi elaborati attivamente in tutti gli oggetti dispatcher in un ServiceHost.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di oggetti servizio che possono essere eseguiti contemporaneamente.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 Tipo di dati: sint32  
  
 Tipo di accesso: sola lettura  
  
 Numero massimo di sessioni che un host può accettare contemporaneamente.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
