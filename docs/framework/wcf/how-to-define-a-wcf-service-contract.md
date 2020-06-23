---
title: 'Esercitazione: definire un contratto di servizio Windows Communication Foundation'
description: Informazioni su come definire un contratto di servizio come parte di una serie di articoli che consentono di iniziare a creare un'applicazione WCF.
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 5cb371da8c7180b8c4cbf5ac11468fbb8e0e13cc
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246311"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="4e341-103">Esercitazione: definire un contratto di servizio Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4e341-103">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="4e341-104">In questa esercitazione viene descritta la prima delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4e341-104">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4e341-105">Per una panoramica delle esercitazioni, vedere [esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="4e341-105">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="4e341-106">Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4e341-106">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="4e341-107">Il contratto di servizio specifica le operazioni supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4e341-107">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="4e341-108">Un'operazione può essere considerata un metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="4e341-108">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="4e341-109">I contratti di servizio vengono creati definendo un'interfaccia C# o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4e341-109">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="4e341-110">Un'interfaccia presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e341-110">An interface has the following characteristics:</span></span>

- <span data-ttu-id="4e341-111">Ogni metodo dell'interfaccia corrisponde a un'operazione di servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="4e341-111">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="4e341-112">Per ogni interfaccia, è necessario applicare l' <xref:System.ServiceModel.ServiceContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="4e341-112">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="4e341-113">Per ogni operazione/metodo è necessario applicare l' <xref:System.ServiceModel.OperationContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="4e341-113">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="4e341-114">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="4e341-114">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="4e341-115">Creare un progetto **libreria di servizi WCF** .</span><span class="sxs-lookup"><span data-stu-id="4e341-115">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="4e341-116">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4e341-116">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="4e341-117">Creare un progetto libreria di servizi WCF e definire un'interfaccia del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="4e341-117">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="4e341-118">Aprire Visual Studio come amministratore.</span><span class="sxs-lookup"><span data-stu-id="4e341-118">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="4e341-119">A tale scopo, selezionare il programma di Visual Studio nel menu **Start** , quindi selezionare **altro**  >  **Esegui come amministratore** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="4e341-119">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="4e341-120">Creare un progetto **libreria di servizi WCF** .</span><span class="sxs-lookup"><span data-stu-id="4e341-120">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="4e341-121">Scegliere **Nuovo** > **Progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="4e341-121">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="4e341-122">Nella finestra di dialogo **nuovo progetto** , sul lato sinistro, espandere **Visual C#** o **Visual Basic**, quindi selezionare la categoria **WCF** .</span><span class="sxs-lookup"><span data-stu-id="4e341-122">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="4e341-123">Visual Studio Visualizza un elenco di modelli di progetto nella sezione centrale della finestra.</span><span class="sxs-lookup"><span data-stu-id="4e341-123">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="4e341-124">Selezionare **libreria del servizio WCF**.</span><span class="sxs-lookup"><span data-stu-id="4e341-124">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="4e341-125">Se non viene visualizzata la categoria del modello di progetto **WCF** , potrebbe essere necessario installare il componente **Windows Communication Foundation** di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4e341-125">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="4e341-126">Nella finestra di dialogo **nuovo progetto** selezionare il collegamento **Apri programma di installazione di Visual Studio** sul lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="4e341-126">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="4e341-127">Selezionare la scheda **singoli componenti** , quindi individuare e selezionare **Windows Communication Foundation** nella categoria **attività di sviluppo** .</span><span class="sxs-lookup"><span data-stu-id="4e341-127">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="4e341-128">Scegliere **modifica** per avviare l'installazione del componente.</span><span class="sxs-lookup"><span data-stu-id="4e341-128">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="4e341-129">Nella sezione inferiore della finestra immettere *GettingStartedLib* per **nome** e *GettingStarted* per il **nome della soluzione**.</span><span class="sxs-lookup"><span data-stu-id="4e341-129">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="4e341-130">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="4e341-130">Select **OK**.</span></span>

      <span data-ttu-id="4e341-131">Visual Studio crea il progetto, che include tre file: *IService1.cs* (o *IService1. vb* per un progetto Visual Basic), *Service1.cs* (o *Service1. vb* per un progetto Visual Basic) e *App.config*. Visual Studio definisce questi file come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4e341-131">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="4e341-132">Il file *IService1* contiene la definizione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4e341-132">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="4e341-133">Il file *Service1* contiene l'implementazione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4e341-133">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="4e341-134">Il file di *App.config* contiene le informazioni di configurazione necessarie per caricare il servizio predefinito con lo strumento host del servizio WCF di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4e341-134">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="4e341-135">Per ulteriori informazioni sullo strumento host del servizio WCF, vedere [host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4e341-135">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="4e341-136">Se Visual Studio è stato installato con Visual Basic impostazioni dell'ambiente di sviluppo, la soluzione potrebbe essere nascosta.</span><span class="sxs-lookup"><span data-stu-id="4e341-136">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="4e341-137">In tal caso, scegliere **Opzioni** dal menu **strumenti** , quindi scegliere **progetti e soluzioni**  >  **generale** nella finestra **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="4e341-137">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="4e341-138">Selezionare **Mostra sempre soluzione**.</span><span class="sxs-lookup"><span data-stu-id="4e341-138">Select **Always show solution**.</span></span> <span data-ttu-id="4e341-139">Inoltre, verificare che l'opzione **Salva nuovi progetti al momento della creazione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4e341-139">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="4e341-140">Da **Esplora soluzioni**aprire il file **IService1.cs** o **IService1. vb** e sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4e341-140">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     <span data-ttu-id="4e341-141">Questo contratto definisce una calcolatrice online.</span><span class="sxs-lookup"><span data-stu-id="4e341-141">This contract defines an online calculator.</span></span> <span data-ttu-id="4e341-142">Si noti `ICalculator` che l'interfaccia è contrassegnata con l' <xref:System.ServiceModel.ServiceContractAttribute> attributo (semplificato come `ServiceContract` ).</span><span class="sxs-lookup"><span data-stu-id="4e341-142">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="4e341-143">Questo attributo definisce uno spazio dei nomi per evitare ambiguità nel nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="4e341-143">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="4e341-144">Il codice contrassegna ogni operazione del calcolatore con l' <xref:System.ServiceModel.OperationContractAttribute> attributo (semplificato come `OperationContract` ).</span><span class="sxs-lookup"><span data-stu-id="4e341-144">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4e341-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4e341-145">Next steps</span></span>

<span data-ttu-id="4e341-146">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="4e341-146">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="4e341-147">Creare un progetto libreria di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="4e341-147">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="4e341-148">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4e341-148">Define a service contract interface.</span></span>

<span data-ttu-id="4e341-149">Passare all'esercitazione successiva per apprendere come implementare il contratto di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="4e341-149">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4e341-150">Esercitazione: implementare un contratto di servizio WCF</span><span class="sxs-lookup"><span data-stu-id="4e341-150">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
