---
title: 'Esercitazione: Definire un contratto di servizio di Windows Communication FoundationTutorial: Define a Windows Communication Foundation service contract'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184089"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="9ec65-102">Esercitazione: Definire un contratto di servizio di Windows Communication FoundationTutorial: Define a Windows Communication Foundation service contract</span><span class="sxs-lookup"><span data-stu-id="9ec65-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="9ec65-103">Questa esercitazione descrive la prima delle cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF) di base.</span><span class="sxs-lookup"><span data-stu-id="9ec65-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="9ec65-104">Per una panoramica delle esercitazioni, vedere [Esercitazione: Introduzione alle applicazioni Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9ec65-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="9ec65-105">Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="9ec65-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="9ec65-106">Il contratto di servizio specifica le operazioni supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="9ec65-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="9ec65-107">Un'operazione può essere considerata un metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="9ec65-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="9ec65-108">È possibile creare contratti di servizio definendo un'interfaccia di C o Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="9ec65-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="9ec65-109">Un'interfaccia ha le seguenti caratteristiche:</span><span class="sxs-lookup"><span data-stu-id="9ec65-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="9ec65-110">Ogni metodo dell'interfaccia corrisponde a un'operazione di servizio specifico.</span><span class="sxs-lookup"><span data-stu-id="9ec65-110">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="9ec65-111">Per ogni interfaccia, è <xref:System.ServiceModel.ServiceContractAttribute> necessario applicare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9ec65-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="9ec65-112">Per ogni operazione/metodo, è <xref:System.ServiceModel.OperationContractAttribute> necessario applicare l'attributo.</span><span class="sxs-lookup"><span data-stu-id="9ec65-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="9ec65-113">In questa esercitazione verranno illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="9ec65-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="9ec65-114">Creare un progetto **libreria di servizi WCF.**</span><span class="sxs-lookup"><span data-stu-id="9ec65-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="9ec65-115">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="9ec65-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="9ec65-116">Creare un progetto di libreria di servizi WCF e definire un'interfaccia del contratto di servizioCreate a WCF Service Library project and define a service contract interface</span><span class="sxs-lookup"><span data-stu-id="9ec65-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="9ec65-117">Aprire Visual Studio come amministratore.</span><span class="sxs-lookup"><span data-stu-id="9ec65-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="9ec65-118">A tale scopo, selezionare il programma di Visual Studio nel menu **Start** e quindi selezionare **Altro** > **Esegui come amministratore** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="9ec65-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="9ec65-119">Creare un progetto **libreria di servizi WCF.**</span><span class="sxs-lookup"><span data-stu-id="9ec65-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="9ec65-120">Scegliere **Nuovo** > **Progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="9ec65-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="9ec65-121">Nella finestra di dialogo **Nuovo progetto,** sul lato sinistro, espandere **Visual C,** o **Visual Basic**, quindi selezionare la categoria **WCF.**</span><span class="sxs-lookup"><span data-stu-id="9ec65-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="9ec65-122">Visual Studio visualizza un elenco di modelli di progetto nella sezione centrale della finestra.</span><span class="sxs-lookup"><span data-stu-id="9ec65-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="9ec65-123">Selezionare **Libreria di servizi WCF**.</span><span class="sxs-lookup"><span data-stu-id="9ec65-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="9ec65-124">Se la categoria del modello di progetto WCF non è visualizzata, potrebbe essere necessario installare il componente Windows Communication Foundation di Visual Studio.If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9ec65-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="9ec65-125">Nella finestra di dialogo **Nuovo progetto** selezionare il collegamento Apri programma di installazione di **Visual Studio** sul lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="9ec65-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="9ec65-126">Selezionare la scheda **Singoli componenti,** quindi individuare e selezionare **Windows Communication Foundation** nella categoria Attività di **sviluppo.**</span><span class="sxs-lookup"><span data-stu-id="9ec65-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="9ec65-127">Scegliere **Modifica** per avviare l'installazione del componente.</span><span class="sxs-lookup"><span data-stu-id="9ec65-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="9ec65-128">Nella sezione inferiore della finestra immettere *GettingStartedLib* come **Nome** e *GettingStarted* come **Nome soluzione**.</span><span class="sxs-lookup"><span data-stu-id="9ec65-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="9ec65-129">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9ec65-129">Select **OK**.</span></span>

      <span data-ttu-id="9ec65-130">Visual Studio crea il progetto, che dispone di tre file: *IService1.cs* (o *IService1.vb* per un progetto Visual Basic), *Service1.cs* (o *Service1.vb* per un progetto Visual Basic) e *App.config*. Visual Studio definisce questi file come segue:Visual Studio defines these files as follows:</span><span class="sxs-lookup"><span data-stu-id="9ec65-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="9ec65-131">Il file *IService1* contiene la definizione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="9ec65-131">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="9ec65-132">Il file *Service1* contiene l'implementazione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="9ec65-132">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="9ec65-133">Il file App.config contiene le informazioni di configurazione necessarie per caricare il servizio predefinito con lo strumento Host del servizio WCF di Visual Studio.The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span><span class="sxs-lookup"><span data-stu-id="9ec65-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="9ec65-134">Per ulteriori informazioni sullo strumento Host servizio WCF, vedere [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9ec65-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="9ec65-135">Se è stato installato Visual Studio con le impostazioni dell'ambiente di sviluppo visual Basic, la soluzione potrebbe essere nascosta.</span><span class="sxs-lookup"><span data-stu-id="9ec65-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="9ec65-136">In questo caso, selezionare **Opzioni** dal menu **Strumenti,** quindi selezionare **Progetti e soluzioni** > **generali** nella finestra **Opzioni.**</span><span class="sxs-lookup"><span data-stu-id="9ec65-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="9ec65-137">Selezionare **Mostra sempre soluzione**.</span><span class="sxs-lookup"><span data-stu-id="9ec65-137">Select **Always show solution**.</span></span> <span data-ttu-id="9ec65-138">Verificare inoltre che **l'opzione Salva nuovi progetti al momento della creazione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="9ec65-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="9ec65-139">In **Esplora soluzioni**aprire il file **IService1.cs** o **IService1.vb** e sostituirne il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="9ec65-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="9ec65-140">Questo contratto definisce una calcolatrice online.</span><span class="sxs-lookup"><span data-stu-id="9ec65-140">This contract defines an online calculator.</span></span> <span data-ttu-id="9ec65-141">Si `ICalculator` noti che <xref:System.ServiceModel.ServiceContractAttribute> l'interfaccia `ServiceContract`è contrassegnata con l'attributo (semplificato come ).</span><span class="sxs-lookup"><span data-stu-id="9ec65-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="9ec65-142">Questo attributo definisce uno spazio dei nomi per evitare ambiguità nel nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="9ec65-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="9ec65-143">Il codice contrassegna ogni <xref:System.ServiceModel.OperationContractAttribute> operazione della `OperationContract`calcolatrice con l'attributo (semplificato come ).</span><span class="sxs-lookup"><span data-stu-id="9ec65-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ec65-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="9ec65-144">Next steps</span></span>

<span data-ttu-id="9ec65-145">In questa esercitazione sono state illustrate le procedure per:</span><span class="sxs-lookup"><span data-stu-id="9ec65-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="9ec65-146">Creare un progetto libreria di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="9ec65-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="9ec65-147">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="9ec65-147">Define a service contract interface.</span></span>

<span data-ttu-id="9ec65-148">Passare all'esercitazione successiva per informazioni su come implementare il contratto di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="9ec65-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="9ec65-149">Esercitazione: Implementare un contratto di servizio WCFTutorial: Implement a WCF service contract</span><span class="sxs-lookup"><span data-stu-id="9ec65-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
