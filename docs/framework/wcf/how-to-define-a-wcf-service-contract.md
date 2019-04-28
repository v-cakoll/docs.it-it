---
title: 'Esercitazione: Definire un contratto di servizio Windows Communication Foundation'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929350"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="4d90c-102">Esercitazione: Definire un contratto di servizio Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="4d90c-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="4d90c-103">Questa esercitazione illustra il primo di cinque attività necessarie per creare un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4d90c-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4d90c-104">Per una panoramica delle esercitazioni, vedere [esercitazione: Iniziare con le applicazioni di Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="4d90c-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="4d90c-105">Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="4d90c-106">Nel contratto di servizio vengono specificate le operazioni supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="4d90c-107">Un'operazione può essere considerata un metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="4d90c-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="4d90c-108">Per creare i contratti di servizio necessario definire un oggetto visivo C# o l'interfaccia di Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="4d90c-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="4d90c-109">Un'interfaccia presenta le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d90c-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="4d90c-110">Ogni metodo nell'interfaccia corrisponde a un'operazione del servizio specifica.</span><span class="sxs-lookup"><span data-stu-id="4d90c-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="4d90c-111">Per ogni interfaccia, è necessario applicare il <xref:System.ServiceModel.ServiceContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="4d90c-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="4d90c-112">Per ogni operazione o metodo, è necessario applicare il <xref:System.ServiceModel.OperationContractAttribute> attributo.</span><span class="sxs-lookup"><span data-stu-id="4d90c-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="4d90c-113">In questa esercitazione si imparerà a:</span><span class="sxs-lookup"><span data-stu-id="4d90c-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="4d90c-114">Creare un **WCF Service Library** progetto.</span><span class="sxs-lookup"><span data-stu-id="4d90c-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="4d90c-115">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="4d90c-116">Creare un progetto libreria di servizi WCF e definire un'interfaccia del contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="4d90c-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="4d90c-117">Aprire Visual Studio come amministratore.</span><span class="sxs-lookup"><span data-stu-id="4d90c-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="4d90c-118">A tale scopo, selezionare il programma in Visual Studio il **avviare** menu e quindi selezionare **ulteriori** > **Esegui come amministratore** dal menu di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="4d90c-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="4d90c-119">Creare un **WCF Service Library** progetto.</span><span class="sxs-lookup"><span data-stu-id="4d90c-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="4d90c-120">Scegliere **Nuovo** > **Progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="4d90c-121">Nel **nuovo progetto** finestra di dialogo sul lato sinistro, espandere **Visual c#** oppure **Visual Basic**e quindi selezionare il **WCF** categoria.</span><span class="sxs-lookup"><span data-stu-id="4d90c-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="4d90c-122">Visual Studio visualizza un elenco di modelli di progetto nella sezione centrale della finestra.</span><span class="sxs-lookup"><span data-stu-id="4d90c-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="4d90c-123">Selezionare **WCF Service Library**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="4d90c-124">Se non viene visualizzato il **WCF** categoria di modelli di progetto, potrebbe essere necessario installare il **Windows Communication Foundation** componente di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="4d90c-125">Nel **nuovo progetto** finestra di dialogo, seleziona la **aperto Visual Studio Installer** collegamento sul lato sinistro.</span><span class="sxs-lookup"><span data-stu-id="4d90c-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="4d90c-126">Selezionare il **singoli componenti** scheda e quindi cercare e selezionare **Windows Communication Foundation** sotto il **le attività di sviluppo** categoria.</span><span class="sxs-lookup"><span data-stu-id="4d90c-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="4d90c-127">Scegli **Modify** per iniziare a installare il componente.</span><span class="sxs-lookup"><span data-stu-id="4d90c-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="4d90c-128">Nella parte inferiore della finestra, immettere *GettingStartedLib* per il **Name** e *GettingStarted* per il **Nome soluzione**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="4d90c-129">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-129">Select **OK**.</span></span>

      <span data-ttu-id="4d90c-130">Visual Studio crea il progetto che dispone di tre file: *IService1.cs* (o *IService1.vb* per un progetto Visual Basic), *Service1.cs* (o *Service1.vb* per un progetto Visual Basic), e  *App. config*. Visual Studio definisce questi file come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4d90c-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="4d90c-131">Il *IService1* file contiene la definizione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="4d90c-132">Il *Service1* file contiene l'implementazione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="4d90c-133">Il *app. config* file contiene le informazioni di configurazione necessarie per caricare il servizio predefinito con lo strumento Host del servizio WCF di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="4d90c-134">Per altre informazioni sullo strumento Host del servizio WCF, vedere [Host del servizio WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4d90c-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="4d90c-135">Se è installato Visual Studio con le impostazioni di ambiente per gli sviluppatori Visual Basic, la soluzione potrebbe essere nascosta.</span><span class="sxs-lookup"><span data-stu-id="4d90c-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="4d90c-136">In questo caso, selezionare **opzioni** dal **Tools** menu, quindi selezionare **progetti e soluzioni** > **generale** in il **opzioni** finestra.</span><span class="sxs-lookup"><span data-stu-id="4d90c-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="4d90c-137">Selezionare **Mostra sempre soluzione**.</span><span class="sxs-lookup"><span data-stu-id="4d90c-137">Select **Always show solution**.</span></span> <span data-ttu-id="4d90c-138">Inoltre, verificare che **Salva nuovi progetti alla creazione** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="4d90c-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="4d90c-139">Dal **Esplora soluzioni**, aprire il **IService1.cs** oppure **IService1.vb** file e sostituire il codice con il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="4d90c-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="4d90c-140">Questo contratto definisce una calcolatrice online.</span><span class="sxs-lookup"><span data-stu-id="4d90c-140">This contract defines an online calculator.</span></span> <span data-ttu-id="4d90c-141">Si noti che il `ICalculator` interfaccia è contrassegnata con il <xref:System.ServiceModel.ServiceContractAttribute> attributo (semplificata come `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="4d90c-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="4d90c-142">Questo attributo definisce uno spazio dei nomi per evitare ambiguità tra il nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="4d90c-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="4d90c-143">Il codice contrassegna ogni operazione della calcolatrice con il <xref:System.ServiceModel.OperationContractAttribute> attributo (semplificata come `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="4d90c-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d90c-144">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4d90c-144">Next steps</span></span>

<span data-ttu-id="4d90c-145">In questa esercitazione si è appreso come:</span><span class="sxs-lookup"><span data-stu-id="4d90c-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="4d90c-146">Creare un progetto libreria di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="4d90c-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="4d90c-147">Definire un'interfaccia del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="4d90c-147">Define a service contract interface.</span></span>

<span data-ttu-id="4d90c-148">Passare all'esercitazione successiva per informazioni su come implementare il contratto di servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="4d90c-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4d90c-149">Esercitazione: Implementare un contratto di servizio WCF</span><span class="sxs-lookup"><span data-stu-id="4d90c-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
