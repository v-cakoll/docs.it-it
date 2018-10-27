---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/25/2018
ms.locfileid: "50046279"
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
  
### <a name="eventid"></a>ID evento  
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
