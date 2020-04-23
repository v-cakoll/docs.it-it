---
title: 'Procedura: scrivere servizi a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 5637d569ad5261bff6865af4ab2ed8b7631d2d38
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053555"
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="33bd5-102">Procedura: scrivere servizi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="33bd5-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="33bd5-103">Se si sceglie di non usare il modello di progetto Servizio Windows, è possibile scrivere servizi personalizzati impostando manualmente l'ereditarietà e altri elementi di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="33bd5-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="33bd5-104">Quando si crea un servizio a livello di codice, è necessario eseguire diversi passaggi che altrimenti vengono gestiti automaticamente dal modello:</span><span class="sxs-lookup"><span data-stu-id="33bd5-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
- <span data-ttu-id="33bd5-105">È necessario impostare la classe del servizio in modo che erediti dalla classe <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="33bd5-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
- <span data-ttu-id="33bd5-106">È necessario creare un metodo `Main` per il progetto del servizio che definisce i servizi da eseguire e chiama il metodo <xref:System.ServiceProcess.ServiceBase.Run%2A> su di essi.</span><span class="sxs-lookup"><span data-stu-id="33bd5-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
- <span data-ttu-id="33bd5-107">È necessario eseguire l'override delle procedure <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> e scrivere l'eventuale codice che si vuole eseguire con tali procedure.</span><span class="sxs-lookup"><span data-stu-id="33bd5-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="33bd5-108">Per scrivere un servizio a livello di codice</span><span class="sxs-lookup"><span data-stu-id="33bd5-108">To write a service programmatically</span></span>  
  
1. <span data-ttu-id="33bd5-109">Creare un progetto vuoto e creare un riferimento agli spazi dei nomi necessari seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="33bd5-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1. <span data-ttu-id="33bd5-110">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="33bd5-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2. <span data-ttu-id="33bd5-111">Nella scheda **.NET Framework** scorrere fino a **System.dll** e fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="33bd5-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3. <span data-ttu-id="33bd5-112">Scorrere fino a **System.ServiceProcess.dll** e fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="33bd5-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4. <span data-ttu-id="33bd5-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="33bd5-113">Click **OK**.</span></span>  
  
2. <span data-ttu-id="33bd5-114">Aggiungere una classe e configurarla in modo che erediti da <xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="33bd5-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3. <span data-ttu-id="33bd5-115">Aggiungere il codice seguente per configurare la classe di servizio:</span><span class="sxs-lookup"><span data-stu-id="33bd5-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4. <span data-ttu-id="33bd5-116">Creare un metodo `Main` per la classe e usarlo per definire il servizio che verrà incluso nella classe. `userService1` è il nome della classe:</span><span class="sxs-lookup"><span data-stu-id="33bd5-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5. <span data-ttu-id="33bd5-117">Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e definire l'elaborazione da eseguire eventualmente all'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="33bd5-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6. <span data-ttu-id="33bd5-118">Eseguire l'override di qualsiasi altro metodo per cui si vuole definire un'elaborazione personalizzata e scrivere il codice per determinare le azioni che il servizio deve eseguire in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="33bd5-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7. <span data-ttu-id="33bd5-119">Aggiungere i programmi di installazione necessari per l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="33bd5-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="33bd5-120">Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="33bd5-120">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
8. <span data-ttu-id="33bd5-121">Compilare il progetto scegliendo **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="33bd5-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="33bd5-122">Non è possibile eseguire un progetto di servizio premendo F5.</span><span class="sxs-lookup"><span data-stu-id="33bd5-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="33bd5-123">Creare un progetto per il programma di installazione e le azioni personalizzate per installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="33bd5-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="33bd5-124">Per un esempio, vedere [Procedura dettagliata: Creazione di un'applicazione di servizio Windows in Progettazione componenti](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="33bd5-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="33bd5-125">Installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="33bd5-125">Install the service.</span></span> <span data-ttu-id="33bd5-126">Per altre informazioni, vedere [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="33bd5-126">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bd5-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33bd5-127">See also</span></span>

- [<span data-ttu-id="33bd5-128">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="33bd5-128">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="33bd5-129">Procedura: creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="33bd5-129">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="33bd5-130">Procedura: aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="33bd5-130">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="33bd5-131">Procedura: registrare informazioni sui servizi</span><span class="sxs-lookup"><span data-stu-id="33bd5-131">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="33bd5-132">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="33bd5-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
