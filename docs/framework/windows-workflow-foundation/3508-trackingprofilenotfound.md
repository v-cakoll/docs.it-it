---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755571"
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|3508|  
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
