---
title: API Web ASP.NET e WCF
description: È possibile sapere se WCF o il API Web ASP.NET è più adatto alle proprie esigenze confrontando le principali funzionalità di ciascuna tecnologia.
ms.date: 03/30/2017
ms.assetid: 08ceded3-fd9a-4467-9715-c4cbd9c7228e
ms.openlocfilehash: de8d1905866c860da96983c2f3d52599e3342403
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245963"
---
# <a name="wcf-and-aspnet-web-api"></a>API Web ASP.NET e WCF
WCF è il modello di programmazione unificato di Microsoft per la compilazione di applicazioni orientate ai servizi. Consente agli sviluppatori di compilare soluzioni transazionali protette e affidabili in grado di integrarsi a piattaforme diverse e interagire con investimenti esistenti. [API Web ASP.NET](https://www.asp.net/web-api) è un Framework che consente di creare facilmente servizi HTTP che raggiungono un'ampia gamma di client, inclusi browser e dispositivi mobili. API Web ASP.NET è la piattaforma ideale per compilare applicazioni RESTful in .NET Framework. In questo argomento vengono indicate alcune linee guida utili per decidere la tecnologia che soddisfa meglio le proprie esigenze.  
  
## <a name="choosing-which-technology-to-use"></a>Scelta della tecnologia da utilizzare  
 Nella tabella seguente vengono descritte le principali funzionalità di ogni tecnologia.  
  
|WCF|API Web ASP.NET|  
|---------|---------------------|  
|Abilita i servizi di compilazione che supportano più protocolli di trasporto (HTTP, TCP, UDP e trasporti personalizzati) e consentono il passaggio da un protocollo all'altro.|Solo HTTP. Modello di programmazione di prima classe per HTTP. Più adatto per l'accesso da vari browser, dispositivi mobili e così via.|  
|Abilita i servizi di compilazione che supportano più codifiche (testo, MTOM e binario) dello stesso tipo di messaggio e consente il passaggio da una codifica all'altra.|Abilita le API Web che supportano un'ampia varietà di tipi di contenuti multimediali, ad esempio XML, JSON e così via.|  
|Supporta i servizi di compilazione con gli standard WS-* come la messaggistica affidabile, le transazioni, la sicurezza dei messaggi.|Usa il protocollo e i formati di base, ad esempio HTTP, WebSocket, SSL, JSON e XML. Non è disponibile alcun supporto per i protocolli di livello superiore, ad esempio la messaggistica affidabile o le transazioni.|  
|Supporta i modelli di scambio dei messaggi richiesta-risposta, unidirezionale e duplex.|HTTP è richiesta/risposta, ma è possibile supportare modelli aggiuntivi tramite l'integrazione di [SignalR](https://github.com/SignalR/SignalR) e WebSocket.|  
|I servizi SOAP WCF possono essere descritti in WSDL per permettere agli strumenti automatizzati di generare i proxy client anche per i servizi con schemi complessi.|Esistono diversi modi per descrivere un'API Web, dalla pagina della Guida HTML generata automaticamente che descrive frammenti ai metadati strutturati per API integrate OData.|  
|Viene fornito con la .NET Framework.|Viene fornito con .NET Framework ma è open source ed è anche disponibile fuori banda come download indipendente.|  
  
 Utilizzare WCF per creare servizi Web affidabili e sicuri accessibili su diversi trasporti. Utilizzare l'API Web ASP.NET per creare i servizi basati su HTTP accessibili da un'ampia varietà di client. Utilizzare l'API Web ASP.NET se si stanno creando e progettando nuovi servizi in stile REST. Sebbene WCF fornisca supporto per scrivere servizi in stile REST, il supporto per REST nell'API Web ASP.NET è più completo e tutti i futuri miglioramenti della funzionalità REST verranno introdotti nell'API Web ASP.NET. Se si dispone di un servizio WCF e si desidera esporre endpoint REST aggiuntivi, utilizzare WCF e <xref:System.ServiceModel.WebHttpBinding>.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni su Windows Communication Foundation](whats-wcf.md)
- [Concetti fondamentali di Windows Communication Foundation](fundamental-concepts.md)
