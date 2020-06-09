---
title: Esempio di condivisione delle porte Net.TCP
ms.date: 03/30/2017
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
ms.openlocfilehash: 6c196380951d0da912cd937e3ebc38a03f80489c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84584311"
---
# <a name="nettcp-port-sharing-sample"></a>Esempio di condivisione delle porte Net.TCP
Il protocollo TCP/IP utilizza un numero a 16 bit, definito porta, per differenziare le connessioni a più applicazioni di rete che sono in esecuzione nello stesso computer. Se un'applicazione è in ascolto su una porta, tutto il traffico TCP per quella porta viene indirizzato a tale applicazione. Su quella porta non possono essere contemporaneamente in ascolto altre applicazioni.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 Molti protocolli utilizzano un numero di porta standard o predefinito. Ad esempio, il protocollo HTTP utilizza in genere la porta TCP 80. Internet Information Services (IIS) dispone di un listener per condividere una porta tra più applicazioni HTTP. IIS è in ascolto direttamente sulla porta e inoltra i messaggi all'applicazione appropriata in base alle informazioni presenti all'interno del flusso di messaggi. In questo modo più applicazioni HTTP possono utilizzare lo stesso numero di porta senza dover competere per riservare la porta per la ricezione dei messaggi.  
  
 La condivisione delle porte NetTcp è una funzionalità di Windows Communication Foundation (WCF) che consente a più applicazioni di rete di condividere una singola porta. Il servizio di condivisione porte Net.Tcp accetta connessioni mediante il protocollo net.tcp e inoltra i messaggi in base al relativo indirizzo di destinazione.  
  
 Questo servizio non è abilitato per impostazione predefinita ed è necessario abilitarlo manualmente prima di eseguire questo esempio. Per altre informazioni, vedere [procedura: abilitare il servizio di condivisione porte net. TCP](../feature-details/how-to-enable-the-net-tcp-port-sharing-service.md). Se il servizio è disabilitato, viene generata un'eccezione all'avvio dell'applicazione server.  
  
```console
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 La condivisione delle porte può essere abilitata sul server impostando la proprietà <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> dell'associazione <xref:System.ServiceModel.NetTcpBinding> o l'elemento di associazione <xref:System.ServiceModel.Channels.TcpTransportBindingElement>. Il client non deve necessariamente conoscere la modalità di configurazione della condivisione delle porte per poterla utilizzare sul server.  
  
## <a name="enabling-port-sharing"></a>Abilitazione della condivisione delle porte  
 Nel codice seguente viene illustrata l'abilitazione della condivisione delle porte sul server. Viene avviata un'istanza del servizio `ICalculator` su una porta fissa con un percorso URI casuale. Anche se due servizi possono condividere la stessa porta, gli indirizzi degli endpoint complessivi devono comunque essere univoci affinché il servizio di condivisione porte Net.Tcp possa indirizzare i messaggi all'applicazione corretta.  

```csharp
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address = $"net.tcp://localhost:9000/calculator/{salt}";
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```

 Quando la condivisione delle porte è abilitata, è possibile eseguire più volte il servizio senza generare un conflitto sul numero della porta. Se si modifica il codice per disabilitare la condivisione delle porte, l'avvio di due copie del servizio comporta l'errore della seconda con un'eccezione <xref:System.ServiceModel.AddressAlreadyInUseException>.  
  
```console  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a>Esecuzione dell'esempio  
 È possibile utilizzare il client di prova per verificare che i messaggi vengano indirizzati correttamente ai servizi che condividono la porta.  

```csharp
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = $"net.tcp://localhost:9000/calculator/{salt}";
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```

 Ogni istanza del servizio mostra il relativo numero e indirizzo univoco. Ad esempio, è possibile visualizzare il testo seguente quando si esegue service.exe.  
  
```console  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 Immettere il numero del servizio indicato in questo punto quando si esegue client.exe.  
  
```console  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 Questo esempio può essere eseguito in una configurazione a più computer modificando l'indirizzo generato che il client utilizza. Nel file Client.cs modificare la stringa di formato dell'indirizzo dell'endpoint affinché corrisponda al nuovo indirizzo del servizio. Sostituire qualsiasi riferimento a "localhost" con l'indirizzo IP del server. È necessario ricompilare l'esempio dopo avere apportato questa modifica.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Installare ASP.NET 4,0 usando il comando seguente.  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Abilitare il servizio di condivisione porte Net.Tcp come descritto nella sezione dell'introduzione.  
  
4. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
5. Per eseguire l'esempio in una configurazione con un solo computer o tra computer diversi, seguire le istruzioni in [esecuzione degli esempi di Windows Communication Foundation](running-the-samples.md). Dettagli specifici per l'esecuzione di questo esempio sono inclusi nella sezione Esecuzione dell'esempio.  
