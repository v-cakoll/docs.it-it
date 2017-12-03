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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d6ed443d2b645687d59a3d795c706f303616cfb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a>Procedura: eseguire la migrazione del codice di un servizio Web ASP.NET a Windows Communication Foundation
Nella procedura seguente viene descritto come eseguire la migrazione di un servizio Web ASP.NET a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="procedure"></a>Procedura  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a>Per eseguire la migrazione del codice di un servizio Web ASP.NET a WCF  
  
1.  Assicurarsi che esista un set completo di test per il servizio.  
  
2.  Generare il codice WSDL per il servizio e salvarne una copia nella stessa cartella del file con estensione asmx del servizio.  
  
3.  Eseguire l'aggiornamento del servizio Web ASP.NET per usare .NET 2.0. Prima di distribuire .NET Framework 2.0 per l'applicazione in IIS e quindi utilizzare Visual Studio 2005 per automatizzare il processo di conversione di codice, come documentato nel [Guida dettagliata alla conversione di progetti Web da Visual Studio .NET 2002/2003 a Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492). Eseguire il set di test.  
  
4.  Fornire valori espliciti per i parametri `Namespace` and `Name` degli attributi <xref:System.Web.Services.WebService>, se non sono già stati forniti. Eseguire la stessa operazione per il parametro `MessageName` della classe <xref:System.Web.Services.WebMethodAttribute>. Se non sono già stati forniti valori espliciti per le intestazioni SOAPAction HTTP da cui le richieste vengono indirizzate ai metodi, specificare esplicitamente il valore predefinito del parametro `Action` con <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.  
  
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
  
5.  Verificare la modifica.  
  
6.  Spostare qualsiasi codice effettivo presente nei corpi dei metodi della classe in una classe separata che verrà usata dalla classe originale.  
  
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
  
7.  Verificare la modifica.  
  
8.  Aggiungere riferimenti agli assembly [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] System.ServiceModel e System.Runtime.Serialization al progetto del servizio Web ASP.NET.  
  
9. Eseguire [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] classe client da WSDL. Aggiungere il modulo di classe generato alla soluzione.  
  
10. Il modulo di classe generato nel passaggio precedente contiene la definizione di un'interfaccia.  
  
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
  
     Modificare la definizione della classe del servizio Web ASP.NET per specificare che classe implementa l'interfaccia in questione, come illustrato nel codice di esempio seguente.  
  
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
  
11. Compilare il progetto. Potrebbero verificarsi alcuni errori a causa del codice generato nel passaggio nove, che duplica alcune definizioni del tipo. Correggere questi errori generalmente eliminando le definizioni dei tipi preesistenti. Verificare la modifica.  
  
12. Rimuovere gli attributi specifici di ASP.NET, ad esempio <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> e <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.  
  
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
  
13. Configurare la classe, che ora è un tipo di servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], per richiedere la modalità di compatibilità ASP.NET [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se il servizio Web ASP.NET si basa su uno qualsiasi degli elementi seguenti:  
  
    -   Classe <xref:System.Web.HttpContext>.  
  
    -   Profili ASP.NET.  
  
    -   ACL sui file con estensione asmx.  
  
    -   Opzioni di autenticazione IIS  
  
    -   Opzioni di rappresentazione ASP.NET  
  
    -   Globalizzazione ASP.NET  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. Rinominare il file con estensione asmx originale in asmx.old.  
  
15. Creare un file di servizio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per il servizio, assegnargli l'estensione asmx e salvarlo nella directory principale dell'applicazione in IIS.  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. Aggiungere una configurazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per il servizio al file di configurazione Web.config. Configurare il servizio per utilizzare il [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), utilizzare il file del servizio con estensione ASMX creato nei passaggi precedenti e per non generare WSDL per se stesso, ma utilizzare il file WSDL dal passaggio 2. Configurare inoltre il servizio per usare la modalità di compatibilità ASP.NET, se necessario.  
  
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
  
17. Salvare la configurazione.  
  
18. Compilare il progetto.  
  
19. Eseguire il set di test per assicurarsi che tutte le modifiche funzionino.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: eseguire la migrazione di codice Client del servizio Web ASP.NET a Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
