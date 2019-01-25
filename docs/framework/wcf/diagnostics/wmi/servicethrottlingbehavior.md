---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 98e8a720e92547ca0a893dd988b91cb7907660b5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689851"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
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
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di messaggi elaborati attivamente in tutti gli oggetti dispatcher in un ServiceHost.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di oggetti servizio che possono essere eseguiti contemporaneamente.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 Tipo di dati: sint32  
  
 Tipo di accesso: Sola lettura  
  
 Numero massimo di sessioni che un host può accettare contemporaneamente.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
