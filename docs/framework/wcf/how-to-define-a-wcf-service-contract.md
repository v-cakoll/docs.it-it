---
title: 'Procedura: definire un contratto di servizio di Windows Communication Foundation'
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 4f85a51c47eb045d1d2f0111cb217199c9acf0d7
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46537878"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="ecba4-102">Procedura: definire un contratto di servizio di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ecba4-102">How to: Define a Windows Communication Foundation Service Contract</span></span>

<span data-ttu-id="ecba4-103">Questa è la prima delle sei attività necessarie per creare un'applicazione Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ecba4-103">This is the first of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="ecba4-104">Per una panoramica di tutte e sei le attività, vedere l'argomento [Esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ecba4-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

 <span data-ttu-id="ecba4-105">Quando si crea un servizio WCF, la prima attività consiste nel definire un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ecba4-105">When creating a WCF service, the first task is to define a service contract.</span></span> <span data-ttu-id="ecba4-106">Nel contratto di servizio vengono specificate le operazioni supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ecba4-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="ecba4-107">Un'operazione può essere considerata un metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="ecba4-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="ecba4-108">I contratti vengono creati definendo un'interfaccia C++, C# o Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="ecba4-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="ecba4-109">Ogni metodo nell'interfaccia corrisponde a un'operazione del servizio specifica.</span><span class="sxs-lookup"><span data-stu-id="ecba4-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="ecba4-110">A ogni interfaccia deve essere applicato l'oggetto <xref:System.ServiceModel.ServiceContractAttribute> e a ogni operazione deve essere applicato l'attributo <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ecba4-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="ecba4-111">Se un metodo di un'interfaccia a cui è associato l'attributo <xref:System.ServiceModel.ServiceContractAttribute> non dispone dell'attributo <xref:System.ServiceModel.OperationContractAttribute>, tale metodo non viene esposto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="ecba4-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>

 <span data-ttu-id="ecba4-112">Nell'esempio riportato dopo la procedura, viene fornito il codice utilizzato per questa attività.</span><span class="sxs-lookup"><span data-stu-id="ecba4-112">The code used for this task is provided in the example following the procedure.</span></span>

## <a name="define-a-service-contract"></a><span data-ttu-id="ecba4-113">Definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="ecba4-113">Define a service contract</span></span>

1. <span data-ttu-id="ecba4-114">Aprire Visual Studio come amministratore facendo clic con il programma nel **avviare** dal menu e selezionando **ulteriori** > **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="ecba4-114">Open Visual Studio as an administrator by right-clicking the program in the **Start** menu and selecting **More** > **Run as administrator**.</span></span>

2. <span data-ttu-id="ecba4-115">Creare un progetto libreria di servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="ecba4-115">Create a WCF Service Library project.</span></span>

   1. <span data-ttu-id="ecba4-116">Scegliere **Nuovo** > **Progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="ecba4-116">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="ecba4-117">Nel **nuovo progetto** finestra di dialogo sul lato sinistro, espandere **Visual c#** oppure **Visual Basic**e quindi selezionare il **WCF** categoria.</span><span class="sxs-lookup"><span data-stu-id="ecba4-117">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="ecba4-118">Nella sezione centrale della finestra di dialogo viene visualizzato un elenco di modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="ecba4-118">A list of project templates is displayed in the center section of the dialog.</span></span> <span data-ttu-id="ecba4-119">Selezionare **WCF Service Library**.</span><span class="sxs-lookup"><span data-stu-id="ecba4-119">Select **WCF Service Library**.</span></span>

   3. <span data-ttu-id="ecba4-120">Immettere `GettingStartedLib` nella **Name** nella casella di testo e `GettingStarted` nel **Nome soluzione** nella casella di testo nella parte inferiore della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="ecba4-120">Enter `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ecba4-121">Se non viene visualizzato il **WCF** categoria di modelli di progetto, potrebbe essere necessario installare il **Windows Communication Foundation** componente di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ecba4-121">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="ecba4-122">Nel **nuovo progetto** finestra di dialogo, scegliere il collegamento con la dicitura **aperto Visual Studio Installer**.</span><span class="sxs-lookup"><span data-stu-id="ecba4-122">In the **New Project** dialog box, click the link that says **Open Visual Studio Installer**.</span></span> <span data-ttu-id="ecba4-123">Selezionare il **singoli componenti** scheda e quindi cercare e selezionare **Windows Communication Foundation** sotto il **le attività di sviluppo** categoria.</span><span class="sxs-lookup"><span data-stu-id="ecba4-123">Select the **Individual Components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="ecba4-124">Scegli **Modify** per iniziare a installare il componente.</span><span class="sxs-lookup"><span data-stu-id="ecba4-124">Choose **Modify** to begin installing the component.</span></span>

   <span data-ttu-id="ecba4-125">Visual Studio crea il progetto che contiene 3 file: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) e App. config. Il file IService1 contiene un contratto di servizio predefinito.</span><span class="sxs-lookup"><span data-stu-id="ecba4-125">Visual Studio creates the project, which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config. The IService1 file contains a default service contract.</span></span> <span data-ttu-id="ecba4-126">Il file Service1 contiene un'implementazione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="ecba4-126">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="ecba4-127">Il file App.config contiene la configurazione necessaria per caricare il servizio predefinito con l'host del servizio WCF di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ecba4-127">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="ecba4-128">Per altre informazioni sullo strumento Host del servizio WCF, vedere [Host del servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="ecba4-128">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>

3. <span data-ttu-id="ecba4-129">Aprire il file IService1.cs o IService1.vb ed eliminare il codice all'interno della dichiarazione dello spazio dei nomi, lasciando la dichiarazione dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="ecba4-129">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration, leaving the namespace declaration.</span></span> <span data-ttu-id="ecba4-130">All'interno della dichiarazione dello spazio dei nomi definire una nuova interfaccia denominata `ICalculator`, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="ecba4-130">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>

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

     <span data-ttu-id="ecba4-131">Questo contratto definisce una calcolatrice online.</span><span class="sxs-lookup"><span data-stu-id="ecba4-131">This contract defines an online calculator.</span></span> <span data-ttu-id="ecba4-132">Si noti che l'interfaccia `ICalculator` è contrassegnata con l'attributo <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ecba4-132">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="ecba4-133">Questo attributo definisce uno spazio dei nomi utilizzato per evitare ambiguità nel nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="ecba4-133">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="ecba4-134">Ogni operazione della calcolatrice è contrassegnata con l'attributo <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ecba4-134">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ecba4-135">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="ecba4-135">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ecba4-136">Procedura: implementare un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="ecba4-136">How to: Implement a service contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a><span data-ttu-id="ecba4-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecba4-137">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="ecba4-138">Procedura: Implementare un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="ecba4-138">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="ecba4-139">Introduzione</span><span class="sxs-lookup"><span data-stu-id="ecba4-139">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="ecba4-140">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="ecba4-140">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)