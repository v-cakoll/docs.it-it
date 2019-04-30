---
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: 1776252c362feb3c3ebc04651603944040ceee7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61999752"
---
# <a name="401--stopsignpostevent"></a>401- StopSignPostEvent
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|401|  
|Parole chiave|Risoluzione dei problemi|  
|Livello|Informazioni|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento contrassegna la fine di un'attività end-to-end contenente il nome dell’attività.  
  
## <a name="message"></a>Messaggio  
 Limite dell'attività.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Dati estesi|`xs:string`|Nome dell'attività.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
