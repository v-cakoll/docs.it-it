---
title: 'Procedura: Generare manualmente classi del servizio dati client (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: f8d99213a1ef98c48855ba9f561f87a800768c89
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894304"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a><span data-ttu-id="3eab3-102">Procedura: Generare manualmente classi del servizio dati client (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="3eab3-102">How to: Manually Generate Client Data Service Classes (WCF Data Services)</span></span>
<span data-ttu-id="3eab3-103">WCF Data Services si integra con Visual Studio per consentire la generazione automatica di classi del servizio dati client quando si utilizza la finestra di dialogo **Aggiungi riferimento al servizio** per aggiungere un riferimento a un servizio dati in un progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3eab3-103">WCF Data Services integrates with Visual Studio to enable you to automatically generate client data service classes when you use the **Add Service Reference** dialog box to add a reference to a data service in a Visual Studio project.</span></span> <span data-ttu-id="3eab3-104">Per altre informazioni, vedere [Procedura: Aggiungere un riferimento](how-to-add-a-data-service-reference-wcf-data-services.md)al servizio dati.</span><span class="sxs-lookup"><span data-stu-id="3eab3-104">For more information, see [How to: Add a Data Service Reference](how-to-add-a-data-service-reference-wcf-data-services.md).</span></span> <span data-ttu-id="3eab3-105">È inoltre possibile generare in modo manuale le stesse classi del servizio dati client utilizzando lo strumento per la generazione del codice, ovvero `DataSvcUtil.exe`.</span><span class="sxs-lookup"><span data-stu-id="3eab3-105">You can also manually generate the same client data service classes by using the code-generation tool, `DataSvcUtil.exe`.</span></span> <span data-ttu-id="3eab3-106">Questo strumento, incluso con WCF Data Services, genera .NET Framework classi dalla definizione del servizio dati.</span><span class="sxs-lookup"><span data-stu-id="3eab3-106">This tool, which is included with WCF Data Services, generates .NET Framework classes from the data service definition.</span></span> <span data-ttu-id="3eab3-107">Può inoltre essere usato per generare classi del servizio dati in base al file del modello concettuale (CSDL) e al file con estensione edmx che rappresenta un modello di Entity Framework in un progetto di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3eab3-107">It can also be used to generate data service classes from the conceptual model (.csdl) file and from the .edmx file that represents an Entity Framework model in a Visual Studio project.</span></span>

 <span data-ttu-id="3eab3-108">Nell'esempio riportato in questo argomento vengono create le classi del servizio dati client in base al servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="3eab3-108">The example in this topic creates client data service classes based on the Northwind sample data service.</span></span> <span data-ttu-id="3eab3-109">Questo servizio viene creato al completamento della [WCF Data Services Guida introduttiva](quickstart-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="3eab3-109">This service is created when you complete the [WCF Data Services quickstart](quickstart-wcf-data-services.md).</span></span> <span data-ttu-id="3eab3-110">Per alcuni esempi inclusi in questo argomento è richiesto il file del modello concettuale per il modello Northwind.</span><span class="sxs-lookup"><span data-stu-id="3eab3-110">Some examples in this topic require the conceptual model file for the Northwind model.</span></span> <span data-ttu-id="3eab3-111">Per altre informazioni, vedere [Procedura: Utilizzare EdmGen. exe per generare i file](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)di modello e di mapping.</span><span class="sxs-lookup"><span data-stu-id="3eab3-111">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span> <span data-ttu-id="3eab3-112">Per alcuni esempi inclusi in questo argomento è richiesto il file con estensione edmx per il modello Northwind.</span><span class="sxs-lookup"><span data-stu-id="3eab3-112">Some examples in this topic require the .edmx file for the Northwind model.</span></span> <span data-ttu-id="3eab3-113">Per ulteriori informazioni, vedere [Cenni preliminari sui file](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))con estensione edmx.</span><span class="sxs-lookup"><span data-stu-id="3eab3-113">For more information, see [.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).</span></span>

### <a name="to-generate-c-classes-that-support-data-binding"></a><span data-ttu-id="3eab3-114">Per generare classi C# che supportano l'associazione dati</span><span class="sxs-lookup"><span data-stu-id="3eab3-114">To generate C# classes that support data binding</span></span>

- <span data-ttu-id="3eab3-115">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-115">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="3eab3-116">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="3eab3-116">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a><span data-ttu-id="3eab3-117">Per generare classi Visual Basic che supportano il data binding</span><span class="sxs-lookup"><span data-stu-id="3eab3-117">To generate Visual Basic classes that support data binding</span></span>

- <span data-ttu-id="3eab3-118">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-118">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="3eab3-119">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="3eab3-119">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-service-uri"></a><span data-ttu-id="3eab3-120">Per generare classi C# basate sull'URI del servizio</span><span class="sxs-lookup"><span data-stu-id="3eab3-120">To generate C# classes based on the service URI</span></span>

- <span data-ttu-id="3eab3-121">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-121">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="3eab3-122">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="3eab3-122">You must replace the value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a><span data-ttu-id="3eab3-123">Per generare classi Visual Basic basate sull'URI del servizio</span><span class="sxs-lookup"><span data-stu-id="3eab3-123">To generate Visual Basic classes based on the service URI</span></span>

- <span data-ttu-id="3eab3-124">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-124">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > <span data-ttu-id="3eab3-125">È necessario sostituire il valore fornito al parametro `/uri:` con l'URI dell'istanza del servizio dati Northwind di esempio.</span><span class="sxs-lookup"><span data-stu-id="3eab3-125">You must replace value supplied to the `/uri:` parameter with the URI of your instance of the Northwind sample data service.</span></span>

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="3eab3-126">Per generare classi C# basate sul file del modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="3eab3-126">To generate C# classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="3eab3-127">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-127">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a><span data-ttu-id="3eab3-128">Per generare classi Visual Basic basate sul file del modello concettuale (CSDL)</span><span class="sxs-lookup"><span data-stu-id="3eab3-128">To generate Visual Basic classes based on the conceptual model file (CSDL)</span></span>

- <span data-ttu-id="3eab3-129">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-129">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a><span data-ttu-id="3eab3-130">Per generare classi C# basate sul file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="3eab3-130">To generate C# classes based on the .edmx file</span></span>

- <span data-ttu-id="3eab3-131">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-131">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a><span data-ttu-id="3eab3-132">Per generare classi Visual Basic basate sul file con estensione edmx</span><span class="sxs-lookup"><span data-stu-id="3eab3-132">To generate Visual Basic classes based on the .edmx file</span></span>

- <span data-ttu-id="3eab3-133">Al prompt dei comandi eseguire il comando seguente senza interruzioni di riga:</span><span class="sxs-lookup"><span data-stu-id="3eab3-133">At the command prompt, execute the following command without line breaks:</span></span>

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a><span data-ttu-id="3eab3-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3eab3-134">See also</span></span>

- [<span data-ttu-id="3eab3-135">Generazione della libreria client del servizio dati</span><span class="sxs-lookup"><span data-stu-id="3eab3-135">Generating the Data Service Client Library</span></span>](generating-the-data-service-client-library-wcf-data-services.md)
- [<span data-ttu-id="3eab3-136">Procedura: Aggiungere un riferimento al servizio dati</span><span class="sxs-lookup"><span data-stu-id="3eab3-136">How to: Add a Data Service Reference</span></span>](how-to-add-a-data-service-reference-wcf-data-services.md)
- [<span data-ttu-id="3eab3-137">Utilità client WCF Data Services (DataSvcUtil.exe)</span><span class="sxs-lookup"><span data-stu-id="3eab3-137">WCF Data Service Client Utility (DataSvcUtil.exe)</span></span>](wcf-data-service-client-utility-datasvcutil-exe.md)
