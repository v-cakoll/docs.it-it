---
title: 'Esercitazione: Definire un contratto di servizio Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: ba88fc6ba4cba8d46ed1b43080d471b1b7c4bd75
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928880"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="ce2b1-102">Esercitazione: Definire un contratto di servizio Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ce2b1-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="ce2b1-103">In questa esercitazione viene descritta la prima delle cinque attività necessarie per creare un'applicazione di base Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ce2b1-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="ce2b1-104">Per una panoramica delle esercitazioni, vedere [esercitazione: Inizia a usare Windows Communication Foundation applicazioni](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ce2b1-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="ce2b1-105">Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="ce2b1-106">Nel contratto di servizio vengono specificate le operazioni supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="ce2b1-107">Un'operazione può essere considerata un metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="ce2b1-108">I contratti di servizio vengono creati definendo un' C# interfaccia Visual o Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="ce2b1-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="ce2b1-109">Un'interfaccia presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="ce2b1-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="ce2b1-110">Ogni metodo nell'interfaccia corrisponde a un'operazione del servizio specifica.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="ce2b1-111">Per ogni interfaccia, è necessario applicare l' <xref:System.ServiceModel.ServiceContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="ce2b1-112">Per ogni operazione/metodo è necessario applicare l' <xref:System.ServiceModel.OperationContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="ce2b1-113">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="ce2b1-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ce2b1-114">Creare un progetto **libreria di servizi WCF** .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="ce2b1-115">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="ce2b1-116">Creare un progetto libreria di servizi WCF e definire un'interfaccia del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="ce2b1-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="ce2b1-117">Aprire Visual Studio come amministratore.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="ce2b1-118">A tale scopo, selezionare il programma di Visual Studio nel menu **Start** , quindi selezionare **altro** > **Esegui come amministratore** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="ce2b1-119">Creare un progetto **libreria di servizi WCF** .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="ce2b1-120">Scegliere **Nuovo** > **Progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="ce2b1-121">Nella finestra di dialogo **nuovo progetto** , sul lato sinistro, espandere  **C# Visual** o **Visual Basic**, quindi selezionare la categoria **WCF** .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="ce2b1-122">Visual Studio Visualizza un elenco di modelli di progetto nella sezione centrale della finestra.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="ce2b1-123">Selezionare **libreria del servizio WCF**.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="ce2b1-124">Se non viene visualizzata la categoria del modello di progetto **WCF** , potrebbe essere necessario installare il componente **Windows Communication Foundation** di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="ce2b1-125">Nella finestra di dialogo **nuovo progetto** selezionare il collegamento **Apri programma di installazione di Visual Studio** sul lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="ce2b1-126">Selezionare la scheda **singoli componenti** , quindi individuare e selezionare **Windows Communication Foundation** nella categoria **attività di sviluppo** .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="ce2b1-127">Scegliere **modifica** per avviare l'installazione del componente.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="ce2b1-128">Nella sezione inferiore della finestra immettere *GettingStartedLib* per **nome** e *GettingStarted* per il **nome della soluzione**.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="ce2b1-129">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-129">Select **OK**.</span></span>

      <span data-ttu-id="ce2b1-130">Visual Studio crea il progetto, che include tre file: *IService1.cs* (o *IService1. vb* per un progetto Visual Basic), *Service1.cs* (o *Service1. vb* per un progetto Visual Basic) e *app. config*. Visual Studio definisce questi file come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ce2b1-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="ce2b1-131">Il file *IService1* contiene la definizione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="ce2b1-132">Il file *Service1* contiene l'implementazione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="ce2b1-133">Il file *app. config* contiene le informazioni di configurazione necessarie per caricare il servizio predefinito con lo strumento host del servizio WCF di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="ce2b1-134">Per ulteriori informazioni sullo strumento host del servizio WCF, vedere [host del servizio WCF (WcfSvcHost. exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ce2b1-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="ce2b1-135">Se Visual Studio è stato installato con Visual Basic impostazioni dell'ambiente di sviluppo, la soluzione potrebbe essere nascosta.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="ce2b1-136">In tal caso, scegliere **Opzioni** dal menu **strumenti** , quindi scegliere **progetti e soluzioni** > **generale** nella finestra **Opzioni** .</span><span class="sxs-lookup"><span data-stu-id="ce2b1-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="ce2b1-137">Selezionare **Mostra sempre soluzione**.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-137">Select **Always show solution**.</span></span> <span data-ttu-id="ce2b1-138">Inoltre, verificare che l'opzione **Salva nuovi progetti al momento della creazione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="ce2b1-139">Da **Esplora soluzioni**aprire il file **IService1.cs** o **IService1. vb** e sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="ce2b1-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="ce2b1-140">Questo contratto definisce una calcolatrice online.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-140">This contract defines an online calculator.</span></span> <span data-ttu-id="ce2b1-141">Si noti `ICalculator` che l'interfaccia è contrassegnata con l' <xref:System.ServiceModel.ServiceContractAttribute> attributo `ServiceContract`(semplificato come).</span><span class="sxs-lookup"><span data-stu-id="ce2b1-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="ce2b1-142">Questo attributo definisce uno spazio dei nomi per evitare ambiguità nel nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="ce2b1-143">Il codice contrassegna ogni operazione del calcolatore con <xref:System.ServiceModel.OperationContractAttribute> l'attributo (semplificato come `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="ce2b1-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce2b1-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ce2b1-144">Next steps</span></span>

<span data-ttu-id="ce2b1-145">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="ce2b1-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ce2b1-146">Creare un progetto libreria di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="ce2b1-147">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-147">Define a service contract interface.</span></span>

<span data-ttu-id="ce2b1-148">Passare all'esercitazione successiva per apprendere come implementare il contratto di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="ce2b1-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ce2b1-149">Esercitazione: Implementare un contratto di servizio WCF</span><span class="sxs-lookup"><span data-stu-id="ce2b1-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
