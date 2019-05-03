---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964295"
---
# <a name="activitytransfer"></a>ActivityTransfer
Evento trasferimento attività  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
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
  
- Tipo di dati: oggetto  
    Tipo di accesso: Sola lettura  
  
- ID attività  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
- Tipo di dati: oggetto  
    Tipo di accesso: Sola lettura  
  
- ID attività correlata  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel.|
