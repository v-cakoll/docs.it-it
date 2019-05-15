---
title: Utilità client WCF Data Services (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: bf812f45e4a4090becd8dfafe035d39d1d851860
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583631"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Utilità client WCF Data Services (DataSvcUtil.exe)

DataSvcUtil.exe è uno strumento da riga di comando fornito da WCF Data Services che utilizza un [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed e genera le classi del servizio dati client necessarie per accedere a un servizio dati da un'applicazione client .NET Framework. Questa utilità consente di generare classi di dati usando le origini di metadati seguenti:

- L'URI radice di un servizio dati. L'utilità richiede il documento dei metadati del servizio che descrive il modello di dati esposto dal servizio dati. Per altre informazioni, vedere [OData: Documento di metadati di servizio](https://go.microsoft.com/fwlink/?LinkId=186070).

- Un file di modello di dati (con estensione CSDL) definito tramite lo schema conceptual schema definition language (CSDL), come definito nel [ \[MC-CSDL\]: Formato di File di definizione dello Schema concettuale](https://go.microsoft.com/fwlink/?LinkID=159072) specifica.

- Un file con estensione edmx creato usando gli strumenti di Entity Data Model forniti con Entity Framework. Per altre informazioni, vedere la [ \[MC-EDMX\]: Entity Data Model per il formato dei pacchetti di servizi dati](https://go.microsoft.com/fwlink/?LinkID=178833) specifica.

Per altre informazioni, vedere [Procedura: Generare manualmente classi del servizio dati Client](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Lo strumento DataSvcUtil.exe viene installato nella directory di .NET Framework. In molti casi, trova in *C:\Windows\Microsoft.NET\Framework\v4.0*. Per i sistemi a 64 bit, questa si trova nella *C:\Windows\Microsoft.NET\Framework64\v4.0*. È anche possibile accedere allo strumento DataSvcUtil.exe dal prompt dei comandi per gli sviluppatori per Visual Studio.

## <a name="syntax"></a>Sintassi

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parametri

|Opzione|Descrizione|
|------------|-----------------|
|`/dataservicecollection`|Indica che verrà generato anche il codice necessario per l'associazione di oggetti a controlli.|
|`/help`<br /><br /> -oppure-<br /><br /> `/?`|Visualizza la sintassi e le opzioni di comando dello strumento.|
|`/in:` *\<file>*|Consente di specificare il file con estensione csdl o edmx oppure una directory in cui si trova il file.|
|`/language:`[VB&#124;CSharp]|Consente di specificare il linguaggio per i file di codice sorgente generati. Il linguaggio predefinito è C#.|
|`/nologo`|Consente di disattivare la visualizzazione del messaggio di copyright.|
|`/out:` *\<file>*|Consente di specificare il nome del file di codice sorgente contenente le classi del servizio dati client generate.|
|`/uri:` *\<string>*|L'URI del feed OData.|
|`/version:`[1.0&#124;2.0]|Specifica la versione accettata più recente di OData. La versione viene determinata in base il `DataServiceVersion` attributo dell'elemento DataService nei metadati del servizio dati restituiti. Per altre informazioni, vedere [controllo delle versioni del servizio dati](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). Quando si specifica la `/dataservicecollection` parametro, è necessario specificare anche `/version:2.0` per consentire il data binding.|

## <a name="see-also"></a>Vedere anche

- [Generazione della libreria client del servizio dati](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Procedura: Aggiungere un riferimento al servizio dati](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
