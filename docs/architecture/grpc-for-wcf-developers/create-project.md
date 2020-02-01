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
# <a name="create-a-new-aspnet-core-grpc-project"></a><span data-ttu-id="6aeb8-103">Creare un nuovo progetto ASP.NET Core gRPC</span><span class="sxs-lookup"><span data-stu-id="6aeb8-103">Create a new ASP.NET Core gRPC project</span></span>

<span data-ttu-id="6aeb8-104">Il .NET Core SDK è dotato di uno strumento CLI potente, `dotnet`, che consente di creare e gestire progetti e soluzioni dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-104">The .NET Core SDK comes with a powerful CLI tool, `dotnet`, which enables you to create and manage projects and solutions from the command line.</span></span> <span data-ttu-id="6aeb8-105">L'SDK è strettamente integrato con Visual Studio, quindi tutti gli elementi sono disponibili anche tramite l'interfaccia utente grafica nota.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-105">The SDK is closely integrated with Visual Studio, so everything is also available through the familiar graphical user interface.</span></span> <span data-ttu-id="6aeb8-106">In questo capitolo vengono illustrate entrambe le modalità di creazione di un nuovo progetto di ASP.NET Core gRPC.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-106">This chapter shows both ways to create a new ASP.NET Core gRPC project.</span></span>

## <a name="create-the-project-by-using-visual-studio"></a><span data-ttu-id="6aeb8-107">Creare il progetto usando Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6aeb8-107">Create the project by using Visual Studio</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6aeb8-108">Per sviluppare qualsiasi app ASP.NET Core 3,0, è necessario Visual Studio 2019 versione 16,3 o successiva, con il carico di lavoro di **sviluppo ASP.NET e Web** installato.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-108">To develop any ASP.NET Core 3.0 app, you need Visual Studio 2019 version 16.3 or later, with the **ASP.NET and web development** workload installed.</span></span>

<span data-ttu-id="6aeb8-109">Creare una soluzione vuota denominata **TraderSys** dal modello di *soluzione vuota* .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-109">Create an empty solution called **TraderSys** from the *Blank Solution* template.</span></span> <span data-ttu-id="6aeb8-110">Aggiungere una cartella della soluzione denominata `src`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-110">Add a solution folder called `src`.</span></span> <span data-ttu-id="6aeb8-111">Quindi, fare clic con il pulsante destro del mouse sulla cartella e scegliere **aggiungi** > **nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-111">Then, right-click on the folder and choose **Add** > **New Project**.</span></span> <span data-ttu-id="6aeb8-112">Immettere `grpc` nella casella di ricerca del modello. verrà visualizzato un modello di progetto denominato `gRPC Service`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-112">Enter `grpc` in the template search box, and you should see a project template called `gRPC Service`.</span></span>

![Screenshot della finestra di dialogo Aggiungi nuovo progetto](media/create-project/new-grpc-project.png)

<span data-ttu-id="6aeb8-114">Selezionare **Avanti** per passare alla finestra di dialogo **Configura nuovo progetto** .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-114">Select **Next** to continue to the **Configure your new project** dialog box.</span></span> <span data-ttu-id="6aeb8-115">Denominare il progetto `TraderSys.Portfolios` e aggiungere una sottodirectory `src` al **percorso**.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-115">Name the project `TraderSys.Portfolios` and add an `src` subdirectory to the **Location**.</span></span>

![Screenshot della finestra di dialogo Configura nuovo progetto](media/create-project/configure-project.png)

<span data-ttu-id="6aeb8-117">Selezionare **Avanti** per passare alla finestra di dialogo **Crea un nuovo servizio gRPC** .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-117">Select **Next** to continue to the **Create a new gRPC service** dialog box.</span></span>

![Screenshot della finestra di dialogo Crea un nuovo servizio gRPC](media/create-project/create-new-grpc-service.png)

<span data-ttu-id="6aeb8-119">Al momento sono disponibili opzioni limitate per la creazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-119">At present, you have limited options for the service creation.</span></span> <span data-ttu-id="6aeb8-120">Docker verrà introdotto in un secondo momento, quindi, per ora, lasciare l'opzione deselezionata.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-120">Docker will be introduced later, so for now, leave that option unselected.</span></span> <span data-ttu-id="6aeb8-121">Basta selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-121">Just select **Create**.</span></span> <span data-ttu-id="6aeb8-122">Il primo progetto di ASP.NET Core 3,0 gRPC viene generato e aggiunto alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-122">Your first ASP.NET Core 3.0 gRPC project is generated and added to the solution.</span></span> <span data-ttu-id="6aeb8-123">Se non si vuole sapere come usare la `dotnet CLI`, passare alla sezione [pulire il codice di esempio](#clean-up-the-example-code) .</span><span class="sxs-lookup"><span data-stu-id="6aeb8-123">If you don't want to know about working with the `dotnet CLI`, skip to the [Clean up the example code](#clean-up-the-example-code) section.</span></span>

## <a name="create-the-project-by-using-the-net-core-cli"></a><span data-ttu-id="6aeb8-124">Creare il progetto usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="6aeb8-124">Create the project by using the .NET Core CLI</span></span>

<span data-ttu-id="6aeb8-125">In questa sezione viene illustrata la creazione di soluzioni e progetti dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-125">This section covers the creation of solutions and projects from the command line.</span></span>

<span data-ttu-id="6aeb8-126">Creare la soluzione come illustrato nel comando seguente.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-126">Create the solution as shown in the following command.</span></span> <span data-ttu-id="6aeb8-127">Il flag `-o` (o `--output`) specifica la directory di output, che viene creata nella directory corrente, se non esiste già.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-127">The `-o` (or `--output`) flag specifies the output directory, which is created in the current directory if it doesn't already exist.</span></span> <span data-ttu-id="6aeb8-128">La soluzione ha lo stesso nome della directory: `TraderSys.sln`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-128">The solution has the same name as the directory: `TraderSys.sln`.</span></span> <span data-ttu-id="6aeb8-129">È possibile specificare un nome diverso usando il flag `-n` (o `--name`).</span><span class="sxs-lookup"><span data-stu-id="6aeb8-129">You can provide a different name by using the `-n` (or `--name`) flag.</span></span>

```dotnetcli
dotnet new sln -o TraderSys
cd TraderSys
```

<span data-ttu-id="6aeb8-130">ASP.NET Core 3,0 viene fornita con un modello CLI per i servizi gRPC.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-130">ASP.NET Core 3.0 comes with a CLI template for gRPC services.</span></span> <span data-ttu-id="6aeb8-131">Creare il nuovo progetto usando questo modello, inserendolo in una sottodirectory `src` come è convenzionale per i progetti ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-131">Create the new project by using this template, putting it into an `src` subdirectory as is conventional for ASP.NET Core projects.</span></span> <span data-ttu-id="6aeb8-132">Il progetto viene denominato dopo la directory (`TraderSys.Portfolios.csproj`), a meno che non si specifichi un nome diverso con il flag di `-n`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-132">The project is named after the directory (`TraderSys.Portfolios.csproj`), unless you specify a different name with the `-n` flag.</span></span>

```dotnetcli
dotnet new grpc -o src/TraderSys.Portfolios
```

<span data-ttu-id="6aeb8-133">Aggiungere infine il progetto alla soluzione usando il comando `dotnet sln`:</span><span class="sxs-lookup"><span data-stu-id="6aeb8-133">Finally, add the project to the solution by using the `dotnet sln` command:</span></span>

```dotnetcli
dotnet sln add src/TraderSys.Portfolios
```

> [!TIP]
> <span data-ttu-id="6aeb8-134">Poiché la directory specifica contiene solo un singolo file di `.csproj`, è possibile specificare solo la directory per salvare la digitazione.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-134">Because the particular directory only contains a single `.csproj` file, you can specify just the directory, to save typing.</span></span>

<span data-ttu-id="6aeb8-135">È ora possibile aprire la soluzione in Visual Studio 2019, Visual Studio Code o qualsiasi altro editor preferito.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-135">You can now open this solution in Visual Studio 2019, Visual Studio Code, or whatever editor you prefer.</span></span>

## <a name="clean-up-the-example-code"></a><span data-ttu-id="6aeb8-136">Pulire il codice di esempio</span><span class="sxs-lookup"><span data-stu-id="6aeb8-136">Clean up the example code</span></span>

<span data-ttu-id="6aeb8-137">A questo punto è stato creato un servizio di esempio usando il modello gRPC, che è stato esaminato in precedenza nel libro.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-137">You've now created an example service by using the gRPC template, which was reviewed earlier in the book.</span></span> <span data-ttu-id="6aeb8-138">Questo non è utile nel contesto di trading azionario, quindi verranno modificati gli elementi per il primo progetto.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-138">This isn't useful in our stock trading context, so we'll edit things for our first project.</span></span>

### <a name="rename-and-edit-the-proto-file"></a><span data-ttu-id="6aeb8-139">Rinominare e modificare il file proto</span><span class="sxs-lookup"><span data-stu-id="6aeb8-139">Rename and edit the proto file</span></span>

<span data-ttu-id="6aeb8-140">Procedere e rinominare il file di `Protos/greet.proto` in `Protos/portfolios.proto`e aprirlo nell'editor.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-140">Go ahead and rename the `Protos/greet.proto` file to `Protos/portfolios.proto`, and open it in your editor.</span></span> <span data-ttu-id="6aeb8-141">Elimina tutti gli elementi dopo la riga di `package`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-141">Delete everything after the `package` line.</span></span> <span data-ttu-id="6aeb8-142">Modificare quindi i nomi di `option csharp_namespace`, `package` e `service` e rimuovere il servizio `SayHello` predefinito.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-142">Then change the `option csharp_namespace`, `package` and `service` names, and remove the default `SayHello` service.</span></span> <span data-ttu-id="6aeb8-143">Il codice ha ora un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="6aeb8-143">The code now looks like the following:</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.Portfolios.Protos";

package PortfolioServer;

service Portfolios {
  // RPCs will go here
}
```

> [!TIP]
> <span data-ttu-id="6aeb8-144">Il modello non aggiunge la parte dello spazio dei nomi `Protos` per impostazione predefinita, ma l'aggiunta rende più semplice la conservazione delle classi generate da gRPC e delle classi delimitate in modo chiaro nel codice.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-144">The template doesn't add the `Protos` namespace part by default, but adding it makes it easier to keep gRPC-generated classes and your own classes clearly separated in your code.</span></span>

<span data-ttu-id="6aeb8-145">Se si rinomina il file di `greet.proto` in un Integrated Development Environment (IDE) come Visual Studio, un riferimento a questo file viene aggiornato automaticamente nel file `.csproj`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-145">If you rename the `greet.proto` file in an integrated development environment (IDE) like Visual Studio, a reference to this file is automatically updated in the `.csproj` file.</span></span> <span data-ttu-id="6aeb8-146">Tuttavia, in un altro editor, ad esempio Visual Studio Code, questo riferimento non viene aggiornato automaticamente, quindi è necessario modificare il file di progetto manualmente.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-146">But in some other editor, such as Visual Studio Code, this reference isn't updated automatically, so you need to edit the project file manually.</span></span>

<span data-ttu-id="6aeb8-147">Nelle destinazioni di compilazione di gRPC è presente un elemento `Protobuf` elemento che consente di specificare quali file di `.proto` devono essere compilati e quale forma di generazione del codice è necessaria (ovvero "Server" o "client").</span><span class="sxs-lookup"><span data-stu-id="6aeb8-147">In the gRPC build targets, there's a `Protobuf` item element that lets you specify which `.proto` files should be compiled, and which form of code generation is required (that is, "Server" or "Client").</span></span>

```xml
<ItemGroup>
  <Protobuf Include="Protos\portfolios.proto" GrpcServices="Server" />
</ItemGroup>
```

### <a name="rename-the-greeterservice-class"></a><span data-ttu-id="6aeb8-148">Rinominare la classe `GreeterService`</span><span class="sxs-lookup"><span data-stu-id="6aeb8-148">Rename the `GreeterService` class</span></span>

<span data-ttu-id="6aeb8-149">La classe `GreeterService` si trova nella cartella `Services` ed eredita da `Greeter.GreeterBase`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-149">The `GreeterService` class is in the `Services` folder and inherits from `Greeter.GreeterBase`.</span></span> <span data-ttu-id="6aeb8-150">Rinominare il `PortfolioService`e impostare la classe di base su `Portfolios.PortfoliosBase`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-150">Rename it to `PortfolioService`, and change the base class to `Portfolios.PortfoliosBase`.</span></span> <span data-ttu-id="6aeb8-151">Eliminare i metodi `override`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-151">Delete the `override` methods.</span></span>

```csharp
public class PortfolioService : Portfolios.PortfoliosBase
{
}
```

<span data-ttu-id="6aeb8-152">Si è verificato un riferimento alla classe `GreeterService` nel metodo `Configure` della classe `Startup`.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-152">There was a reference to the `GreeterService` class in the `Configure` method in the `Startup` class.</span></span> <span data-ttu-id="6aeb8-153">Se è stato usato il refactoring per rinominare la classe, il riferimento dovrebbe essere stato aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-153">If you used refactoring to rename the class, this reference should have been updated automatically.</span></span> <span data-ttu-id="6aeb8-154">Tuttavia, se non è stato fatto, è necessario modificarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-154">However, if you didn't, you need to edit it manually.</span></span>

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

<span data-ttu-id="6aeb8-155">Nella sezione successiva verranno aggiunte funzionalità a questo nuovo servizio.</span><span class="sxs-lookup"><span data-stu-id="6aeb8-155">In the next section, we'll add functionality to this new service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6aeb8-156">[Precedente](migrate-wcf-to-grpc.md)
>[Successivo](migrate-request-reply.md)</span><span class="sxs-lookup"><span data-stu-id="6aeb8-156">[Previous](migrate-wcf-to-grpc.md)
[Next](migrate-request-reply.md)</span></span>
