---
title: 'Procedura: eseguire la migrazione del codice di un servizio Web ASP.NET a Windows Communication Foundation'
ms.date: 03/30/2017
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
ms.openlocfilehash: 90a6109a56299ec1bcaff4a35141abc194484772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496699"
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a>Procedura: eseguire la migrazione del codice di un servizio Web ASP.NET a Windows Communication Foundation
La procedura seguente descrive come eseguire la migrazione di un servizio Web ASP.NET per Windows Communication Foundation (WCF).  
  
## <a name="procedure"></a>Routine  
  
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
  
8.  Aggiungere riferimenti agli assembly WCF System. ServiceModel e Serialization al progetto di servizio Web ASP.NET.  
  
9. Eseguire [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare una classe client WCF da WSDL. Aggiungere il modulo di classe generato alla soluzione.  
  
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
  
13. Configurare la classe, che ora è un tipo di servizio WCF, in modo da richiedere la modalità di compatibilità ASP.NET di WCF, se il servizio Web ASP.NET si basava su uno dei seguenti:  
  
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
  
15. Creare un file del servizio WCF per il servizio, assegnargli l'estensione ASMX e salvarlo nella radice dell'applicazione in IIS.  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. Aggiungere una configurazione di WCF per il servizio in un file Web. config. Configurare il servizio per utilizzare il [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), utilizzare il file del servizio con estensione ASMX creato nei passaggi precedenti e per non generare WSDL per se stesso, ma utilizzare il file WSDL dal passaggio 2. Configurare inoltre il servizio per usare la modalità di compatibilità ASP.NET, se necessario.  
  
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
 [Procedura: Eseguire la migrazione del codice client dei servizi Web ASP.NET in Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
