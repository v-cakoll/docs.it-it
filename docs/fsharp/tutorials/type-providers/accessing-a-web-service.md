---
title: 'Procedura dettagliata: accesso a un servizio Web tramite provider di tipi (F #)'
description: 'Informazioni su come utilizzare il provider di tipi di Web Services Description Language (WSDL) disponibile in F # 3.0 per accedere a un servizio WSDL.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a>Procedura dettagliata: Accesso a un servizio Web tramite provider di tipi

> [!NOTE]
Questa guida è stata scritta per F # 3.0 e verrà aggiornata.  Per provider di tipo multipiattaforma aggiornati, vedere [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
I collegamenti di riferimento API richiederà a MSDN.  Il riferimento all'API in Microsoft Docs (docs.microsoft.com) non è completo.

Questa procedura dettagliata viene illustrato come utilizzare il provider di tipi di servizi Web (WSDL, Web Services Description Language) che è disponibile in F # 3.0 per accedere a un servizio WSDL. In altri linguaggi .NET, generare il codice per accedere al servizio web da chiamare svcutil.exe o aggiungendo un riferimento web in, ad esempio, un progetto c# per ottenere Visual Studio chiamare svcutil.exe. In F # è l'opzione aggiuntiva dell'utilizzo del provider di tipo WSDL, pertanto, non appena si scrive il codice che crea il tipo WsdlService, i tipi generati e diventano disponibili. Questo processo si basa sul servizio sia disponibile quando si scrive il codice.

In questa procedura dettagliata vengono illustrate le attività seguenti. È necessario completare le in quest'ordine perché la procedura abbia esito positivo:


- Creazione del progetto
<br />

- Configurazione del provider di tipi
<br />

- Chiamare il servizio web e l'elaborazione dei risultati
<br />


## <a name="creating-the-project"></a>Creazione del progetto
Nel passaggio, si crea un progetto e aggiungere i riferimenti appropriati per l'utilizzo di un provider di tipi WSDL.


#### <a name="to-create-and-set-up-an-f-project"></a>Per creare e configurare un progetto F#

1. Aprire un nuovo progetto applicazione Console c#.
<br />

2. In **Esplora**, aprire il menu di scelta rapida per il progetto **riferimento** nodo, quindi scegliere **Aggiungi riferimento**.
<br />

3. Nel **assembly** area scegliere **Framework**, quindi nell'elenco di assembly disponibili, scegliere **Serialization** e  **System. ServiceModel**.
<br />

4. Nel **assembly** area scegliere **estensioni**.
<br />

5. Nell'elenco di assembly disponibili, scegliere **Typeproviders**, quindi scegliere il **OK** pulsante per aggiungere riferimenti a questi assembly.
<br />

## <a name="configuring-the-type-provider"></a>Configurazione del provider di tipi
In questo passaggio, utilizzare il provider di tipi WSDL per generare i tipi per il servizio web TerraServer.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>Per configurare il provider di tipi e generare i tipi

1. Aggiungere la seguente riga di codice per aprire lo spazio dei nomi del provider di tipo.
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. Aggiungere la seguente riga di codice di richiamare il provider di tipi con un servizio web. In questo esempio, utilizzare il servizio web TerraServer.
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  Se l'URI del servizio è errata o se il servizio è inattivo o non sta eseguendo, viene visualizzata una sottolineatura ondulata rossa sotto questa riga di codice. Se si sceglie il codice, un messaggio di errore viene descritto il problema. È possibile trovare le stesse informazioni nel **elenco errori** finestra o nel **finestra di Output** al termine della compilazione.
<br />  Esistono due modi per specificare le impostazioni di configurazione per una connessione di WSDL, utilizzando il file app. config per il progetto oppure utilizzando i parametri di tipo statico nella dichiarazione del tipo di provider. È possibile utilizzare svcutil.exe per generare gli elementi di file di configurazione appropriato. Per ulteriori informazioni sull'utilizzo di svcutil.exe per generare informazioni di configurazione per un servizio web, vedere [strumento ServiceModel Metadata Utility &#40; Svcutil.exe &#41; ](https://msdn.microsoft.com/library/aa347733.aspx). Per una descrizione completa dei parametri di tipo statico per il provider di tipi WSDL, vedere [Provider di tipi WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a>Chiamare il servizio web e l'elaborazione dei risultati
Ciascun servizio web dispone di un proprio set di tipi che sono usati come parametri per le chiamate di metodo. In questo passaggio, questi parametri per la preparazione, chiama un metodo web e di elaborare le informazioni che viene restituito.


#### <a name="to-call-the-web-service-and-process-the-results"></a>Per chiamare il servizio web e per elaborare i risultati

1. Il servizio web potrebbe essere previsto un timeout o smettere di funzionare, pertanto è consigliabile includere una chiamata al servizio web in un blocco di gestione delle eccezioni. Scrivere il codice seguente per tentare di ottenere dati dal servizio web.
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

Si noti che è creare i tipi di dati che sono necessari per il servizio web, ad esempio **sul posto** e **percorso**, come i tipi annidati di WsdlService digitare **serie**.
<br />


## <a name="see-also"></a>Vedere anche
[Provider di tipi WsdlService](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[Provider di tipi](index.md)
