---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|ID|3508|  
|Parole chiave|WFServices|  
|Livello|Dettagliato|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Indica che TrackingProfile non è presente nel file di configurazione o ActivityDefinitionId non corrisponde al profilo.  
  
## <a name="message"></a>Messaggio  
 Impossibile trovare TrackingProfile '%1' per ActivityDefinitionId '%2'. TrackingProfile non incluso nel file di configurazione o ActivityDefinitionId non corrisponde.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|Nome del profilo di rilevamento.|  
|ActivityDefinitionId|xs:string|ID di definizione dell'attività.|  
|AppDomain|xs:string|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
