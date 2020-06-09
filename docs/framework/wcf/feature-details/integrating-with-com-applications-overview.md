---
title: Panoramica sull'integrazione con applicazioni COM
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], integration overview
ms.assetid: 02c5697f-6e2e-47d6-b715-f3a28aebfbd5
ms.openlocfilehash: c283e7cbc4cb4b8bc37dd1313480410df93a93bf
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596825"
---
# <a name="integrating-with-com-applications-overview"></a>Panoramica sull'integrazione con applicazioni COM

Windows Communication Foundation (WCF) fornisce allo sviluppatore del codice gestito un ambiente completo per la creazione di applicazioni connesse. Tuttavia, se si ha un investimento sostanziale nel codice basato su COM non gestito e non si vuole eseguire la migrazione, è comunque possibile integrare i servizi Web WCF direttamente nel codice esistente usando il moniker del servizio WCF. Il moniker servizio può essere usato da un'ampia gamma di ambienti di sviluppo basati su COM, ad esempio Office VBA, Visual Basic 6.0 o Visual C++ 6.0.

> [!NOTE]
> Il moniker del servizio utilizza un canale di comunicazione WCF per tutte le comunicazioni. I meccanismi di sicurezza e identità per tale canale differiscono da quelli utilizzati nei proxy COM e DCOM standard. Inoltre, poiché il moniker del servizio utilizza un canale di comunicazione WCF, il periodo di timeout predefinito è di un minuto per tutte le chiamate.

Il moniker del servizio viene utilizzato con la `GetObject` funzione per fornire allo sviluppatore non gestito un approccio specifico com e fortemente tipizzato per la chiamata ai servizi Web WCF. Questa operazione richiede una definizione locale visibile a COM del contratto del servizio Web WCF e l'associazione da utilizzare. Analogamente ad altri client WCF, il moniker del servizio deve creare un canale tipizzato per il servizio, anche se questa costruzione del canale si verifica in modo trasparente al programmatore COM sulla prima chiamata al metodo.

In comune con altri client WCF, quando si usa il moniker, le applicazioni specificano l'indirizzo, l'associazione e il contratto per comunicare con un servizio. Il contratto può essere specificato in uno dei modi seguenti:

- Contratto tipizzato: il contratto viene registrato come tipo visibile a COM sul computer client.

- Contratto WSDL: il contratto viene fornito sotto forma di documento WSDL.

- Contratto MEX: il contratto viene recuperato in fase di esecuzione da un endpoint MEX (Metadata Exchange).

## <a name="parameters-supported-by-the-service-moniker"></a>Parametri supportati dal moniker del servizio

Nella tabella seguente vengono illustrati i parametri supportati dal moniker del servizio.

|Parametro|Descrizione|
|---------------|-----------------|
|`address`|Percorso URL del servizio.|
|`binding`|Nome della sezione dell'associazione ottenuto dalla configurazione dell'applicazione.|
|`bindingConfiguration`|Istanza dell'associazione non anonima ottenuta dall'interno la sezione dell'associazione non anonima.|
|`contract`|Identificatore di interfaccia (IID) che rappresenta il contratto del servizio o il nome del contratto (ottenuto da MEX).|
|`wsdl`|Documento WSDL che fornisce un tipo alternativo di definizione del contratto.|
|`spnIdentity`|Identità del nome principale del server (SPN) da utilizzare per comunicare con il servizio.|
|`upnIdentity`|Identità del nome di entità utente (UPN) da utilizzare per comunicare con il servizio.|
|`dnsIdentity`|Identità DNS da utilizzare per comunicare con il servizio.|
|`mexAddress`|Percorso URL dell'endpoint MEX (Metadata Exchange) del servizio.|
|`mexBinding`|Nome della sezione dell'associazione ottenuto dalla configurazione dell'applicazione da connettere con l'endpoint MEX.|
|`mexBindingConfiguration`|Istanza dell'associazione non anonima ottenuta dall'interno della sezione dell'associazione non anonima da connettere con l'endpoint MEX.|
|`bindingNamespace`|Spazio dei nomi del nome della sezione dell'associazione ottenuto dal MEX recuperato.|
|`contractNamespace`|Spazio dei nomi del contratto ottenuto dal MEX recuperato.|
|`mexSpnIdentity`|Identità del nome principale del server (SPN) da utilizzare per comunicare con l'endpoint MEX.|
|`mexUpnIdentity`|Identità del nome dell'entità utente (UPN) da utilizzare per comunicare con l'endpoint MEX.|
|`mexDnsIdentity`|Identità DNS da utilizzare per comunicare con l'endpoint MEX.|
|`serializer`|Consente di specificare l'utilizzo del serializzatore "xml" o "datacontract."|

> [!NOTE]
> Anche quando viene usato con client completamente basati su COM, il moniker del servizio richiede che WCF e il .NET Framework di supporto 2,0 siano installati nel computer client. È inoltre fondamentale che le applicazioni client che utilizzano il moniker del servizio carichino la versione appropriata del runtime .NET Framework. Quando il moniker viene utilizzato all'interno di applicazioni Office, può essere necessario un file di configurazione per garantire il caricamento della versione corretta del framework. Ad esempio, con Excel, è consigliabile inserire il testo seguente in un file denominato Excel.exe.config nella stessa directory del file Excel.exe:
>
> `<?xml version="1.0" encoding="utf-8"?>`
>
> `<configuration xmlns=` `http://schemas.microsoft.com/.NetConfiguration/v2.0` `>`
>
> `<startup>`
>
> `<requiredRuntime version="v2.0.50727" />`
>
> `</startup>`
>
> `</configuration>`

## <a name="see-also"></a>Vedere anche

- [Procedura: registrare e configurare un moniker servizio](how-to-register-and-configure-a-service-moniker.md)
