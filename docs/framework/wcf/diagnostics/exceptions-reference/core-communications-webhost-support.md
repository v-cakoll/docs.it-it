---
title: 'Comunicazioni principali: supporto Webhost'
ms.date: 03/30/2017
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
ms.openlocfilehash: 724dc2eb66d058920fda07af899cd7464182c438
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471677"
---
# <a name="core-communications-webhost-support"></a>Comunicazioni principali: supporto Webhost
In questo argomento vengono elencate tutte le eccezioni generate dal supporto Webhost.  
  
## <a name="exception-list"></a>Elenco delle eccezioni  
  
|Codice risorsa|Stringa di risorsa|  
|-------------------|---------------------|  
|Hosting_CompatibilityServiceNotHosted|Il servizio richiede la compatibilità ASP.NET. Deve inoltre essere ospitato in IIS. Ospitare il servizio in IIS con la compatibilità ASP.NET abilitata in Web.config o impostare la proprietà AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode su un valore diverso da Required.|  
|Hosting_ListenerNotFoundForActivationInRecycling|Nessun canale è attualmente in ascolto all'indirizzo specificato. Se un'applicazione è in fase di riciclo, il servizio viene chiuso.|  
|Hosting_NonHTTPInCompatibilityMode|Gli unici protocolli supportati nella compatibilità ASP.NET sono HTTP e HTTPS. Rimuovere l'endpoint specificato o disabilitare la compatibilità ASP.NET per l'applicazione.|  
|Hosting_ProcessNotExecutingUnderHostedContext|Non è possibile richiamare il processo di hosting specificato all'interno dell'ambiente host corrente. L'API richiede che l'applicazione chiamante sia ospitata in Internet Information Services o nel servizio di attivazione dei processi di Windows.|  
|Hosting_ServiceCompatibilityRequire|Non è possibile attivare il servizio perché richiede la compatibilità ASP.NET. La compatibilità ASP.NET non è abilitata per questa applicazione. Abilitare la compatibilità ASP.NET nel file Web.config o impostare AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
