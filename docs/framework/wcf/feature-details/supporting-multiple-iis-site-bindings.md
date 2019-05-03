---
title: Supporto delle associazioni a più siti IIS
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: 5a8b06d86b505452f9ded808f727343b1453e592
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696106"
---
# <a name="supporting-multiple-iis-site-bindings"></a>Supporto delle associazioni a più siti IIS
Quando si ospita un servizio Windows Communication Foundation (WCF) in Internet Information Services (IIS) 7.0, è possibile specificare più indirizzi di base che utilizzano lo stesso protocollo nello stesso sito. In questo modo lo stesso servizio può rispondere a diversi URI. Ciò è utile quando si desidera ospitare un servizio che è in ascolto sulla `http://www.contoso.com` e `http://contoso.com`. È inoltre utile per creare un servizio che dispone di un indirizzo di base per gli utenti interni e un indirizzo di base separato per gli utenti esterni. Ad esempio: `http://internal.contoso.com` e `http://www.contoso.com`.  
  
> [!NOTE]
>  Questa funzionalità è disponibile solo utilizzando il protocollo HTTP.  
  
## <a name="multiple-base-addresses"></a>Più indirizzi di base  
 Questa funzionalità è disponibile solo per i servizi WCF ospitati in IIS. Per impostazione predefinita questa funzionalità non è abilitata. Per attivarla è necessario aggiungere il `multipleSiteBindingsEnabled` dell'attributo di <`serviceHostingEnvironment`> elemento nel file Web. config di file e impostarlo su `true`, come illustrato nell'esempio seguente.  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 Quando si ospita un servizio WCF in IIS, IIS crea un indirizzo di base in base all'URI per la directory virtuale che contiene l'applicazione. È possibile aggiungere ulteriori indirizzi di base che utilizzano lo stesso protocollo mediante Gestione Internet Information Services per aggiungere una o più associazioni al sito Web. Per ogni associazione specificare un protocollo (HTTP o HTTPS), un indirizzo IP, una porta e un nome host. Per altre informazioni sull'uso di Gestione Internet Information Services, vedere [Gestione IIS (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164057). Per altre informazioni sull'aggiunta di associazioni a un sito, vedere [creare un sito Web (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164060)  
  
 Specificare più indirizzi di base per lo stesso sito influisce sul contenuto della pagina della Guida WCF, l'importazione dello schema e le informazioni WSDL/MEX generate dal servizio. La pagina della Guida WCF consente di visualizzare la riga di comando da utilizzare per generare un client WCF in grado di comunicare con il servizio. La riga di comando contiene solo il primo indirizzo specificato nell'associazione IIS per il sito Web. In modo analogo allo schema di importazione, viene utilizzato solo il primo indirizzo di base specificato nell'associazione IIS. I dati WSDL e MEX contengono tutti gli indirizzi di base specificati nelle associazioni IIS.  
  
> [!WARNING]
>  Ciò significa che se un servizio dispone di due indirizzi di base, uno per utenti interni e uno per utenti esterni, entrambi vengono specificati nelle informazioni WSDL/MEX generate dal servizio.
