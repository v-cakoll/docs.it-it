---
title: Supporto delle associazioni a più siti IIS
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: e364be55687323d3059c4a7e084818e3f7d54d5f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743438"
---
# <a name="supporting-multiple-iis-site-bindings"></a>Supporto delle associazioni a più siti IIS
Quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Services (IIS) 7,0, potrebbe essere necessario fornire più indirizzi di base che utilizzano lo stesso protocollo sullo stesso sito. In questo modo lo stesso servizio può rispondere a diversi URI. Questa opzione è utile quando si desidera ospitare un servizio in ascolto su `http://www.contoso.com` e `http://contoso.com`. È inoltre utile per creare un servizio che dispone di un indirizzo di base per gli utenti interni e un indirizzo di base separato per gli utenti esterni. Ad esempio: `http://internal.contoso.com` e `http://www.contoso.com`.  
  
> [!NOTE]
> Questa funzionalità è disponibile solo utilizzando il protocollo HTTP.  
  
## <a name="multiple-base-addresses"></a>Più indirizzi di base  
 Questa funzionalità è disponibile solo per i servizi WCF ospitati in IIS. Per impostazione predefinita questa funzionalità non è abilitata. Per abilitarla, è necessario aggiungere l'attributo `multipleSiteBindingsEnabled` all'elemento <`serviceHostingEnvironment`> nel file Web. config e impostarlo su `true`, come illustrato nell'esempio seguente.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Quando si ospita un servizio WCF in IIS, IIS crea un indirizzo di base per l'utente in base all'URI della directory virtuale che contiene l'applicazione. È possibile aggiungere ulteriori indirizzi di base che utilizzano lo stesso protocollo mediante Gestione Internet Information Services per aggiungere una o più associazioni al sito Web. Per ogni associazione specificare un protocollo (HTTP o HTTPS), un indirizzo IP, una porta e un nome host. Per ulteriori informazioni sull'utilizzo di Internet Information Services Manager, vedere [Gestione IIS (IIS 7)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753842(v=ws.10)). Per ulteriori informazioni sull'aggiunta di binding a un sito, vedere [la pagina relativa alla creazione di un sito Web (IIS 7)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772350(v=ws.10)) .  
  
 La specifica di più indirizzi di base per lo stesso sito influiscono sul contenuto della pagina della Guida WCF, sull'importazione dello schema e sulle informazioni WSDL/MEX generate dal servizio. Nella pagina della Guida di WCF viene visualizzata la riga di comando da utilizzare per generare un client WCF in grado di comunicare con il servizio. La riga di comando contiene solo il primo indirizzo specificato nell'associazione IIS per il sito Web. In modo analogo allo schema di importazione, viene utilizzato solo il primo indirizzo di base specificato nell'associazione IIS. I dati WSDL e MEX contengono tutti gli indirizzi di base specificati nelle associazioni IIS.  
  
> [!WARNING]
> Ciò significa che se un servizio dispone di due indirizzi di base, uno per utenti interni e uno per utenti esterni, entrambi vengono specificati nelle informazioni WSDL/MEX generate dal servizio.
