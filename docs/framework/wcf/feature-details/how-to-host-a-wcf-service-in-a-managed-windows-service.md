---
title: 'Procedura: ospitare un servizio WCF in un servizio Windows gestito'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
ms.openlocfilehash: 698a5134683341fedf2a37f7d6383770e14c232c
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964795"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a>Procedura: ospitare un servizio WCF in un servizio Windows gestito

In questo argomento vengono illustrati i passaggi di base necessari per creare un servizio Windows Communication Foundation (WCF) ospitato da un servizio Windows. Lo scenario è abilitato dall'opzione di hosting del servizio Windows gestito che è un servizio WCF con esecuzione prolungata ospitato all'esterno di Internet Information Services (IIS) in un ambiente protetto che non viene attivato tramite messaggio. La durata del servizio è controllata invece dal sistema operativo. Questa opzione di hosting è disponibile in tutte le versioni di Windows.

I servizi Windows possono essere gestiti con Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) e possono essere configurati per essere avviati automaticamente all'avvio del sistema. Questa opzione di hosting consiste nella registrazione del dominio applicazione (AppDomain) che ospita un servizio WCF come servizio Windows gestito, in modo che la durata del processo del servizio sia controllata da Gestione controllo servizi (SCM) per i servizi Windows.

Il codice del servizio include un'implementazione del contratto di servizio, una classe di servizio Windows e una classe del programma di installazione. La classe di implementazione del servizio, `CalculatorService`, è un servizio WCF. `CalculatorWindowsService` è un servizio Windows. Per essere qualificata come servizio Windows, la classe eredita da `ServiceBase` e implementa i metodi `OnStart` e `OnStop`. In `OnStart`, viene creata e aperta una classe <xref:System.ServiceModel.ServiceHost> per il tipo `CalculatorService`. In `OnStop`, il servizio viene interrotto ed eliminato. L'host è inoltre responsabile di fornire un indirizzo di base all'host del servizio, che è stato configurato nelle impostazioni dell'applicazione. La classe del programma di installazione, che eredita da <xref:System.Configuration.Install.Installer>, consente al programma di essere installato come servizio Windows dallo strumento Installutil.exe.

## <a name="construct-the-service-and-provide-the-hosting-code"></a>Costruire il servizio e fornire il codice host

1. Creare un nuovo progetto di **app console** di Visual Studio denominato **servizio**.

2. Rinominare Program.cs come Service.cs.

3. Modificare lo spazio dei nomi in `Microsoft.ServiceModel.Samples`.

4. Aggiungere riferimenti agli assembly riportati di seguito:

    - System.ServiceModel.dll

    - System.ServiceProcess.dll

    - System.Configuration.Install.dll

5. Aggiungere le istruzioni using seguenti a Service.cs.

     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]

6. Definire il contratto di servizio `ICalculator` come mostrato nel codice seguente.

     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]

7. Implementare il contratto di servizio in una classe denominata `CalculatorService` come illustrato nel codice seguente.

     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]

8. Creare una nuova classe denominata `CalculatorWindowsService` che eredita dalla classe <xref:System.ServiceProcess.ServiceBase>. Aggiungere una variabile locale denominata `serviceHost` per fare riferimento all'istanza di <xref:System.ServiceModel.ServiceHost>. Definire il metodo `Main` che chiama `ServiceBase.Run(new CalculatorWindowsService)`

     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]

9. Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> creando e aprendo una nuova istanza di <xref:System.ServiceModel.ServiceHost> come mostrato nel codice seguente.

     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]

10. Eseguire l'override del metodo <xref:System.ServiceProcess.ServiceBase.OnStop%2A> chiudendo <xref:System.ServiceModel.ServiceHost> come mostrato nel codice seguente.

     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]

11. Creare una nuova classe denominata `ProjectInstaller` che eredita da <xref:System.Configuration.Install.Installer> e che sia contrassegnata con <xref:System.ComponentModel.RunInstallerAttribute> impostato su `true`. Questo consente l'installazione del servizio Windows mediante lo strumento Installutil.exe.

     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]

12. Rimuovere la classe `Service` generata al momento della creazione del progetto.

13. Aggiungere un file di configurazione dell'applicazione al progetto. Sostituire il contenuto del file con l'XML di configurazione riportato di seguito.

    ```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <system.serviceModel>    <services>
          <!-- This section is optional with the new configuration model
               introduced in .NET Framework 4. -->
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"
                   behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->
            <endpoint address=""
                      binding="wsHttpBinding"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
            <endpoint address="mex"
                      binding="mexHttpBinding"
                      contract="IMetadataExchange" />
          </service>
        </services>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceMetadata httpGetEnabled="true"/>
              <serviceDebug includeExceptionDetailInFaults="False"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>
      </system.serviceModel>
    </configuration>
    ```

     Fare clic con il pulsante destro del mouse sul file app. config nel **Esplora soluzioni** e selezionare **Proprietà**. In **copia nella directory di output** selezionare **copia se più recente**.

     In questo esempio vengono specificati in modo esplicito gli endpoint del file di configurazione. Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti. In questo esempio, poiché il servizio ha <xref:System.ServiceModel.Description.ServiceMetadataBehavior> impostato su `true`, è anche abilitata la pubblicazione di metadati. Per altre informazioni su endpoint, associazioni e comportamenti predefiniti, vedere [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) (Configurazione semplificata) e [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md) (Configurazione semplificata per servizi WCF).

## <a name="install-and-run-the-service"></a>Installare ed eseguire il servizio .

1. Compilare la soluzione per creare l'eseguibile `Service.exe`.

2. Aprire Prompt dei comandi per gli sviluppatori per Visual Studio e passare alla directory del progetto. Digitare `installutil bin\service.exe` al prompt dei comandi per installare il servizio Windows.

     Digitare `services.msc` al prompt dei comandi per accedere a Gestione controllo servizi (SCM). Il servizio Windows verrà visualizzato in Servizi come "WCFWindowsServiceSample". Il servizio WCF può rispondere ai client solo se il servizio Windows è in esecuzione. Per avviare il servizio, fare clic con il pulsante destro del mouse su di esso in Gestione controllo servizi e scegliere "Avvia" oppure digitare **net start WCFWindowsServiceSample** al prompt dei comandi.

3. Se si apportano modifiche al servizio, è prima necessario arrestare il servizio e disinstallarlo. Per arrestare il servizio, fare clic con il pulsante destro del mouse sul servizio in SCM e selezionare "arresta" oppure **digitare net stop WCFWindowsServiceSample** al prompt dei comandi. Si noti che se si arresta il servizio Windows e quindi si esegue un client, si verificherà un'eccezione <xref:System.ServiceModel.EndpointNotFoundException> quando un client tenta di accedere al servizio. Per disinstallare il servizio Windows digitare **installutil/u bin\service.exe** al prompt dei comandi.

## <a name="example"></a>Esempio

Di seguito è riportato un elenco completo del codice utilizzato in questo argomento:

[!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
[!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]

Analogamente all'opzione di self-hosting, l'ambiente host del servizio Windows richiede che venga scritto codice di hosting come parte dell'applicazione. Il servizio viene implementato come applicazione console e contiene il proprio codice di hosting. In altri ambienti host, quali ad esempio l'host del servizio di attivazione dei processi di Windows (WAS, Windows Process Activation Service) in Internet Information Services (IIS), non è necessario che gli sviluppatori scrivano codice di hosting.

## <a name="see-also"></a>Vedere anche

- [Configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md)
- [Hosting in un'applicazione gestita](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)
- [Servizi di hosting](../../../../docs/framework/wcf/hosting-services.md)
- [Funzionalità di hosting di Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
