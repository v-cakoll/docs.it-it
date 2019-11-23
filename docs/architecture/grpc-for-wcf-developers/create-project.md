---
title: Creare una nuova ASP.NET Core progetto gRPC-gRPC per sviluppatori WCF
description: Informazioni su come creare un progetto gRPC con Visual Studio o dalla riga di comando.
ms.date: 09/02/2019
ms.openlocfilehash: 992c3f57be25ae2517d41437170dc287f58934b6
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967885"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="3b15f-103">Creare un nuovo progetto ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="3b15f-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="3b15f-104">.NET Core è dotato di uno strumento CLI potente, `dotnet`, che consente di creare e gestire progetti e soluzioni dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3b15f-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="3b15f-105">Lo strumento è strettamente integrato con Visual Studio, quindi tutti gli elementi sono disponibili anche tramite la nota interfaccia GUI.</span><span class="sxs-lookup"><span data-stu-id="3b15f-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="3b15f-106">In questo capitolo vengono illustrate entrambe le modalità per creare un nuovo progetto di ASP.NET Core gRPC: prima di tutto con Visual Studio, quindi con l'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b15f-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="3b15f-107">Creare il progetto con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3b15f-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b15f-108">Per sviluppare qualsiasi app ASP.NET Core 3,0, è necessario Visual Studio 2019,3 o versione successiva con il carico di lavoro di **sviluppo ASP.NET e Web** installato.</span><span class="sxs-lookup"><span data-stu-id="3b15f-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="3b15f-109">Creare una soluzione vuota denominata **TraderSys** dal modello di *soluzione vuota* .</span><span class="sxs-lookup"><span data-stu-id="3b15f-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="3b15f-110">Aggiungere una cartella della soluzione denominata `src`, quindi fare clic con il pulsante destro del mouse sulla cartella e scegliere **aggiungi** > **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="3b15f-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="3b15f-111">Immettere `grpc` nella casella di ricerca del modello. verrà visualizzato un modello di progetto denominato `gRPC Service`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

![Finestra di dialogo Aggiungi nuovo progetto che mostra il modello di progetto di servizio gRPC](media/create-project/new-grpc-project.png)

<span data-ttu-id="3b15f-113">Fare clic su **Avanti** per passare alla finestra di dialogo **Configura progetto** e denominare il progetto `TraderSys.Portfolios`e aggiungere una sottodirectory `src` al **percorso**.</span><span class="sxs-lookup"><span data-stu-id="3b15f-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Finestra di dialogo Configura progetto](media/create-project/configure-project.png)

<span data-ttu-id="3b15f-115">Fare clic su **Avanti** per passare alla finestra di dialogo **nuovo progetto gRPC** .</span><span class="sxs-lookup"><span data-stu-id="3b15f-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

![Finestra di dialogo nuovo progetto gRPC](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="3b15f-117">Al momento sono disponibili opzioni limitate per la creazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="3b15f-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="3b15f-118">Docker verrà introdotto più avanti nel libro, quindi lasciare deselezionata la casella di controllo per il momento e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="3b15f-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="3b15f-119">Il primo progetto di ASP.NET Core 3,0 gRPC viene generato e aggiunto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="3b15f-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="3b15f-120">Se non si vuole sapere come usare la `dotnet CLI`, passare alla sezione [pulire il codice di esempio](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="3b15f-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="3b15f-121">Creare il progetto usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="3b15f-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="3b15f-122">In questa sezione viene illustrata la creazione di soluzioni e progetti dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="3b15f-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="3b15f-123">Creare la soluzione come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="3b15f-123">Create the solution as shown below.</span></span> <span data-ttu-id="3b15f-124">Il flag `-o` (o `--output`) specifica la directory di output, che verrà creata nella directory corrente, se non esiste.</span><span class="sxs-lookup"><span data-stu-id="3b15f-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="3b15f-125">Alla soluzione verrà assegnato lo stesso nome della directory, ad esempio `TraderSys.sln`. È possibile specificare un nome diverso usando il flag `-n` (o `--name`).</span><span class="sxs-lookup"><span data-stu-id="3b15f-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="3b15f-126">ASP.NET Core 3,0 viene fornita con un modello CLI per i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="3b15f-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="3b15f-127">Creare il nuovo progetto usando questo modello, inserendolo in una sottodirectory `src` come Convenzione per i progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="3b15f-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="3b15f-128">Il progetto verrà denominato dopo la directory (ad esempio `TraderSys.Portfolios.csproj`), a meno che non si specifichi un nome diverso con il flag di `-n`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="3b15f-129">Infine, aggiungere il progetto alla soluzione usando il comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="3b15f-130">Poiché la directory specificata contiene solo un singolo file di `.csproj`, è possibile evitare di specificare solo la directory per il salvataggio della digitazione.</span><span class="sxs-lookup"><span data-stu-id="3b15f-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="3b15f-131">È ora possibile aprire la soluzione in Visual Studio 2019, Visual Studio Code o qualsiasi altro editor preferito.</span><span class="sxs-lookup"><span data-stu-id="3b15f-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="3b15f-132">Pulire il codice di esempio</span><span class="sxs-lookup"><span data-stu-id="3b15f-132">Clean up the example code</span></span>

<span data-ttu-id="3b15f-133">A questo punto è stato creato un servizio di esempio con il modello gRPC, che è stato esaminato in precedenza nel libro.</span><span class="sxs-lookup"><span data-stu-id="3b15f-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="3b15f-134">Questo non è utile nel contesto di trading azionario, quindi verranno modificati gli elementi per il primo progetto.</span><span class="sxs-lookup"><span data-stu-id="3b15f-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="3b15f-135">Rinominare e modificare il file proto</span><span class="sxs-lookup"><span data-stu-id="3b15f-135">Rename and edit the proto file</span></span>

<span data-ttu-id="3b15f-136">Procedere e rinominare il file di `Protos/greet.proto` per `Protos/portfolios.proto` e aprirlo nell'editor.</span><span class="sxs-lookup"><span data-stu-id="3b15f-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="3b15f-137">Eliminare tutti gli elementi dopo la riga di `package`, quindi modificare i nomi di `option csharp_namespace`, `package` e `service` e rimuovere il servizio di `SayHello` predefinito, in modo che il codice sia simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="3b15f-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="3b15f-138">Il modello non aggiunge la parte dello spazio dei nomi `Protos` per impostazione predefinita, ma l'aggiunta rende più semplice la conservazione delle classi generate da gRPC e delle classi delimitate in modo chiaro nel codice.</span><span class="sxs-lookup"><span data-stu-id="3b15f-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="3b15f-139">Se si rinomina il file di `greet.proto` in un Integrated Development Environment (IDE) come Visual Studio, un riferimento a questo file viene aggiornato automaticamente nel file `.csproj`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="3b15f-140">Tuttavia, in un altro editor, ad esempio Visual Studio Code, questo riferimento non viene aggiornato automaticamente, quindi è necessario modificare il file di progetto manualmente.</span><span class="sxs-lookup"><span data-stu-id="3b15f-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="3b15f-141">Nelle destinazioni di compilazione di gRPC è presente un elemento `Protobuf` elemento che consente di specificare quali file di `.proto` devono essere compilati e quale forma di generazione del codice è necessaria (ovvero "Server" o "client").</span><span class="sxs-lookup"><span data-stu-id="3b15f-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="3b15f-142">Rinominare la classe GreeterService</span><span class="sxs-lookup"><span data-stu-id="3b15f-142">Rename the GreeterService class</span></span>

<span data-ttu-id="3b15f-143">La classe `GreeterService` si trova nella cartella `Services` ed eredita da `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="3b15f-144">Rinominarlo in `PortfolioService` e impostare la classe di base su `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="3b15f-145">Eliminare i metodi `override`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="3b15f-146">Si è verificato un riferimento alla classe `GreeterService` nel metodo `Configure` della classe `Startup`.</span><span class="sxs-lookup"><span data-stu-id="3b15f-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="3b15f-147">Se è stato usato il refactoring per rinominare la classe, il riferimento dovrebbe essere stato aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="3b15f-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="3b15f-148">Tuttavia, se non è stato fatto, è necessario modificarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="3b15f-148">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="3b15f-149">Nella sezione successiva verranno aggiunte funzionalità a questo nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="3b15f-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3b15f-150">[Precedente](migrate-wcf-to-grpc.md)
>[Successivo](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="3b15f-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
