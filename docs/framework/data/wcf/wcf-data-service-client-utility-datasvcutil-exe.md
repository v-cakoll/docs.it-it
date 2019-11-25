---
title: Utilità client WCF Data Services (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: de260e1a6b58fdbac1a2f0f40c7ec2e50b13644e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975090"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Utilità client WCF Data Services (DataSvcUtil.exe)

DataSvcUtil. exe è uno strumento da riga di comando fornito da WCF Data Services che utilizza un feed di Open Data Protocol (OData) e genera le classi del servizio dati client necessarie per accedere a un servizio dati da un'applicazione client .NET Framework. Questa utilità consente di generare classi di dati usando le origini di metadati seguenti:

- L'URI radice di un servizio dati. L'utilità richiede il documento dei metadati del servizio che descrive il modello di dati esposto dal servizio dati. Per ulteriori informazioni, vedere [OData: documento dei metadati del servizio](https://go.microsoft.com/fwlink/?LinkId=186070).

- Un file del modello di dati (con estensione CSDL) definito utilizzando il Conceptual Schema Definition Language (CSDL), come definito nella specifica del [formato del file di definizione dello schema concettuale di\[MC-csdl\]:](https://go.microsoft.com/fwlink/?LinkID=159072) .

- Un file con estensione edmx creato usando gli strumenti di Entity Data Model forniti con Entity Framework. Per ulteriori informazioni, vedere la [\[MC-EDMX\]: Entity Data Model per la specifica del formato di pacchetti di servizi dati](https://go.microsoft.com/fwlink/?LinkID=178833) .

Per altre informazioni, vedere [procedura: generare manualmente classi del servizio dati client](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Lo strumento DataSvcUtil. exe viene installato nella directory .NET Framework. In molti casi, si trova in *C:\Windows\Microsoft.NET\Framework\v4.0*. Per i sistemi a 64 bit, si trova in *C:\Windows\Microsoft.NET\Framework64\v4.0*. È anche possibile accedere allo strumento DataSvcUtil. exe da Prompt dei comandi per gli sviluppatori per Visual Studio.

## <a name="syntax"></a>Sintassi

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parametri

|Opzione|Descrizione|
|------------|-----------------|
|`/dataservicecollection`|Indica che verrà generato anche il codice necessario per l'associazione di oggetti a controlli.|
|`/help`<br /><br /> oppure<br /><br /> `/?`|Visualizza la sintassi e le opzioni di comando dello strumento.|
|`/in:` *\<file >*|Consente di specificare il file con estensione csdl o edmx oppure una directory in cui si trova il file.|
|`/language:`[VB&#124;CSharp]|Consente di specificare il linguaggio per i file di codice sorgente generati. Il linguaggio predefinito è C#.|
|`/nologo`|Consente di disattivare la visualizzazione del messaggio di copyright.|
|`/out:` *\<file >*|Consente di specificare il nome del file di codice sorgente contenente le classi del servizio dati client generate.|
|`/uri:` *stringa\<*|URI del feed OData.|
|`/version:`[1,0&#124;2,0]|Specifica la versione più recente accettata di OData. La versione viene determinata in base all'attributo `DataServiceVersion` dell'elemento DataService nei metadati del servizio dati restituiti. Per ulteriori informazioni, vedere [controllo delle versioni del servizio dati](data-service-versioning-wcf-data-services.md). Quando si specifica il parametro `/dataservicecollection`, è necessario specificare anche `/version:2.0` per abilitare data binding.|

## <a name="see-also"></a>Vedere anche

- [Generazione della libreria client del servizio dati](generating-the-data-service-client-library-wcf-data-services.md)
- [Procedura: aggiungere un riferimento al servizio dati](how-to-add-a-data-service-reference-wcf-data-services.md)
