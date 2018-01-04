---
title: 'Procedura: scrivere servizi a livello di codice'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: cdb9c7bba564b71bfba86076218e48610cf73076
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="091b6-102">Procedura: scrivere servizi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="091b6-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="091b6-103">Se si sceglie di non utilizzare il modello di progetto di servizio Windows, è possibile scrivere i propri servizi impostando l'ereditarietà e altri elementi dell'infrastruttura manualmente.</span><span class="sxs-lookup"><span data-stu-id="091b6-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="091b6-104">Quando si crea un servizio a livello di codice, è necessario eseguire diversi passaggi gestiti automaticamente il modello:</span><span class="sxs-lookup"><span data-stu-id="091b6-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
-   <span data-ttu-id="091b6-105">È necessario impostare la classe di servizio da cui ereditare la <xref:System.ServiceProcess.ServiceBase> classe.</span><span class="sxs-lookup"><span data-stu-id="091b6-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="091b6-106">È necessario creare un `Main` metodo per il progetto di servizio che definisce i servizi da eseguire e chiama il <xref:System.ServiceProcess.ServiceBase.Run%2A> metodo su di essi.</span><span class="sxs-lookup"><span data-stu-id="091b6-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
-   <span data-ttu-id="091b6-107">È necessario eseguire l'override di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedure e scrivere il codice desiderato per l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="091b6-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="091b6-108">Scrivere un servizio a livello di codice</span><span class="sxs-lookup"><span data-stu-id="091b6-108">To write a service programmatically</span></span>  
  
1.  <span data-ttu-id="091b6-109">Creare un progetto vuoto e creare un riferimento agli spazi dei nomi necessari attenendosi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="091b6-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1.  <span data-ttu-id="091b6-110">In **Esplora**, fare doppio clic su di **riferimenti** nodo e fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="091b6-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="091b6-111">Nel **.NET Framework** scheda, scorrere fino a **System.dll** e fare clic su **selezionare**.</span><span class="sxs-lookup"><span data-stu-id="091b6-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3.  <span data-ttu-id="091b6-112">Scorrere fino a **System.ServiceProcess.dll** e fare clic su **selezionare**.</span><span class="sxs-lookup"><span data-stu-id="091b6-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4.  <span data-ttu-id="091b6-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="091b6-113">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="091b6-114">Aggiungere una classe e configurarlo in modo da ereditare <xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="091b6-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  <span data-ttu-id="091b6-115">Aggiungere il codice seguente per configurare la classe di servizio:</span><span class="sxs-lookup"><span data-stu-id="091b6-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  <span data-ttu-id="091b6-116">Creare un `Main` metodo per la classe e che consente di definire il servizio verrà contenuto la classe. `userService1` è il nome della classe:</span><span class="sxs-lookup"><span data-stu-id="091b6-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <span data-ttu-id="091b6-117">Eseguire l'override di <xref:System.ServiceProcess.ServiceBase.OnStart%2A> (metodo) e definire i processi da eseguire quando viene avviato il servizio.</span><span class="sxs-lookup"><span data-stu-id="091b6-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  <span data-ttu-id="091b6-118">Eseguire l'override di qualsiasi altro metodo che si desidera definire l'elaborazione per personalizzata e scrivere codice per determinare le azioni che il servizio deve intraprendere in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="091b6-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7.  <span data-ttu-id="091b6-119">Aggiungere i programmi di installazione necessari per l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="091b6-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="091b6-120">Per ulteriori informazioni, vedere [procedura: aggiungere programmi di installazione per l'applicazione di servizio](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="091b6-120">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
8.  <span data-ttu-id="091b6-121">Compilare il progetto selezionando **Compila soluzione** dal **compilare** menu.</span><span class="sxs-lookup"><span data-stu-id="091b6-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="091b6-122">Non è possibile eseguire un progetto di servizio premendo F5.</span><span class="sxs-lookup"><span data-stu-id="091b6-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="091b6-123">Creare un progetto di installazione e le azioni personalizzate per installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="091b6-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="091b6-124">Per un esempio, vedere [procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="091b6-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="091b6-125">Installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="091b6-125">Install the service.</span></span> <span data-ttu-id="091b6-126">Per altre informazioni, vedere [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="091b6-126">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="091b6-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="091b6-127">See Also</span></span>  
 [<span data-ttu-id="091b6-128">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="091b6-128">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="091b6-129">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="091b6-129">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="091b6-130">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="091b6-130">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="091b6-131">Procedura: registrare informazioni sui servizi</span><span class="sxs-lookup"><span data-stu-id="091b6-131">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="091b6-132">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="091b6-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
