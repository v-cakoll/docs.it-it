---
title: Supporto delle associazioni a più siti IIS
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a4b586b4d5c3c37355bf7b05a8a0227565a5b5e5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="supporting-multiple-iis-site-bindings"></a>Supporto delle associazioni a più siti IIS
Se si ospita un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in Internet Information Services (IIS) 7.0, potrebbe risultare opportuno fornire più indirizzi di base che utilizzano lo stesso protocollo per lo stesso sito. In questo modo lo stesso servizio può rispondere a diversi URI. Ciò è utile quando si desidera ospitare un servizio in attesa sulla stessa http://www.contoso.com e http://contoso.com. È inoltre utile per creare un servizio che dispone di un indirizzo di base per gli utenti interni e un indirizzo di base separato per gli utenti esterni. Ad esempio: http://internal.contoso.com e http://www.contoso.com.  
  
> [!NOTE]
>  Questa funzionalità è disponibile solo utilizzando il protocollo HTTP.  
  
## <a name="multiple-base-addresses"></a>Più indirizzi di base  
 Questa funzionalità è disponibile solo per i servizi [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ospitati in IIS. Per impostazione predefinita questa funzionalità non è abilitata. Per abilitare la funzionalità è necessario aggiungere il `multipleSiteBindingsEnabled` attributo per il <`serviceHostingEnvironment`> elemento nel file Web. config file e impostarlo su `true`, come illustrato nell'esempio seguente.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Se si ospita un servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in IIS, quest'ultimo crea un indirizzo di base basato sull'URI della directory virtuale che contiene l'applicazione. È possibile aggiungere ulteriori indirizzi di base che utilizzano lo stesso protocollo mediante Gestione Internet Information Services per aggiungere una o più associazioni al sito Web. Per ogni associazione specificare un protocollo (HTTP o HTTPS), un indirizzo IP, una porta e un nome host. Per ulteriori informazioni sull'utilizzo di Gestione Internet Information Services, vedere [Gestione IIS (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057). Per ulteriori informazioni sull'aggiunta di associazioni per un sito, vedere [creare un sito Web (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)  
  
 L'impostazione di più indirizzi di base per lo stesso sito influisce sul contenuto della pagina della Guida di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], sullo schema di importazione e sulle informazioni WSDL/MEX generate dal servizio. Nella pagina della Guida di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] viene visualizzata la riga di comando da utilizzare per generare un client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in grado di comunicare con il servizio. La riga di comando contiene solo il primo indirizzo specificato nell'associazione IIS per il sito Web. In modo analogo allo schema di importazione, viene utilizzato solo il primo indirizzo di base specificato nell'associazione IIS. I dati WSDL e MEX contengono tutti gli indirizzi di base specificati nelle associazioni IIS.  
  
> [!WARNING]
>  Ciò significa che se un servizio dispone di due indirizzi di base, uno per utenti interni e uno per utenti esterni, entrambi vengono specificati nelle informazioni WSDL/MEX generate dal servizio.
