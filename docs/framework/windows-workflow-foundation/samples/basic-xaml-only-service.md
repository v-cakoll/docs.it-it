---
title: Servizio solo XAML di base
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c106feb0-0245-43b5-aefe-93ce0e4d38eb
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 004a37682b855135998ef4620e673421f769326d
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2017
---
# <a name="basic-xaml-only-service"></a><span data-ttu-id="91550-102">Servizio solo XAML di base</span><span class="sxs-lookup"><span data-stu-id="91550-102">Basic XAML only Service</span></span>
<span data-ttu-id="91550-103">In questo esempio viene illustrato come creare un servizio solo XAML.</span><span class="sxs-lookup"><span data-stu-id="91550-103">This sample demonstrates how to create a XAML only service.</span></span> <span data-ttu-id="91550-104">Lo scenario è quello di un servizio di diagnostica per problemi correlati all'auto.</span><span class="sxs-lookup"><span data-stu-id="91550-104">The scenario is a diagnostics service for car-related problems.</span></span> <span data-ttu-id="91550-105">Il servizio viene implementato come flusso di lavoro che pone al client una serie di domande per diagnosticare il problema.</span><span class="sxs-lookup"><span data-stu-id="91550-105">The service is implemented as a workflow that asks the client a series of questions to diagnose the problem.</span></span> <span data-ttu-id="91550-106">Esistono due tipi di problema diagnosticabili dal servizio (l'auto non parte oppure l'aria condizionata non funziona).</span><span class="sxs-lookup"><span data-stu-id="91550-106">There are two types of issues the service can diagnose (car does not start or air conditioning not working).</span></span> <span data-ttu-id="91550-107">Il flusso di lavoro usa il modello Request/Reply della finestra di progettazione per esporre tre operazioni di servizio semplici.</span><span class="sxs-lookup"><span data-stu-id="91550-107">The workflow uses Request/Reply template from the designer to expose three simple service operations.</span></span> <span data-ttu-id="91550-108">Il servizio viene ospitato in IIS creando una directory virtuale in IIS e copiando i file service1.xamlx e Web.config nella directory virtuale. Non è richiesto alcun codice compilato.</span><span class="sxs-lookup"><span data-stu-id="91550-108">The service is hosted in IIS by creating a virtual directory in IIS and copying the service1.xamlx and Web.config files into the virtual directory, no compiled code is required.</span></span> <span data-ttu-id="91550-109">Per impostazione predefinita in questo esempio copierà automaticamente i file necessari nella directory virtuale creata quando si seguono le istruzioni di installazione per gli esempi di WCF e WF: [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) quando compilato in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="91550-109">By default this sample will automatically copy the needed files into the virtual directory created when you follow the setup instructions for the WCF and WF samples: [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) when built in Visual Studio 2010.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="91550-110">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="91550-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="91550-111">Caricare la soluzione del progetto in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] e compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="91550-111">Load the project solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] and build the project.</span></span>  
  
2.  <span data-ttu-id="91550-112">Eseguire l'applicazione client generata in [directory soluzione di base]\Client\bin\debug.</span><span class="sxs-lookup"><span data-stu-id="91550-112">Run the Client application generated in [solution base directory]\Client\bin\debug.</span></span>  
  
3.  <span data-ttu-id="91550-113">L'applicazione stampa le opzioni, ne seleziona una</span><span class="sxs-lookup"><span data-stu-id="91550-113">The application prints out options, selects an option.</span></span> <span data-ttu-id="91550-114">e pone alcune domande, rispondendo con sì o no (utilizzo di chiavi S/N).</span><span class="sxs-lookup"><span data-stu-id="91550-114">The application then asks some questions, answer them yes or no (using Y/N keys).</span></span> <span data-ttu-id="91550-115">Quando il servizio ha diagnosticato i problemi, l'applicazione stampa una diagnosi.</span><span class="sxs-lookup"><span data-stu-id="91550-115">When the service is done diagnosing the issues, the application prints out a diagnosis.</span></span>  
  
4.  <span data-ttu-id="91550-116">L'applicazione torna alle opzioni.</span><span class="sxs-lookup"><span data-stu-id="91550-116">The application goes back to the options.</span></span> <span data-ttu-id="91550-117">È possibile diagnosticare un altro problema o uscire dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="91550-117">You can diagnose another problem or exit the application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91550-118">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="91550-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="91550-119">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="91550-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="91550-120">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="91550-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="91550-121">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="91550-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLService`