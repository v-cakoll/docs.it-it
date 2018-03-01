---
title: 'Procedura: definire un contratto di servizio di Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c69f79d8629acee80a2e59346032e7733ec37dea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="b8670-102">Procedura: definire un contratto di servizio di Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b8670-102">How to: Define a Windows Communication Foundation Service Contract</span></span>
<span data-ttu-id="b8670-103">Questa è la prima delle sei attività necessarie per creare un'applicazione [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] di base.</span><span class="sxs-lookup"><span data-stu-id="b8670-103">This is the first of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="b8670-104">Per una panoramica di tutte e sei le attività, vedere il [esercitazione introduttiva](../../../docs/framework/wcf/getting-started-tutorial.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="b8670-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="b8670-105">Quando si crea un servizio di [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], la prima attività consiste nel definire un contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="b8670-105">When creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service, the first task is to define a service contract.</span></span> <span data-ttu-id="b8670-106">Nel contratto di servizio vengono specificate le operazioni supportate dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b8670-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="b8670-107">Un'operazione può essere considerata un metodo del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="b8670-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="b8670-108">I contratti vengono creati definendo un'interfaccia C++, C# o Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="b8670-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="b8670-109">Ogni metodo nell'interfaccia corrisponde a un'operazione del servizio specifica.</span><span class="sxs-lookup"><span data-stu-id="b8670-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="b8670-110">A ogni interfaccia deve essere applicato l'oggetto <xref:System.ServiceModel.ServiceContractAttribute> e a ogni operazione deve essere applicato l'attributo <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8670-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="b8670-111">Se un metodo di un'interfaccia a cui è associato l'attributo <xref:System.ServiceModel.ServiceContractAttribute> non dispone dell'attributo <xref:System.ServiceModel.OperationContractAttribute>, tale metodo non viene esposto dal servizio.</span><span class="sxs-lookup"><span data-stu-id="b8670-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>  
  
 <span data-ttu-id="b8670-112">Nell'esempio riportato dopo la procedura, viene fornito il codice utilizzato per questa attività.</span><span class="sxs-lookup"><span data-stu-id="b8670-112">The code used for this task is provided in the example following the procedure.</span></span>  
  
### <a name="to-define-a-service-contract"></a><span data-ttu-id="b8670-113">Per definire un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="b8670-113">To define a service contract</span></span>  
  
1.  <span data-ttu-id="b8670-114">Aprire [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] come amministratore facendo clic con il programma di **avviare** menu e selezionando **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="b8670-114">Open  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as an administrator by right-clicking the program in the **Start** menu and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="b8670-115">Creare un progetto libreria di servizi WCF facendo il **File** menu e selezionando **New**, **progetto**.</span><span class="sxs-lookup"><span data-stu-id="b8670-115">Create a WCF Service Library project by clicking the **File** menu and selecting **New**, **Project**.</span></span> <span data-ttu-id="b8670-116">Nel **nuovo progetto** finestra di dialogo, sul lato sinistro della finestra di dialogo espandere **Visual c#** per un progetto c# o **altri linguaggi** e quindi **diVisualBasic** per un progetto di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b8670-116">In the **New Project** dialog, on the left-hand side of the dialog expand **Visual C#** for a C# project or **Other Languages** and then **Visual Basic** for a Visual Basic project.</span></span> <span data-ttu-id="b8670-117">Selezionare la lingua selezionata **WCF** e verrà visualizzato un elenco di modelli di progetto nella sezione centrale della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b8670-117">Under the language selected select **WCF** and a list of project templates will be displayed on the center section of the dialog.</span></span> <span data-ttu-id="b8670-118">Selezionare **libreria di servizi WCF**e il tipo `GettingStartedLib` nel **nome** casella di testo e `GettingStarted` nel **Nome soluzione** casella di testo nella parte inferiore della finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="b8670-118">Select **WCF Service Library**, and type `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>  
  
3.  <span data-ttu-id="b8670-119">Visual Studio creerà il progetto che contiene 3 file: IService1.cs (o IService1.vb), Service1.cs (o Service1.vb) e App.config.  Il file IService1 contiene un contratto di servizio predefinito.</span><span class="sxs-lookup"><span data-stu-id="b8670-119">Visual Studio will create the project which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config.  The IService1 file contains a default service contract.</span></span>  <span data-ttu-id="b8670-120">Il file Service1 contiene un'implementazione predefinita del contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="b8670-120">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="b8670-121">Il file App.config contiene la configurazione necessaria per caricare il servizio predefinito con l'host del servizio WCF di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b8670-121">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="b8670-122">Per ulteriori informazioni sullo strumento di Host servizio WCF, vedere [Host servizio WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="b8670-122">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>  
  
4.  <span data-ttu-id="b8670-123">Aprire il file IService1.cs o IService1.vb ed eliminare il codice all'interno della dichiarazione dello spazio dei nomi mantenendo però quest'ultima.</span><span class="sxs-lookup"><span data-stu-id="b8670-123">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration leaving the namespace declaration.</span></span> <span data-ttu-id="b8670-124">All'interno della dichiarazione dello spazio dei nomi definire una nuova interfaccia denominata `ICalculator`, come mostrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="b8670-124">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
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
  
    ```  
    ‘IService.vb  
    Imports System  
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
  
     <span data-ttu-id="b8670-125">Questo contratto definisce una calcolatrice online.</span><span class="sxs-lookup"><span data-stu-id="b8670-125">This contract defines an online calculator.</span></span> <span data-ttu-id="b8670-126">Si noti che l'interfaccia `ICalculator` è contrassegnata con l'attributo <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8670-126">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="b8670-127">Questo attributo definisce uno spazio dei nomi utilizzato per evitare ambiguità nel nome del contratto.</span><span class="sxs-lookup"><span data-stu-id="b8670-127">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="b8670-128">Ogni operazione della calcolatrice è contrassegnata con l'attributo <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b8670-128">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b8670-129">Quando vengono utilizzati attributi per annotare un'interfaccia, un membro o una classe, è possibile eliminare la parte "Attribute" dal nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="b8670-129">When using attributes to annotate an interface, member, or class, you can drop the "Attribute" part from the attribute name.</span></span> <span data-ttu-id="b8670-130">In questo modo <xref:System.ServiceModel.ServiceContractAttribute> diventa `[ServiceContract]` in C# o `<ServiceContract>` in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b8670-130">So <xref:System.ServiceModel.ServiceContractAttribute> becomes `[ServiceContract]` in C#, or `<ServiceContract>` in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8670-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b8670-131">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="b8670-132">Procedura: Implementare un contratto di servizio</span><span class="sxs-lookup"><span data-stu-id="b8670-132">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="b8670-133">Introduzione</span><span class="sxs-lookup"><span data-stu-id="b8670-133">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="b8670-134">Servizio indipendente</span><span class="sxs-lookup"><span data-stu-id="b8670-134">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
