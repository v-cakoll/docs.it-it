---
title: Microservizi ospitati in Docker - C#
description: Informazioni su come creare servizi ASP.NET Core in esecuzione in contenitori Docker
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: b043b0109bcf8a67867d2c73a5ab22e43a4963cf
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208001"
---
# <a name="microservices-hosted-in-docker"></a>Microservizi ospitati in Docker

Questa esercitazione descrive nel dettaglio la procedura per creare e distribuire un microservizio ASP.NET Core in un contenitore Docker. Nel corso di questa esercitazione verranno illustrate le attività seguenti:

* Generazione di un'applicazione ASP.NET Core.
* Creazione di un ambiente di sviluppo Docker.
* Creazione di un'immagine Docker basata su un'immagine esistente
* Distribuzione del servizio in un ambiente Docker

Verranno inoltre illustrate alcune funzionalità del linguaggio C#:

* Conversione di oggetti C# in payload JSON
* Creazione di oggetti di trasferimento dati non modificabili.
* Elaborazione delle richieste HTTP in ingresso e generazione della risposta HTTP.
* Uso dei tipi valore nullable.

È possibile [visualizzare o scaricare l'app di esempio](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) per questo argomento. Per istruzioni sul download, vedere [Esempi ed esercitazioni](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

## <a name="why-docker"></a>Vantaggi offerti dall'uso di Docker

Docker semplifica la creazione di immagini delle macchine standard per ospitare i servizi in un data center o nel cloud pubblico. Docker consente di configurare l'immagine e di eseguirne la replica in base alle necessità per scalare l'installazione dell'applicazione.

Tutto il codice riportato in questa esercitazione può essere eseguito in qualsiasi ambiente .NET Core.
Le attività aggiuntive per un'installazione Docker funzioneranno per un'applicazione ASP.NET Core. 

## <a name="prerequisites"></a>Prerequisiti

È necessario configurare il computer per l'esecuzione di .NET Core. Le istruzioni di installazione sono disponibili nella pagina [.NET Core](https://www.microsoft.com/net/core).
Questa applicazione può essere eseguita in Windows, Linux, macOS o in un contenitore Docker.
È necessario installare l'editor di codice preferito. Nelle descrizioni seguenti viene usato [Visual Studio Code](https://code.visualstudio.com/), un editor open source multipiattaforma, ma è possibile usare gli strumenti con cui si ha maggiore familiarità.

È inoltre necessario installare il motore di Docker. Per le istruzioni di installazione relative alla piattaforma in uso, vedere la pagina [Docker Installation](http://www.docker.com/products/docker) (Installazione di Docker).
È possibile installare Docker in diverse distribuzioni di Linux, macOS o Windows. La pagina citata sopra contiene sezioni per ciascuna delle installazioni disponibili.

## <a name="create-the-application"></a>Creare l'applicazione

Dopo avere installato tutti gli strumenti, creare una nuova applicazione ASP.NET Core. A tale scopo, creare una nuova directory denominata "WeatherMicroservice" e dalla shell preferita eseguire il comando seguente in tale directory:

```console
dotnet new web
```

Il comando `dotnet` esegue gli strumenti necessari per lo sviluppo di .NET. Ogni verbo esegue un comando diverso.

Il comando `dotnet new` viene usato per creare progetti .NET Core.

Per questo microservizio si vuole creare l'applicazione Web più semplice e leggera possibile. Si userà quindi il modello "Progetto ASP.NET Core vuoto" specificandone il nome breve, `web`.

Il modello crea automaticamente quattro file:

* Un file Startup.cs, contenente la base dell'applicazione.
* Un file Program.cs, contenente il punto di ingresso dell'applicazione.
* Un file WeatherMicroservice.csproj, ovvero il file di compilazione dell'applicazione.
* Un file Properties/launchSettings.json. contenente le impostazioni di debug degli IDE.

È ora possibile eseguire l'applicazione generata dal modello:

```console
dotnet run
```

Questo comando prima ripristina le dipendenze necessarie per compilare l'applicazione e quindi compila l'applicazione.

La configurazione predefinita è in ascolto su `http://localhost:5000`. È possibile aprire un browser e passare a tale pagina, dove viene visualizzato un messaggio "Hello World!" .

Al termine, è possibile arrestare l'applicazione premendo <kbd>Ctrl</kbd>+<kbd>C</kbd>.

### <a name="anatomy-of-an-aspnet-core-application"></a>Composizione di un'applicazione ASP.NET Core

Dopo aver compilato l'applicazione, è ora opportuno analizzare il modo in cui questa funzionalità viene implementata. A questo punto risultano particolarmente interessanti due dei file generati: WeatherMicroservice.json e Startup.cs. 

Il file con estensione csproj contiene informazioni sul progetto.
I due nodi più interessanti sono `<TargetFramework>` e `<PackageReference>`.

Il nodo `<TargetFramework>` specifica la versione di .NET con cui questa applicazione verrà eseguita.

Ogni nodo `<PackageReference>` viene usato per specificare un pacchetto necessario per questa applicazione.

L'applicazione viene implementata nel file Startup.cs, contenente la classe startup.

I due metodi vengono chiamati dall'infrastruttura ASP.NET Core per configurare ed eseguire l'applicazione. Il metodo `ConfigureServices` descrive i servizi necessari per l'applicazione. Poiché si sta creando un microservizio semplificato, non è necessario configurare alcuna dipendenza. Il metodo `Configure` consente di configurare i gestori per le richieste HTTP in ingresso. Il modello genera un semplice gestore che risponde a qualsiasi richiesta con il testo "Hello World!".

## <a name="build-a-microservice"></a>Creare un microservizio

Il servizio che si intende creare distribuirà report meteo da qualsiasi località. In un ambiente di produzione, per recuperare i dati meteo sarebbe necessario chiamare un qualche servizio. Ai fini di questo esempio, verrà generata una previsione meteo casuale. 

Per implementare il servizio meteo casuale, è necessario eseguire diverse attività:

* Analizzare la richiesta in ingresso per leggere la latitudine e la longitudine.
* Generare alcuni dati di previsione casuali.
* Convertire i dati di previsione casuali da oggetti C# in pacchetti JSON.
* Impostare l'intestazione della risposta per indicare che il servizio reinvia JSON.
* Scrivere la risposta.

Ciascuno di questi passaggi è descritto nelle sezioni seguenti.

### <a name="parsing-the-query-string"></a>Analisi della stringa di query

Per iniziare, viene eseguita l'analisi della stringa di query. Nella stringa di query il servizio accetterà argomenti 'lat' e 'long' nel formato seguente:

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

Tutte le modifiche che è necessario apportare sono presenti nell'espressione lambda definita come argomento per `app.Run` nella classe startup.

L'argomento presente nell'espressione lambda è l'`HttpContext` della richiesta. Una delle sue proprietà è l'oggetto `Request`. L'oggetto `Request` ha una proprietà `Query` contenente un dizionario di tutti i valori presenti nella stringa di query per la richiesta. La prima operazione consiste nell'individuare i valori relativi alla latitudine e alla longitudine:

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

I valori del dizionario `Query` sono di tipo `StringValue`. Questo tipo può contenere una raccolta di stringhe. Ai fini di questo servizio meteo, ogni valore è una singola stringa. Per questo motivo nel codice sopra riportato è presente una chiamata a `FirstOrDefault()`. 

Come passaggio successivo, è necessario convertire le stringhe in valori double. Per convertire una stringa in un valore double verrà usato il metodo `double.TryParse()`:

```csharp
bool TryParse(string s, out double result);
```

Questo metodo utilizza parametri C# per indicare se la stringa di input può essere convertita in un valore double. Se la stringa costituisce una rappresentazione valida per un valore double, il metodo restituisce true e l'argomento `result` contiene il valore. Se la stringa non rappresenta un valore double valido, il metodo restituisce false.

È possibile adattare tale API mediante l'uso di un *metodo di estensione* che restituisce un *valore double nullable*. Un *tipo valore nullable* rappresenta alcuni tipi valore e può includere anche un valore mancante o null. Per rappresentare un tipo nullable, aggiungere il carattere `?` alla dichiarazione del tipo. 

I metodi di estensione sono definiti come metodi statici. Se tuttavia si aggiunge il modificatore `this` al primo parametro di tali metodi, è possibile chiamarli come se fossero membri della classe. I metodi di estensione possono essere definiti soltanto in classi statiche. Di seguito è riportata la definizione della classe contenente il metodo di estensione per l'analisi:

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

Prima di chiamare il metodo di estensione, modificare le impostazioni cultura correnti sulle impostazioni cultura inglese non dipendenti da paese/area geografica:

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

Ciò garantisce che l'applicazione analizzi i numeri allo stesso modo in qualsiasi server, indipendentemente dalle impostazioni cultura predefinite.

È ora possibile usare il metodo di estensione per convertire gli argomenti della stringa di query nel tipo double:

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

Per testare facilmente il codice di analisi, aggiornare la risposta in modo che includa i valori degli argomenti seguenti:

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

A questo punto, è possibile eseguire l'applicazione Web e verificare se il codice di analisi funziona correttamente. Aggiungere valori alla richiesta Web in un browser. Verranno visualizzati i risultati aggiornati.

### <a name="build-a-random-weather-forecast"></a>Creare una previsione meteo casuale

L'attività successiva consiste nella creazione di una previsione meteo casuale. Come prima operazione, creare un contenitore dati in cui siano presenti i valori necessari per una previsione meteo:

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

Come passaggio successivo, aggiungere un costruttore che imposti tali valori in modo casuale. Il costruttore usa i valori relativi a latitudine e longitudine per inizializzare il generatore di numeri `Random`. Questo significa che la previsione per la stessa località è la stessa. Se si modificano gli argomenti relativi alla latitudine e alla longitudine, si otterrà una previsione diversa, poiché si parte da un altro valore di inizializzazione.

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

Nel metodo di risposta è ora possibile generare una previsione a 5 giorni:

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a>Generare la risposta JSON

L'attività finale del codice sul server consiste nel convertire l'elenco `WeatherReport` in un documento JSON e nel rinviarlo al client. Come prima operazione, creare il documento JSON. All'elenco delle dipendenze verrà aggiunto il serializzatore JSON Newtonsoft. A tale scopo, è possibile usare il comando `dotnet` seguente:

```console
dotnet add package Newtonsoft.Json
```

È quindi possibile usare la classe `JsonConvert` per scrivere l'oggetto in una stringa:

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

Il codice sopra riportato converte l'oggetto forecast (un elenco di oggetti `WeatherForecast`) in un documento JSON. Dopo aver costruito il documento di risposta, impostare il tipo di contenuto su `application/json` e scrivere la stringa.

L'applicazione viene eseguita e restituisce previsioni casuali.

## <a name="build-a-docker-image"></a>Creare un'immagine Docker

L'attività finale consiste nell'esecuzione dell'applicazione in Docker. Verrà creato un contenitore Docker per eseguire un'immagine Docker che rappresenta l'applicazione.

Un'***immagine Docker*** è un file che definisce l'ambiente per l'esecuzione dell'applicazione.

Un ***contenitore Docker*** rappresenta un'istanza in esecuzione di un'immagine Docker.

Per analogia, è possibile assimilare l'*immagine Docker* a una *classe* e il *contenitore Docker* a un oggetto o a un'istanza di tale classe.  

A questo scopo, verrà usato il Dockerfile seguente:

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

Di seguito viene descritto il contenuto di tale file.

La prima riga specifica l'immagine di origine usata per compilare l'applicazione:

```
FROM microsoft/dotnet:2.1-sdk AS build
```

Docker consente di configurare un'immagine del computer basata su un modello di origine. Questo significa che, per iniziare, non è necessario specificare tutti i parametri del computer, ma soltanto le eventuali modifiche. Tali modifiche dovranno includere l'applicazione.

In questo esempio verrà usata la versione `2.1-sdk` dell'immagine `dotnet`. Questo è il modo più semplice per creare un ambiente Docker funzionante. Questa immagine include il runtime di .NET Core e .NET Core SDK.
Ciò rende più semplice iniziare e compilare, ma crea un'immagine più grande. Questa immagine verrà pertanto usata per la compilazione dell'applicazione, mentre per l'esecuzione verrà usata un'immagine diversa.

Le prossime righe consentono di installare e compilare l'applicazione:

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

Il codice sopra riportato copia il file di progetto dalla directory corrente alla macchina virtuale Docker e ripristina tutti i pacchetti. Se si usa l'interfaccia della riga di comando, l'immagine Docker deve includere .NET Core SDK. Dopo ciò, viene copiata la parte rimanente dell'applicazione e il comando `dotnet
publish` compila l'applicazione e ne crea il pacchetto.

Viene infine creata una seconda immagine Docker che esegue l'applicazione:

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

Questa immagine usa la versione `2.1-aspnetcore-runtime` dell'immagine `dotnet`, che contiene tutto quando necessario per eseguire applicazioni ASP.NET Core, ma non include .NET Core SDK. Ciò significa che questa immagine non può essere usata per compilare applicazioni .NET Core, ma anche che l'immagine finale risultante è più piccola.

Per ottenere questo risultato, copiare l'applicazione compilata dalla prima immagine alla seconda.

Il comando `ENTRYPOINT` informa Docker del comando che avvia il servizio.

## <a name="building-and-running-the-image-in-a-container"></a>Compilazione ed esecuzione dell'immagine in un contenitore

In questa sezione si eseguirà la compilazione di un'immagine e l'esecuzione di un servizio all'interno di un contenitore Docker. Non si vuole che tutti i file della directory locale vengano copiati nell'immagine. L'applicazione verrà invece compilata nel contenitore. Verrà creato un file `.dockerignore` per specificare le directory non copiate nell'immagine. Si vuole che non venga copiata alcuna risorsa di compilazione. Specificare le directory di compilazione e pubblicazione nel file `.dockerignore`:

```
bin/*
obj/*
out/*
```

L'immagine viene compilata usando il comando `docker build`. Eseguire il comando seguente dalla directory contenente il codice.

```console
docker build -t weather-microservice .
```

Questo comando compila l'immagine del contenitore sulla base di tutte le informazioni presenti nel file Docker. L'argomento `-t` specifica un tag, o un nome, per questa immagine del contenitore. Nella riga di comando precedente il tag usato per il contenitore Docker è `weather-microservice`. Dopo l'esecuzione di questo comando, è disponibile un contenitore pronto per l'esecuzione del nuovo servizio. 

Eseguire il comando seguente per avviare il contenitore e il servizio:

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

L'opzione `-d` consente di eseguire il contenitore scollegato dal terminale corrente. Questo significa che nel terminale non verrà visualizzato l'output del comando. L'opzione `-p` indica il mapping delle porte tra il servizio e l'host. In base al codice sopra riportato, qualsiasi richiesta in ingresso sulla porta 80 verrà inoltrata alla porta 80 del contenitore. La porta 80 corrisponde alla porta su cui il servizio è in ascolto, ovvero alla porta predefinita per le applicazioni di produzione. L'argomento `--name` indica il nome del contenitore in esecuzione. È un nome appropriato, che è possibile specificare per usare il contenitore.

Per vedere se l'immagine è in esecuzione, usare il comando seguente:

```console
docker ps
```

Se il contenitore è in esecuzione, viene visualizzata una riga in cui sono elencati i processi in esecuzione. Questa riga potrebbe essere l'unica.

Per testare il servizio, è possibile aprire un browser, passare a localhost e specificare valori per la latitudine e la longitudine:

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a>Collegarsi a un contenitore in esecuzione

Quando si esegue il servizio in una finestra di comando, è possibile osservare le informazioni di diagnostica stampate per ogni richiesta. Quando il contenitore è in esecuzione senza collegamento, tali informazioni non vengono visualizzate. Il comando attach di Docker consente di collegarsi a un contenitore in esecuzione in modo da visualizzare le informazioni di log.  Eseguire questo comando da una finestra di comando:

```console
docker attach --sig-proxy=false hello-docker
```

L'argomento `--sig-proxy=false` indica che i comandi <kbd>Ctrl</kbd>+<kbd>C</kbd> non vengono inviati al processo del contenitore, ma interrompono il comando `docker attach`. L'argomento finale è il nome assegnato al contenitore nel comando `docker run`. 

> [!NOTE]
> È anche possibile usare l'ID del contenitore assegnato da Docker per fare riferimento a qualsiasi altro contenitore. Se in `docker run` non è stato specificato un nome per il contenitore, è necessario usare l'ID del contenitore.

Aprire un browser e passare al servizio. Nelle finestre di comando verranno visualizzati messaggi di diagnostica provenienti dal contenitore collegato in esecuzione.

Premere <kbd>Ctrl</kbd>+<kbd>C</kbd> per arrestare il processo del comando attach.

Quando si è finito di usare il contenitore, è possibile arrestarlo:

```console
docker stop hello-docker
```

Il contenitore e l'immagine sono ancora disponibili per il riavvio.  Per rimuovere il contenitore dal computer, usare il comando seguente:

```console
docker rm hello-docker
```

Per rimuovere dal computer le immagini non utilizzate, usare il comando seguente:

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a>Conclusione 

In questa esercitazione è stato creato un microservizio ASP.NET Core e sono state aggiunte alcune semplici funzionalità.

È stata compilata un'immagine del contenitore Docker per il servizio e tale contenitore è stato eseguito nel computer in uso. È stata collegata una finestra del terminale al servizio e sono stati visualizzati i messaggi di diagnostica provenienti dal servizio stesso.

Nel corso dell'esercitazione è stato possibile osservare diverse funzionalità del linguaggio C# in azione.
