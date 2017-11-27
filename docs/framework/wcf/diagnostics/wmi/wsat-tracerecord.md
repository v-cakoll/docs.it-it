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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3966311bc10b5ad2ee401ef9e3e13c8f36e14505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
