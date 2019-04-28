---
title: 213 - ServiceHostStarted
ms.date: 03/30/2017
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
ms.openlocfilehash: 819efa2e13c94e2c7a16c24f6ba9c7ef2b87ef8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781823"
---
# <a name="213---servicehoststarted"></a>213 - ServiceHostStarted
## <a name="properties"></a>Proprietà  
  
|||  
|-|-|  
|Id|213|  
|Parole chiave|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceHost|  
|Livello|LogAlways|  
|Canale|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Descrizione  
 Questo evento viene generato quando viene avviato un host del servizio ospitato su Web. Ciò si verifica in genere quando il servizio viene attivato da un messaggio, ma anche se viene configurato per essere avviato in modo automatico.  
  
## <a name="message"></a>Messaggio  
 ServiceHost avviato: '%1'.  
  
## <a name="details"></a>Dettagli  
  
|Nome elemento dati|Tipo elemento dati|Descrizione|  
|--------------------|--------------------|-----------------|  
|Nome tipo servizio|`xs:string`|Nome completo CLR del tipo di implementazione del servizio.|  
|HostReference|`xs:string`|Per i servizi ospitati su Web questo campo identifica in modo univoco il servizio nella gerarchia Web. Il formato viene definito come ' percorso virtuale dell'applicazione nome sito Web&#124;percorso virtuale del servizio&#124;ServiceName'. Esempio: ' Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.|  
|AppDomain|`xs:string`|Stringa restituita da AppDomain.CurrentDomain.FriendlyName.|
