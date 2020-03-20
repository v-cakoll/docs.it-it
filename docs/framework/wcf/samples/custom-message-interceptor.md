---
title: Intercettore dei messaggi personalizzati
ms.date: 03/30/2017
ms.assetid: 73f20972-53f8-475a-8bfe-c133bfa225b0
ms.openlocfilehash: 433b14433a7e2dd6edad551a2732e9049a9861ea
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145086"
---
# <a name="custom-message-interceptor"></a>Intercettore dei messaggi personalizzati
In questo esempio viene illustrato l'utilizzo del modello di estensibilità del canale. In particolare, viene illustrato come implementare un elemento di associazione personalizzato che crea channel factory e listener del canale per intercettare tutti i messaggi in ingresso e in uscita in un particolare punto nello stack di runtime. L'esempio include anche un client e un server che illustrano l'utilizzo di queste factory personalizzate.  
  
 In questo esempio sia il client che il servizio sono programmi console (.exe). Il client e il servizio fanno entrambi uso di una libreria comune (.dll) che contiene l'elemento di associazione personalizzato e gli oggetti di runtime associati.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\MessageInterceptor`  
  
 Nell'esempio viene descritta la procedura consigliata per la creazione di un canale a più livelli personalizzato in Windows Communication Foundation (WCF), utilizzando il framework di canale e seguendo le procedure consigliate WCF. I passaggi per creare un canale su più livelli personalizzato sono i seguenti.  
  
1. Decidere quali forme del canale saranno supportate dalla channel factory e dal listener del canale.  
  
2. Creare una channel factory e un listener di canale che supportano le forme del canale.  
  
3. Inserire un elemento di associazione che aggiunge il canale su più livelli personalizzato a uno stack di canali.  
  
4. Aggiungere una sezione di estensione degli elementi di associazione per esporre il nuovo elemento di associazione al sistema di configurazione.  
  
## <a name="channel-shapes"></a>Forme del canale  
 Per scrivere un canale su più livelli personalizzato, è necessario innanzitutto stabilire quali forme sono necessarie per il canale. Per il controllo messaggi, si supporta qualsiasi forma supportata dal livello sottostante (ad esempio, se il livello sottostante può compilare <xref:System.ServiceModel.Channels.IOutputChannel> e <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, si espongono anche <xref:System.ServiceModel.Channels.IOutputChannel> e <xref:System.ServiceModel.Channels.IDuplexSessionChannel>).  
  
## <a name="channel-factory-and-listener-factory"></a>Channel Factory e Listener Factory  
 Il passaggio successivo per scrivere un canale su più livelli personalizzato consiste nel creare un'implementazione di <xref:System.ServiceModel.Channels.IChannelFactory> per i canali client e di <xref:System.ServiceModel.Channels.IChannelListener> per i canali del servizio.  
  
 Queste classi prendono una factory interna e un listener e delegano tutto tranne le chiamate `OnCreateChannel` e `OnAcceptChannel` alla factory interna e al listener.  
  
```csharp
class InterceptingChannelFactory<TChannel> : ChannelFactoryBase<TChannel>  
{
    //...
}

class InterceptingChannelListener<TChannel> : ListenerFactoryBase<TChannel>  
{
    //...
}  
```  
  
## <a name="adding-a-binding-element"></a>Aggiunta di un elemento di associazione.  
 L'esempio definisce un elemento di associazione personalizzato: `InterceptingBindingElement`. `InterceptingBindingElement`prende `ChannelMessageInterceptor` un come input, `ChannelMessageInterceptor` e lo usa per manipolare i messaggi che passano attraverso di esso. Si tratta della sola classe che deve essere pubblica. La factory, il listener e i canali possono tutti essere implementazioni interne delle interfacce di runtime pubbliche.  
  
```csharp
public class InterceptingBindingElement : BindingElement
{
}
```  
  
## <a name="adding-configuration-support"></a>Aggiunta del supporto di configurazione  
 Per integrare la configurazione di associazione la libreria definisce un gestore della sezione di configurazione come sezione di estensione dell'elemento di associazione. I file di configurazione del client e del server devono registrare l'estensione dell'elemento di associazione con il sistema di configurazione. Implementatori che vogliono esporre l'elemento di associazione al sistema di configurazione possono derivare da questa classe.  
  
```csharp
public abstract class InterceptingElement : BindingElementExtensionElement
{
    //...
}
```  
  
## <a name="adding-policy"></a>Aggiunta di criteri  
 Per integrarsi con il sistema dei criteri, `InterceptingBindingElement` implementa IPolicyExportExtension per segnalare che si deve partecipare alla generazione di criteri. Per supportare i criteri di importazione su un client generato, l'utente può iscrivere una classe derivata di `InterceptingBindingElementImporter`() ed eseguire l'override di `CreateMessageInterceptor` per generare la classe `ChannelMessageInterceptor` attivata dal criterio.  
  
## <a name="example-droppable-message-inspector"></a>Esempio: Controllo messaggi rilasciabili  
 Inclusa nell'esempio vi è un'implementazione di esempio di `ChannelMessageInspector` che elimina i messaggi.  
  
```csharp
class DroppingServerElement : InterceptingElement  
{  
    protected override ChannelMessageInterceptor CreateMessageInterceptor()  
    {  
        return new DroppingServerInterceptor();  
    }  
}  
```  
  
 È possibile accedervi tramite configurazione come segue:  
  
```xml  
<configuration>  
    ...  
    <system.serviceModel>  
        ...  
        <extensions>  
            <bindingElementExtensions>  
                <add name="droppingInterceptor"
                   type=  
          "Microsoft.ServiceModel.Samples.DroppingServerElement, library"/>  
            </bindingElementExtensions>  
        </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
 Il client e il server utilizzano entrambi questa sezione di configurazione appena creata per inserire le factory personalizzate nel livello più basso degli stack dei canali di runtime (sopra il livello del trasporto).  
  
```xml  
<customBinding>  
  <binding name="sampleBinding">  
    <droppingInterceptor/>  
    <httpTransport/>  
  </binding>  
</customBinding>  
```  
  
 Il client utilizza la libreria `MessageInterceptor` per aggiungere un'intestazione personalizzata ai messaggi, anche a quelli numerati. Il servizio d'altro canto utilizza la libreria `MessageInterceptor` per eliminare qualsiasi messaggio che non ha questa intestazione speciale.  
  
 Dopo l'esecuzione del servizio e del client, l'output del client dovrebbe essere il seguente.  
  
```console  
Reporting the next 10 wind speed  
100 kph  
Server dropped a message.  
90 kph  
80 kph  
Server dropped a message.  
70 kph  
60 kph  
Server dropped a message.  
50 kph  
40 kph  
Server dropped a message.  
30 kph  
20 kph  
Server dropped a message.  
10 kph  
Press ENTER to shut down client  
```  
  
 Il client riporta 10 diverse velocità del vento al servizio, ma contrassegna solo la metà di esse con un'intestazione speciale.  
  
 Nel servizio, si dovrebbe vedere l'output seguente.  
  
```console  
Press ENTER to exit.  
Dangerous wind detected! Reported speed (90) is greater than 64 kph.  
Dangerous wind detected! Reported speed (70) is greater than 64 kph.  
5 wind speed reports have been received.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Installare ASP.NET 4.0 utilizzando il comando seguente.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Per compilare la soluzione, seguire le istruzioni in [Compilazione di Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
5. Eseguire prima Service.exe quindi Client.exe e controllare l'output di entrambe le finestre della console.  
