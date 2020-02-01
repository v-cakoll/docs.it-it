---
title: Creare una nuova ASP.NET Core progetto gRPC-gRPC per sviluppatori WCF
description: Informazioni su come creare un progetto gRPC con Visual Studio o la riga di comando.
ms.date: 09/02/2019
ms.openlocfilehash: fbcc598cf503a5baeca941803ff8fa0d5fc99671
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "76919405"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a>Creare un nuovo progetto ASP.NET Core gRPC

Il .NET Core SDK è dotato di uno strumento CLI potente, `dotnet`, che consente di creare e gestire progetti e soluzioni dalla riga di comando. L'SDK è strettamente integrato con Visual Studio, quindi tutti gli elementi sono disponibili anche tramite l'interfaccia utente grafica nota. In questo capitolo vengono illustrate entrambe le modalità di creazione di un nuovo progetto di ASP.NET Core gRPC.

## <a name="create-the-project-by-using-visual-studio"></a>Creare il progetto usando Visual Studio

> [!IMPORTANT]
> Per sviluppare qualsiasi app ASP.NET Core 3,0, è necessario Visual Studio 2019 versione 16,3 o successiva, con il carico di lavoro di **sviluppo ASP.NET e Web** installato.

Creare una soluzione vuota denominata **TraderSys** dal modello di *soluzione vuota* . Aggiungere una cartella della soluzione denominata `src`. Quindi, fare clic con il pulsante destro del mouse sulla cartella e scegliere **aggiungi** > **nuovo progetto**. Immettere `grpc` nella casella di ricerca del modello. verrà visualizzato un modello di progetto denominato `gRPC Service`.

![Screenshot della finestra di dialogo Aggiungi nuovo progetto](media/create-project/new-grpc-project.png)

Selezionare **Avanti** per passare alla finestra di dialogo **Configura nuovo progetto** . Denominare il progetto `TraderSys.Portfolios` e aggiungere una sottodirectory `src` al **percorso**.

![Screenshot della finestra di dialogo Configura nuovo progetto](media/create-project/configure-project.png)

Selezionare **Avanti** per passare alla finestra di dialogo **Crea un nuovo servizio gRPC** .

![Screenshot della finestra di dialogo Crea un nuovo servizio gRPC](media/create-project/create-new-grpc-service.png)

Al momento sono disponibili opzioni limitate per la creazione del servizio. Docker verrà introdotto in un secondo momento, quindi, per ora, lasciare l'opzione deselezionata. Basta selezionare **Crea**. Il primo progetto di ASP.NET Core 3,0 gRPC viene generato e aggiunto alla soluzione. Se non si vuole sapere come usare la `dotnet CLI`, passare alla sezione [pulire il codice di esempio](#clean-up-the-example-code) .

## <a name="create-the-project-by-using-the-net-core-cli"></a>Creare il progetto usando il interfaccia della riga di comando di .NET Core

In questa sezione viene illustrata la creazione di soluzioni e progetti dalla riga di comando.

Creare la soluzione come illustrato nel comando seguente. Il flag `-o` (o `--output`) specifica la directory di output, che viene creata nella directory corrente, se non esiste già. La soluzione ha lo stesso nome della directory: `TraderSys.sln`. È possibile specificare un nome diverso usando il flag `-n` (o `--name`).

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

ASP.NET Core 3,0 viene fornita con un modello CLI per i servizi gRPC. Creare il nuovo progetto usando questo modello, inserendolo in una sottodirectory `src` come è convenzionale per i progetti ASP.NET Core. Il progetto viene denominato dopo la directory (`TraderSys.Portfolios.csproj`), a meno che non si specifichi un nome diverso con il flag di `-n`.

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

Aggiungere infine il progetto alla soluzione usando il comando `dotnet sln`:

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> Poiché la directory specifica contiene solo un singolo file di `.csproj`, è possibile specificare solo la directory per salvare la digitazione.

È ora possibile aprire la soluzione in Visual Studio 2019, Visual Studio Code o qualsiasi altro editor preferito.

## <a name="clean-up-the-example-code"></a>Pulire il codice di esempio

A questo punto è stato creato un servizio di esempio usando il modello gRPC, che è stato esaminato in precedenza nel libro. Questo non è utile nel contesto di trading azionario, quindi verranno modificati gli elementi per il primo progetto.

### <a name="rename-and-edit-the-proto-file"></a>Rinominare e modificare il file proto

Procedere e rinominare il file di `Protos/greet.proto` in `Protos/portfolios.proto`e aprirlo nell'editor. Elimina tutti gli elementi dopo la riga di `package`. Modificare quindi i nomi di `option csharp_namespace`, `package` e `service` e rimuovere il servizio `SayHello` predefinito. Il codice ha ora un aspetto simile al seguente:

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> Il modello non aggiunge la parte dello spazio dei nomi `Protos` per impostazione predefinita, ma l'aggiunta rende più semplice la conservazione delle classi generate da gRPC e delle classi delimitate in modo chiaro nel codice.

Se si rinomina il file di `greet.proto` in un Integrated Development Environment (IDE) come Visual Studio, un riferimento a questo file viene aggiornato automaticamente nel file `.csproj`. Tuttavia, in un altro editor, ad esempio Visual Studio Code, questo riferimento non viene aggiornato automaticamente, quindi è necessario modificare il file di progetto manualmente.

Nelle destinazioni di compilazione di gRPC è presente un elemento `Protobuf` elemento che consente di specificare quali file di `.proto` devono essere compilati e quale forma di generazione del codice è necessaria (ovvero "Server" o "client").

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a>Rinominare la classe `GreeterService`

La classe `GreeterService` si trova nella cartella `Services` ed eredita da `Greeter.GreeterBase`. Rinominare il `PortfolioService`e impostare la classe di base su `Portfolios.PortfoliosBase`. Eliminare i metodi `override`.

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

Si è verificato un riferimento alla classe `GreeterService` nel metodo `Configure` della classe `Startup`. Se è stato usato il refactoring per rinominare la classe, il riferimento dovrebbe essere stato aggiornato automaticamente. Tuttavia, se non è stato fatto, è necessario modificarlo manualmente.

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    if (env.IsDevelopment())
    {
        app.UseDeveloperExceptionPage();
    }

    app.UseRouting();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapGrpcService<PortfolioService>();
    });
}
```

Nella sezione successiva verranno aggiunte funzionalità a questo nuovo servizio.

>[!div class="step-by-step"]
>[Precedente](migrate-wcf-to-grpc.md)
>[Successivo](migrate-request-reply.md)
