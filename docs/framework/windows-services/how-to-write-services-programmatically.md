---
title: 'Procedura: Scrivere servizi a livello di codice'
description: Vedere come scrivere servizi a livello di codice configurando l'ereditarietà e altri elementi dell'infrastruttura.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
ms.openlocfilehash: 9693e3d387f38319519ab04211d8219fe1e5dda1
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925709"
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="e3576-103">Procedura: Scrivere servizi a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e3576-103">How to: Write Services Programmatically</span></span>
<span data-ttu-id="e3576-104">Se si sceglie di non usare il modello di progetto Servizio Windows, è possibile scrivere servizi personalizzati impostando manualmente l'ereditarietà e altri elementi di infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="e3576-104">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="e3576-105">Quando si crea un servizio a livello di codice, è necessario eseguire diversi passaggi che altrimenti vengono gestiti automaticamente dal modello:</span><span class="sxs-lookup"><span data-stu-id="e3576-105">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
- <span data-ttu-id="e3576-106">È necessario impostare la classe del servizio in modo che erediti dalla classe <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="e3576-106">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
- <span data-ttu-id="e3576-107">È necessario creare un metodo `Main` per il progetto del servizio che definisce i servizi da eseguire e chiama il metodo <xref:System.ServiceProcess.ServiceBase.Run%2A> su di essi.</span><span class="sxs-lookup"><span data-stu-id="e3576-107">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
- <span data-ttu-id="e3576-108">È necessario eseguire l'override delle procedure <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e <xref:System.ServiceProcess.ServiceBase.OnStop%2A> e scrivere l'eventuale codice che si vuole eseguire con tali procedure.</span><span class="sxs-lookup"><span data-stu-id="e3576-108">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="e3576-109">Per scrivere un servizio a livello di codice</span><span class="sxs-lookup"><span data-stu-id="e3576-109">To write a service programmatically</span></span>  
  
1. <span data-ttu-id="e3576-110">Creare un progetto vuoto e creare un riferimento agli spazi dei nomi necessari seguendo questa procedura:</span><span class="sxs-lookup"><span data-stu-id="e3576-110">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1. <span data-ttu-id="e3576-111">In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** e scegliere **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="e3576-111">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2. <span data-ttu-id="e3576-112">Nella scheda **.NET Framework** scorrere fino a **System.dll** e fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="e3576-112">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3. <span data-ttu-id="e3576-113">Scorrere fino a **System.ServiceProcess.dll** e fare clic su **Seleziona**.</span><span class="sxs-lookup"><span data-stu-id="e3576-113">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4. <span data-ttu-id="e3576-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="e3576-114">Click **OK**.</span></span>  
  
2. <span data-ttu-id="e3576-115">Aggiungere una classe e configurarla in modo che erediti da <xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="e3576-115">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3. <span data-ttu-id="e3576-116">Aggiungere il codice seguente per configurare la classe di servizio:</span><span class="sxs-lookup"><span data-stu-id="e3576-116">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4. <span data-ttu-id="e3576-117">Creare un metodo `Main` per la classe e usarlo per definire il servizio che verrà incluso nella classe. `userService1` è il nome della classe:</span><span class="sxs-lookup"><span data-stu-id="e3576-117">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5. <span data-ttu-id="e3576-118">Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%2A> e definire l'elaborazione da eseguire eventualmente all'avvio del servizio.</span><span class="sxs-lookup"><span data-stu-id="e3576-118">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6. <span data-ttu-id="e3576-119">Eseguire l'override di qualsiasi altro metodo per cui si vuole definire un'elaborazione personalizzata e scrivere il codice per determinare le azioni che il servizio deve eseguire in ogni caso.</span><span class="sxs-lookup"><span data-stu-id="e3576-119">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7. <span data-ttu-id="e3576-120">Aggiungere i programmi di installazione necessari per l'applicazione di servizio.</span><span class="sxs-lookup"><span data-stu-id="e3576-120">Add the necessary installers for your service application.</span></span> <span data-ttu-id="e3576-121">Per altre informazioni, vedere [Procedura: Aggiungere programmi di installazione all'applicazione di servizio](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="e3576-121">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
8. <span data-ttu-id="e3576-122">Compilare il progetto scegliendo **Compila soluzione** dal menu **Compila**.</span><span class="sxs-lookup"><span data-stu-id="e3576-122">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e3576-123">Non è possibile eseguire un progetto di servizio premendo F5.</span><span class="sxs-lookup"><span data-stu-id="e3576-123">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="e3576-124">Creare un progetto per il programma di installazione e le azioni personalizzate per installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e3576-124">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="e3576-125">Per un esempio, vedere [Procedura dettagliata: Creazione di un'applicazione di servizio Windows in Progettazione componenti](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e3576-125">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="e3576-126">Installare il servizio.</span><span class="sxs-lookup"><span data-stu-id="e3576-126">Install the service.</span></span> <span data-ttu-id="e3576-127">Per altre informazioni, vedere [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="e3576-127">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3576-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3576-128">See also</span></span>

- [<span data-ttu-id="e3576-129">Introduzione alle applicazioni di servizio Windows</span><span class="sxs-lookup"><span data-stu-id="e3576-129">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="e3576-130">Procedura: Creare servizi Windows</span><span class="sxs-lookup"><span data-stu-id="e3576-130">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="e3576-131">Procedura: Aggiungere programmi di installazione all'applicazione di servizio</span><span class="sxs-lookup"><span data-stu-id="e3576-131">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="e3576-132">Procedura: Registrare informazioni sui servizi</span><span class="sxs-lookup"><span data-stu-id="e3576-132">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="e3576-133">Procedura dettagliata: creazione di un'applicazione di servizio Windows in Progettazione componenti</span><span class="sxs-lookup"><span data-stu-id="e3576-133">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
