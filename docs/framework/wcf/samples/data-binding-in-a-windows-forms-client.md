---
title: data binding in un client Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b78cfbd63687fc7288c945ebcbec790150efed61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="data-binding-in-a-windows-forms-client"></a><span data-ttu-id="48b7a-102">data binding in un client Windows Form</span><span class="sxs-lookup"><span data-stu-id="48b7a-102">Data Binding in a Windows Forms Client</span></span>
<span data-ttu-id="48b7a-103">In questo esempio viene illustrata l'associazione a dati restituiti da un servizio di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]  in un'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="48b7a-103">This sample demonstrates how to bind to data returned by a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service in a Windows Forms application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48b7a-104">La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="48b7a-104">The setup procedure and build instructions for this sample are located at the end of this article.</span></span>  
  
 <span data-ttu-id="48b7a-105">In questo esempio viene illustrato un servizio che implementa un contratto in cui viene definito un modello di comunicazione request/reply.</span><span class="sxs-lookup"><span data-stu-id="48b7a-105">This sample demonstrates a service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="48b7a-106">L'esempio è costituito da un'applicazione Windows Form client (.exe) e da un servizio di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ospitato su Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="48b7a-106">The sample consists of a client Windows Forms application (.exe) and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="48b7a-107">Il contratto viene definito mediante l'interfaccia `IWeatherService`, che espone un'operazione denominata `GetWeatherData`.</span><span class="sxs-lookup"><span data-stu-id="48b7a-107">The contract is defined by the `IWeatherService` interface, which exposes an operation named `GetWeatherData`.</span></span> <span data-ttu-id="48b7a-108">Questa operazione accetta una matrice di città e restituisce una matrice di oggetti `WeatherData` che rappresentano la temperatura massima e minima prevista per una città.</span><span class="sxs-lookup"><span data-stu-id="48b7a-108">This operation accepts an array of cities and returns an array of `WeatherData` objects that represent the high and low forecasted temperature for a city.</span></span>  
  
 <span data-ttu-id="48b7a-109">L'associazione di dati si verifica sul client dell'applicazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="48b7a-109">The data binding occurs on the client in the Windows Forms application.</span></span> <span data-ttu-id="48b7a-110">Nella finestra di progettazione Windows Form viene definito un elemento `DataGridView`, che costituisce una rappresentazione grafica dei dati.</span><span class="sxs-lookup"><span data-stu-id="48b7a-110">A `DataGridView` is defined in the Windows Forms designer, which is a graphical representation of the data.</span></span> <span data-ttu-id="48b7a-111">Viene creato anche un intermediario denominato `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="48b7a-111">An intermediary named `BindingSource` is also created.</span></span> <span data-ttu-id="48b7a-112">L'origine dati di `BindingSource` è impostata sulla matrice dei dati restituita dal servizio.</span><span class="sxs-lookup"><span data-stu-id="48b7a-112">The data source of `BindingSource` is set to the data array returned by the service.</span></span> <span data-ttu-id="48b7a-113">Lo scopo dell'elemento `BindingSource` consiste nel fornire un livello di riferimento indiretto tra i dati e la visualizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="48b7a-113">The purpose of the `BindingSource` is to provide a layer of indirection between the data and the data view.</span></span> <span data-ttu-id="48b7a-114">Tutte le interazioni con i dati, ad esempio l'esplorazione, l'ordinamento, il filtro e l'aggiornamento, vengono eseguite mediante chiamate al componente `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="48b7a-114">All interaction with the data, such as navigating, sorting, filtering, and updating, is accomplished with calls to the `BindingSource` component.</span></span> <span data-ttu-id="48b7a-115">Per eseguire l'associazione di dati all'oggetto `DataGridView`, l'elemento `datasource` di  `DataGridView` viene impostato sull'oggetto `BindingSource`.</span><span class="sxs-lookup"><span data-stu-id="48b7a-115">To accomplish data binding to the `DataGridView`, the `datasource` of the `DataGridView` is then set to the `BindingSource` object.</span></span> <span data-ttu-id="48b7a-116">Tutti i dati restituiti dal servizio di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono visualizzati graficamente dall'utente.</span><span class="sxs-lookup"><span data-stu-id="48b7a-116">All of the data returned from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is then displayed graphically to the user.</span></span>  <span data-ttu-id="48b7a-117">Ogni volta che l'utente fa clic sul pulsante, i dati restituiti vengono automaticamente aggiornati nell'oggetto `DataGridView` associato a dati.</span><span class="sxs-lookup"><span data-stu-id="48b7a-117">Every time the user clicks the button, the returned data is automatically updated in the data-bound `DataGridView`.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="48b7a-118">Per impostare, compilare ed eseguire l'esempio</span><span class="sxs-lookup"><span data-stu-id="48b7a-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="48b7a-119">Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="48b7a-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="48b7a-120">Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="48b7a-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="48b7a-121">Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="48b7a-121">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="48b7a-122">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="48b7a-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="48b7a-123">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="48b7a-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="48b7a-124">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="48b7a-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="48b7a-125">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="48b7a-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a><span data-ttu-id="48b7a-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48b7a-126">See Also</span></span>
