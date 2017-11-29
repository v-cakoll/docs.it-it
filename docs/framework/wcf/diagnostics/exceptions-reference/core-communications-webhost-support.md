---
title: 'Comunicazioni principali: supporto Webhost'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034c501f-96f9-4ef7-9602-3ac21788fd3e
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6697df69f7397514972e64d6845298c090af379f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
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
