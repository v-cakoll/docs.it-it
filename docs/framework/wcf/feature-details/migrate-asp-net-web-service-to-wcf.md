---
title: 'Procedura: eseguire la migrazione del codice di un servizio Web ASP.NET a Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 94d6cc499caddc8b3cbbf8ba7845e4de5441165c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a><span data-ttu-id="5bdb4-102">Procedura: eseguire la migrazione del codice di un servizio Web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5bdb4-102">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="5bdb4-103">Nella procedura seguente viene descritto come eseguire la migrazione di un servizio Web ASP.NET a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5bdb4-103">The following procedure describes how to migrate an ASP.NET Web Service to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="5bdb4-104">Procedura</span><span class="sxs-lookup"><span data-stu-id="5bdb4-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a><span data-ttu-id="5bdb4-105">Per eseguire la migrazione del codice di un servizio Web ASP.NET a WCF</span><span class="sxs-lookup"><span data-stu-id="5bdb4-105">To migrate ASP.NET Web service code to WCF</span></span>  
  
1.  <span data-ttu-id="5bdb4-106">Assicurarsi che esista un set completo di test per il servizio.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-106">Ensure that a comprehensive set of tests exist for the service.</span></span>  
  
2.  <span data-ttu-id="5bdb4-107">Generare il codice WSDL per il servizio e salvarne una copia nella stessa cartella del file con estensione asmx del servizio.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-107">Generate the WSDL for the service and save a copy in the same folder as the service’s .asmx file.</span></span>  
  
3.  <span data-ttu-id="5bdb4-108">Eseguire l'aggiornamento del servizio Web ASP.NET per usare .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-108">Upgrade the ASP.NET Web service to use .NET 2.0.</span></span> <span data-ttu-id="5bdb4-109">Prima di distribuire .NET Framework 2.0 per l'applicazione in IIS e quindi utilizzare Visual Studio 2005 per automatizzare il processo di conversione di codice, come documentato nel [Guida dettagliata alla conversione di progetti Web da Visual Studio .NET 2002/2003 a Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span><span class="sxs-lookup"><span data-stu-id="5bdb4-109">First deploy the .NET Framework 2.0 to the application in IIS, and then use Visual Studio 2005 to automate the code conversion process, as documented in [Step-By-Step Guide to Converting Web Projects from Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span></span> <span data-ttu-id="5bdb4-110">Eseguire il set di test.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-110">Run the set of tests.</span></span>  
  
4.  <span data-ttu-id="5bdb4-111">Fornire valori espliciti per i parametri `Namespace` and `Name` degli attributi <xref:System.Web.Services.WebService>, se non sono già stati forniti.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-111">Provide explicit values for the `Namespace` and `Name` parameters of the <xref:System.Web.Services.WebService> attributes if they are not provided already.</span></span> <span data-ttu-id="5bdb4-112">Eseguire la stessa operazione per il parametro `MessageName` della classe <xref:System.Web.Services.WebMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-112">Do the same for the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span> <span data-ttu-id="5bdb4-113">Se non sono già stati forniti valori espliciti per le intestazioni SOAPAction HTTP da cui le richieste vengono indirizzate ai metodi, specificare esplicitamente il valore predefinito del parametro `Action` con <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-113">If explicit values are not already provided for the SOAPAction HTTP headers by which requests are routed to methods, then explicitly specify the default value of the `Action` parameter with a <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
5.  <span data-ttu-id="5bdb4-114">Verificare la modifica.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-114">Test the change.</span></span>  
  
6.  <span data-ttu-id="5bdb4-115">Spostare qualsiasi codice effettivo presente nei corpi dei metodi della classe in una classe separata che verrà usata dalla classe originale.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-115">Move any substantive code in the bodies of the methods of the class to a separate class that the original class is made to use.</span></span>  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
    }  
  
    internal class ActualAdder  
    {  
         internal double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
7.  <span data-ttu-id="5bdb4-116">Verificare la modifica.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-116">Test the change.</span></span>  
  
8.  <span data-ttu-id="5bdb4-117">Aggiungere riferimenti agli assembly [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] System.ServiceModel e System.Runtime.Serialization al progetto del servizio Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-117">Add references to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assemblies System.ServiceModel and System.Runtime.Serialization to the ASP.NET Web service project.</span></span>  
  
9. <span data-ttu-id="5bdb4-118">Eseguire [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] classe client da WSDL.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-118">Run [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class from the WSDL.</span></span> <span data-ttu-id="5bdb4-119">Aggiungere il modulo di classe generato alla soluzione.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-119">Add the generated class module to the solution.</span></span>  
  
10. <span data-ttu-id="5bdb4-120">Il modulo di classe generato nel passaggio precedente contiene la definizione di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-120">The class module generated in the preceding step contains the definition of an interface.</span></span>  
  
    ```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface AdderSoap  
    {  
         [System.ServiceModel.OperationContractAttribute(  
          Action="http://tempuri.org/Add",   
          ReplyAction="http://tempuri.org/Add")]  
         AddResponse Add(AddRequest request);  
    }  
    ```  
  
     <span data-ttu-id="5bdb4-121">Modificare la definizione della classe del servizio Web ASP.NET per specificare che classe implementa l'interfaccia in questione, come illustrato nel codice di esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-121">Modify the definition of the ASP.NET Web service class so that the class is defined as implementing that interface, as shown in the following sample code.</span></span>  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder: AdderSoap  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
            return new AddResponse(  
            new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
11. <span data-ttu-id="5bdb4-122">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-122">Compile the project.</span></span> <span data-ttu-id="5bdb4-123">Potrebbero verificarsi alcuni errori a causa del codice generato nel passaggio nove, che duplica alcune definizioni del tipo.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-123">There may be some errors due to the code generated in step nine that duplicated some type definitions.</span></span> <span data-ttu-id="5bdb4-124">Correggere questi errori generalmente eliminando le definizioni dei tipi preesistenti.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-124">Repair those errors, usually by deleting the pre-existing definitions of the types.</span></span> <span data-ttu-id="5bdb4-125">Verificare la modifica.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-125">Test the change.</span></span>  
  
12. <span data-ttu-id="5bdb4-126">Rimuovere gli attributi specifici di ASP.NET, ad esempio <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> e <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-126">Remove the ASP.NET-specific attributes, such as the <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> and <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
    ```  
    public class Adder: AdderSoap  
    {  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
              return new AddResponse(  
             new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
13. <span data-ttu-id="5bdb4-127">Configurare la classe, che ora è un tipo di servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], per richiedere la modalità di compatibilità ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se il servizio Web ASP.NET si basa su uno qualsiasi degli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5bdb4-127">Configure the class, which is now a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service type, to require [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode if the ASP.NET Web service relied on any of the following:</span></span>  
  
    -   <span data-ttu-id="5bdb4-128">Classe <xref:System.Web.HttpContext>.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-128">The <xref:System.Web.HttpContext> class.</span></span>  
  
    -   <span data-ttu-id="5bdb4-129">Profili ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-129">The ASP.NET Profiles.</span></span>  
  
    -   <span data-ttu-id="5bdb4-130">ACL sui file con estensione asmx.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-130">ACLs on .asmx files.</span></span>  
  
    -   <span data-ttu-id="5bdb4-131">Opzioni di autenticazione IIS</span><span class="sxs-lookup"><span data-stu-id="5bdb4-131">IIS authentication options.</span></span>  
  
    -   <span data-ttu-id="5bdb4-132">Opzioni di rappresentazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5bdb4-132">ASP.NET impersonation options.</span></span>  
  
    -   <span data-ttu-id="5bdb4-133">Globalizzazione ASP.NET</span><span class="sxs-lookup"><span data-stu-id="5bdb4-133">ASP.NET globalization.</span></span>  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. <span data-ttu-id="5bdb4-134">Rinominare il file con estensione asmx originale in asmx.old.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-134">Rename the original .asmx file to .asmx.old.</span></span>  
  
15. <span data-ttu-id="5bdb4-135">Creare un file di servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per il servizio, assegnargli l'estensione asmx e salvarlo nella directory principale dell'applicazione in IIS.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-135">Create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service file for the service, give it the extension, .asmx, and save it into the application root in IIS.</span></span>  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. <span data-ttu-id="5bdb4-136">Aggiungere una configurazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per il servizio al file di configurazione Web.config.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-136">Add a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration for the service to its Web.config file.</span></span> <span data-ttu-id="5bdb4-137">Configurare il servizio per utilizzare il [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), utilizzare il file del servizio con estensione ASMX creato nei passaggi precedenti e per non generare WSDL per se stesso, ma utilizzare il file WSDL dal passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-137">Configure the service to use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), to use the service file with the .asmx extension created in the preceding steps, and to not generate WSDL for itself, but to use the WSDL from step two.</span></span> <span data-ttu-id="5bdb4-138">Configurare inoltre il servizio per usare la modalità di compatibilità ASP.NET, se necessario.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-138">Also configure it to use ASP.NET compatibility mode if necessary.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.web>  
      <compilation>  
      <buildProviders>  
       <remove extension=".asmx" />  
       <add extension=".asmx"   
        type=  
        "System.ServiceModel.Activation.ServiceBuildProvider,  
        T:System.ServiceModel, Version=2.0.0.0,   
       Culture=neutral,   
       PublicKeyToken=b77a5c561934e089" />  
      </buildProviders>  
      </compilation>  
     </system.web>  
     <system.serviceModel>  
      <services>  
      <service name="MyOrganization.Adder "  
        behaviorConfiguration="AdderBehavior">  
       <endpoint   
        address=""  
        binding="basicHttpBinding"  
        contract="AdderSoap "/>  
       </service>  
      </services>  
      <behaviors>  
      <behavior name="AdderBehavior">  
       <metadataPublishing   
        enableMetadataExchange="true"   
        enableGetWsdl="true"   
        enableHelpPage="true"   
        metadataLocation=  
        "http://MyHost.com/AdderService/Service.WSDL"/>  
      </behavior>  
      </behaviors>  
      <serviceHostingEnvironment   
       aspNetCompatibilityEnabled ="true"/>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
17. <span data-ttu-id="5bdb4-139">Salvare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-139">Save the configuration.</span></span>  
  
18. <span data-ttu-id="5bdb4-140">Compilare il progetto.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-140">Compile the project.</span></span>  
  
19. <span data-ttu-id="5bdb4-141">Eseguire il set di test per assicurarsi che tutte le modifiche funzionino.</span><span class="sxs-lookup"><span data-stu-id="5bdb4-141">Run the set of tests to make sure all the changes work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bdb4-142">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bdb4-142">See Also</span></span>  
 [<span data-ttu-id="5bdb4-143">Procedura: eseguire la migrazione di codice Client del servizio Web ASP.NET a Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="5bdb4-143">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
