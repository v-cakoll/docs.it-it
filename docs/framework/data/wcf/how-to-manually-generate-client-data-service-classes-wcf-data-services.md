---
title: 'Procedura: generare manualmente classi del servizio dati client (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dba117ac9f4fd7dc745019d9705c2a707a5b526c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="a46e9-102">Procedura: generare manualmente classi del servizio dati client (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="a46e9-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="a46e9-103">si integra con Visual Studio che consente di generare automaticamente le classi del servizio dati client quando si utilizza il **Aggiungi riferimento al servizio** la finestra di dialogo per aggiungere un riferimento a un servizio dati in un progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a46e9-103"> integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="a46e9-104">Per ulteriori informazioni, vedere [procedura: aggiungere un riferimento al servizio dati](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a46e9-104">For more information, see [How to: Add a Data Service Reference](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="a46e9-105">È inoltre possibile generare in modo manuale le stesse classi del servizio dati client utilizzando lo strumento per la generazione del codice, ovvero `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="a46e9-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="a46e9-106">Questo strumento, incluso con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], consente di generare classi di .NET Framework in base alla definizione del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="a46e9-106">This tool, which is included with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="a46e9-107">Può inoltre essere usato per generare classi del servizio dati in base al file del modello concettuale (CSDL) e al file con estensione edmx che rappresenta un modello di Entity Framework in un progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a46e9-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>  
  
 <span data-ttu-id="a46e9-108">Nell'esempio riportato in questo argomento vengono create le classi del servizio dati client in base al servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="a46e9-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="a46e9-109">Questo servizio viene creato quando si completa la [Guida rapida di WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="a46e9-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="a46e9-110">Per alcuni esempi inclusi in questo argomento è richiesto il file del modello concettuale per il modello Northwind.</span><span class="sxs-lookup"><span data-stu-id="a46e9-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="a46e9-111">Per ulteriori informazioni, vedere [procedura: utilizzare EdmGen.exe per generare il modello e i file di Mapping](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="a46e9-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="a46e9-112">Per alcuni esempi inclusi in questo argomento è richiesto il file con estensione edmx per il modello Northwind.</span><span class="sxs-lookup"><span data-stu-id="a46e9-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="a46e9-113">Per ulteriori informazioni, vedere [Cenni preliminari sui File edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span><span class="sxs-lookup"><span data-stu-id="a46e9-113">For more information, see [.edmx File Overview](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).</span></span>  
  
### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="a46e9-114">Per generare classi C# che supportano il data binding</span><span class="sxs-lookup"><span data-stu-id="a46e9-114">To generate C# classes that support data binding</span></span>  
  
-   <span data-ttu-id="a46e9-115">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a46e9-116">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="a46e9-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="a46e9-117">Per generare Visual Basic che supportano l'associazione dati</span><span class="sxs-lookup"><span data-stu-id="a46e9-117">To generate Visual Basic classes that support data binding</span></span>  
  
-   <span data-ttu-id="a46e9-118">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-118">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a46e9-119">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="a46e9-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="a46e9-120">Per generare classi C# basate sull'URI del servizio</span><span class="sxs-lookup"><span data-stu-id="a46e9-120">To generate C# classes based on the service URI</span></span>  
  
-   <span data-ttu-id="a46e9-121">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-121">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a46e9-122">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="a46e9-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="a46e9-123">Per generare classi Visual Basic basate sull'URI del servizio</span><span class="sxs-lookup"><span data-stu-id="a46e9-123">To generate Visual Basic classes based on the service URI</span></span>  
  
-   <span data-ttu-id="a46e9-124">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-124">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="a46e9-125">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="a46e9-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>  
  
### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="a46e9-126">Per generare classi C# basate sul file del modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="a46e9-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="a46e9-127">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-127">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="a46e9-128">Per generare classi Visual Basic basate sul file del modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="a46e9-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>  
  
-   <span data-ttu-id="a46e9-129">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-129">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="a46e9-130">Per generare classi C# basate sul file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="a46e9-130">To generate C# classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="a46e9-131">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-131">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="a46e9-132">Per generare classi Visual Basic basate sul file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="a46e9-132">To generate Visual Basic classes based on the .edmx file</span></span>  
  
-   <span data-ttu-id="a46e9-133">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="a46e9-133">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a46e9-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a46e9-134">See Also</span></span>  
 [<span data-ttu-id="a46e9-135">Generazione della libreria client del servizio dati</span><span class="sxs-lookup"><span data-stu-id="a46e9-135">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [<span data-ttu-id="a46e9-136">Procedura: aggiungere un riferimento al servizio dati</span><span class="sxs-lookup"><span data-stu-id="a46e9-136">How to: Add a Data Service Reference</span></span>](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)  
 [<span data-ttu-id="a46e9-137">Utilità client WCF Data Services (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="a46e9-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
