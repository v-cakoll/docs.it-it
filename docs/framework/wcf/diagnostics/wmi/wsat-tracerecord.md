---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>Sintassi  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe WSAT_TraceRecord non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe WSAT_TraceRecord dispone delle proprietà seguenti:  
  
### <a name="activityid"></a>ActivityID  
 Tipo di dati: oggetto  
Tipo di accesso: sola lettura  
  
 ID attività del record di traccia.  
  
### <a name="eventid"></a>EventID  
 Tipo di dati: sint32  
Tipo di accesso: sola lettura  
  
 ID evento del record di traccia.  
  
### <a name="tracerecord"></a>TraceRecord  
 Tipo di dati: stringa  
Tipo di accesso: sola lettura  
  
 Record di traccia  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|
