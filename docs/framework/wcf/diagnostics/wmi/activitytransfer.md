---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 480670f19407321eb0928d07752936b2ece1f7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484188"
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
