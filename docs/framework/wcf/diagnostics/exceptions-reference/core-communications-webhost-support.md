---
title: 'Comunicazioni di base: supporto WebHost'
ms.date: 03/30/2017
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
ms.openlocfilehash: 8ee107ffcb9fab629541ce004d1c587fcad652c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61998712"
---
# <a name="core-communications-webhost-support"></a>Comunicazioni di base: supporto WebHost

In questo argomento vengono elencate tutte le eccezioni generate dal supporto Webhost.

## <a name="exception-list"></a>Elenco delle eccezioni

|Codice risorsa|Stringa di risorsa|
|-------------------|---------------------|
|Hosting_CompatibilityServiceNotHosted|Il servizio richiede la compatibilità ASP.NET. Deve inoltre essere ospitato in IIS. Ospitare il servizio in IIS con la compatibilità ASP.NET abilitata in Web.config o impostare la proprietà AspNetCompatibilityRequirementsAttribute.AspNetCompatibilityRequirementsMode su un valore diverso da Required.|
|Hosting_ListenerNotFoundForActivationInRecycling|Nessun canale è attualmente in ascolto all'indirizzo specificato. Se un'applicazione è in fase di riciclo, il servizio viene chiuso.|
|Hosting_NonHTTPInCompatibilityMode|Gli unici protocolli supportati nella compatibilità ASP.NET sono HTTP e HTTPS. Rimuovere l'endpoint specificato o disabilitare la compatibilità ASP.NET per l'applicazione.|
|Hosting_ProcessNotExecutingUnderHostedContext|Impossibile richiamare il processo di hosting specificato all'interno dell'ambiente host corrente. L'API richiede che l'applicazione chiamante sia ospitata in Internet Information Services o nel servizio di attivazione dei processi di Windows.|
|Hosting_ServiceCompatibilityRequire|Non è possibile attivare il servizio perché richiede la compatibilità ASP.NET. La compatibilità ASP.NET non è abilitata per questa applicazione. Abilitare la compatibilità ASP.NET nel file Web.config o impostare AspNetCompatibilityRequirementsAttribute.AspNetCompatibility.|
