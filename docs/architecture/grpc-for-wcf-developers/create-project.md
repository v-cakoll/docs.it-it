---
title: Creare una nuova ASP.NET Core progetto gRPC-gRPC per sviluppatori WCF
description: Informazioni su come creare un progetto gRPC con Visual Studio o dalla riga di comando.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: a0fcc3f9c4e32e87260a6bc79205c909ea3800e0
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2019
ms.locfileid: "71184568"
---
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="611c9-103">Creare un nuovo progetto di ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="611c9-103">Create a new ASP.NET Core gRPC project</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="611c9-104">.NET Core è dotato di un potente strumento CLI `dotnet`,, che consente di creare e gestire progetti e soluzioni dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="611c9-104">.NET Core comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="611c9-105">Lo strumento è strettamente integrato con Visual Studio, quindi tutti gli elementi sono disponibili anche tramite la nota interfaccia GUI.</span><span class="sxs-lookup"><span data-stu-id="611c9-105">The tool is closely integrated with Visual Studio, so everything is also available through the familiar GUI interface.</span></span> <span data-ttu-id="611c9-106">In questo capitolo vengono illustrate entrambe le modalità per creare un nuovo progetto di ASP.NET Core gRPC: prima di tutto con Visual Studio, quindi con l'interfaccia della riga di comando di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="611c9-106">This chapter will show both ways to create a new ASP.NET Core gRPC project: first with Visual Studio, then with the .NET Core CLI.</span></span>

## <a name="create-the-project-using-visual-studio"></a><span data-ttu-id="611c9-107">Creare il progetto con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="611c9-107">Create the project using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="611c9-108">Per sviluppare qualsiasi app ASP.NET Core 3,0, è necessario Visual Studio 2019,3 o versione successiva con il carico di lavoro di **sviluppo ASP.NET e Web** installato.</span><span class="sxs-lookup"><span data-stu-id="611c9-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019.3 or later with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="611c9-109">Creare una soluzione vuota denominata **TraderSys** dal modello di *soluzione vuota* .</span><span class="sxs-lookup"><span data-stu-id="611c9-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="611c9-110">Aggiungere una cartella della soluzione `src`denominata, quindi fare clic con il pulsante destro del mouse sulla cartella e scegliere **Aggiungi** > **nuovo progetto** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="611c9-110">Add a Solution Folder called `src`, then right-click on the folder and choose **Add** > **New Project** from the context menu.</span></span> <span data-ttu-id="611c9-111">Immettere `grpc` nella casella di ricerca del modello. verrà visualizzato un modello di progetto `gRPC Service`denominato.</span><span class="sxs-lookup"><span data-stu-id="611c9-111">Enter `grpc` in the template search box and you should see a project template called `gRPC Service`.</span></span>

![Finestra di dialogo Aggiungi nuovo progetto che mostra il modello di progetto di servizio gRPC](media/create-project/new-grpc-project.png)

<span data-ttu-id="611c9-113">Fare clic su **Avanti** per passare alla finestra di dialogo **Configura progetto** e `TraderSys.Portfolios`assegnare un nome al `src` progetto e aggiungere una sottodirectory al **percorso**.</span><span class="sxs-lookup"><span data-stu-id="611c9-113">Click **Next** to continue to the **Configure project** dialog and name the project `TraderSys.Portfolios`, and add an `src` subdirectory to the **Location**.</span></span>

![Finestra di dialogo Configura progetto](media/create-project/configure-project.png)

<span data-ttu-id="611c9-115">Fare clic su **Avanti** per passare alla finestra di dialogo **nuovo progetto gRPC** .</span><span class="sxs-lookup"><span data-stu-id="611c9-115">Click **Next** to continue to the **New gRPC project** dialog.</span></span>

![Finestra di dialogo nuovo progetto gRPC](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="611c9-117">Al momento sono disponibili opzioni limitate per la creazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="611c9-117">At present, there are limited options for the service creation.</span></span> <span data-ttu-id="611c9-118">Docker verrà introdotto più avanti nel libro, quindi lasciare deselezionata la casella di controllo per il momento e fare clic su **Crea**.</span><span class="sxs-lookup"><span data-stu-id="611c9-118">Docker will be introduced later in the book, so leave that checkbox unchecked for now and just click **Create**.</span></span> <span data-ttu-id="611c9-119">Il primo progetto di ASP.NET Core 3,0 gRPC viene generato e aggiunto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="611c9-119">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="611c9-120">Per informazioni sull'utilizzo `dotnet CLI`di, passare alla sezione [pulire il codice di esempio](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="611c9-120">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-using-the-net-core-cli"></a><span data-ttu-id="611c9-121">Creare il progetto usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="611c9-121">Create the project using the .NET Core CLI</span></span>

<span data-ttu-id="611c9-122">In questa sezione viene illustrata la creazione di soluzioni e progetti dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="611c9-122">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="611c9-123">Creare la soluzione come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="611c9-123">Create the solution as shown below.</span></span> <span data-ttu-id="611c9-124">Il `-o` flag ( `--output`o) specifica la directory di output, che verrà creata nella directory corrente, se non esiste.</span><span class="sxs-lookup"><span data-stu-id="611c9-124">The `-o` (or `--output`) flag specifies the output directory, which will be created in the current directory if it does not exist.</span></span> <span data-ttu-id="611c9-125">Alla soluzione verrà assegnato lo stesso nome della directory, ad esempio `TraderSys.sln`. È possibile specificare un nome diverso usando il `-n` flag ( `--name`o).</span><span class="sxs-lookup"><span data-stu-id="611c9-125">The solution will be given the same name as the directory, i.e. `TraderSys.sln`. You can provide a different name using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="611c9-126">ASP.NET Core 3,0 viene fornita con un modello CLI per i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="611c9-126">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="611c9-127">Creare il nuovo progetto usando questo modello, inserendolo in una `src` sottodirectory come Convenzione per i progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="611c9-127">Create the new project using this template, putting it into an `src` subdirectory as is the convention for ASP.NET Core projects.</span></span> <span data-ttu-id="611c9-128">Il progetto verrà denominato dopo la directory (ad esempio `TraderSys.Portfolios.csproj`), a meno che non si specifichi un nome diverso con il `-n` flag.</span><span class="sxs-lookup"><span data-stu-id="611c9-128">The project will be named after the directory (i.e. `TraderSys.Portfolios.csproj`) unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="611c9-129">Infine, aggiungere il progetto alla soluzione usando il `dotnet sln` comando.</span><span class="sxs-lookup"><span data-stu-id="611c9-129">Finally, add the project to the solution using the `dotnet sln` command.</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="611c9-130">Poiché la directory specificata contiene solo un singolo `.csproj` file, è possibile specificare solo la directory per salvare la digitazione.</span><span class="sxs-lookup"><span data-stu-id="611c9-130">Since the given directory only contains a single `.csproj` file, you can get away with specifying just the directory to save typing.</span></span>

<span data-ttu-id="611c9-131">È ora possibile aprire la soluzione in Visual Studio 2019, Visual Studio Code o qualsiasi altro editor preferito.</span><span class="sxs-lookup"><span data-stu-id="611c9-131">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="611c9-132">Pulire il codice di esempio</span><span class="sxs-lookup"><span data-stu-id="611c9-132">Clean up the example code</span></span>

<span data-ttu-id="611c9-133">A questo punto è stato creato un servizio di esempio con il modello gRPC, che è stato esaminato in precedenza nel libro.</span><span class="sxs-lookup"><span data-stu-id="611c9-133">You've now created an example service using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="611c9-134">Questo non è utile nel contesto di trading azionario, quindi verranno modificati gli elementi per il primo progetto.</span><span class="sxs-lookup"><span data-stu-id="611c9-134">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="611c9-135">Rinominare e modificare il file proto</span><span class="sxs-lookup"><span data-stu-id="611c9-135">Rename and edit the proto file</span></span>

<span data-ttu-id="611c9-136">Procedere e rinominare il `Protos/greet.proto` `Protos/portfolios.proto` file in e aprirlo nell'editor.</span><span class="sxs-lookup"><span data-stu-id="611c9-136">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto` and open it in your editor.</span></span> <span data-ttu-id="611c9-137">Eliminare tutti gli elementi `package` dopo la riga, modificare `option csharp_namespace` `package` i nomi `service` e, quindi rimuovere il servizio `SayHello` predefinito, in modo che il codice sia simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="611c9-137">Delete everything after the `package` line, then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service, so the code looks like this.</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="611c9-138">Il modello non aggiunge la `Protos` parte dello spazio dei nomi per impostazione predefinita, ma l'aggiunta rende più semplice la conservazione delle classi generate da gRPC e delle classi delimitate in modo chiaro nel codice.</span><span class="sxs-lookup"><span data-stu-id="611c9-138">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="611c9-139">Se si rinomina il `greet.proto` file in un Integrated Development Environment (IDE) come Visual Studio, `.csproj` nel file viene automaticamente aggiornato un riferimento a questo file.</span><span class="sxs-lookup"><span data-stu-id="611c9-139">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="611c9-140">Tuttavia, in un altro editor, ad esempio Visual Studio Code, questo riferimento non viene aggiornato automaticamente, quindi è necessario modificare il file di progetto manualmente.</span><span class="sxs-lookup"><span data-stu-id="611c9-140">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="611c9-141">Nelle destinazioni di compilazione di gRPC è presente un `Protobuf` elemento Item che consente di `.proto` specificare i file da compilare e il formato di generazione del codice necessario, ovvero "Server" o "client".</span><span class="sxs-lookup"><span data-stu-id="611c9-141">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="611c9-142">Rinominare la classe GreeterService</span><span class="sxs-lookup"><span data-stu-id="611c9-142">Rename the GreeterService class</span></span>

<span data-ttu-id="611c9-143">La `GreeterService` classe si trova `Services` nella cartella ed eredita da `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="611c9-143">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="611c9-144">Rinominarlo `Portfolios.PortfoliosBase`emodificarela classe di base in. `PortfolioService`</span><span class="sxs-lookup"><span data-stu-id="611c9-144">Rename it to `PortfolioService` and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="611c9-145">Eliminare i `override` metodi.</span><span class="sxs-lookup"><span data-stu-id="611c9-145">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="611c9-146">Si è verificato un riferimento alla `GreeterService` classe `Configure` nel metodo nella `Startup` classe.</span><span class="sxs-lookup"><span data-stu-id="611c9-146">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="611c9-147">Se è stato usato il refactoring per rinominare la classe, il riferimento dovrebbe essere stato aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="611c9-147">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="611c9-148">Tuttavia, se non è stato fatto, è necessario modificarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="611c9-148">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="611c9-149">Nella sezione successiva verranno aggiunte funzionalità a questo nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="611c9-149">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="611c9-150">[Precedente](migrate-wcf-to-grpc.md)
>[Successivo](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="611c9-150">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
