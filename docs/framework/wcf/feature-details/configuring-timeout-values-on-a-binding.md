---
title: Configurazione dei valori di timeout per un'associazione
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: 968e80bbd4b50d72d089a325f8e3fe498de2eac2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185294"
---
# <a name="configuring-timeout-values-on-a-binding"></a>Configurazione dei valori di timeout per un'associazione
Esistono numerose impostazioni di timeout disponibili nelle associazioni WCF. La configurazione corretta di queste impostazioni di timeout non solo può migliorare le prestazioni del servizio, bensì anche svolgere un ruolo nell'usabilità e nella sicurezza del servizio. Nelle associazioni WCF sono disponibili i timeout seguenti:  
  
1. OpenTimeout  
  
2. CloseTimeout  
  
3. SendTimeout  
  
4. ReceiveTimeout  
  
## <a name="wcf-binding-timeouts"></a>Timeout di associazioni WCF  
 Ognuna delle impostazioni riportate in questo argomento viene effettuata sull'associazione stessa, nel codice o nella configurazione. Nel codice seguente viene illustrato come impostare a livello di codice i timeout in un'associazione WCF nel contesto di un servizio self-hosted.  
  
```csharp  
public static void Main()
{
    Uri baseAddress = new Uri("http://localhost/MyServer/MyService");

    try
    {
        ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService));

        WSHttpBinding binding = new WSHttpBinding();
        binding.OpenTimeout = new TimeSpan(0, 10, 0);
        binding.CloseTimeout = new TimeSpan(0, 10, 0);
        binding.SendTimeout = new TimeSpan(0, 10, 0);
        binding.ReceiveTimeout = new TimeSpan(0, 10, 0);

        serviceHost.AddServiceEndpoint("ICalculator", binding, baseAddress);
        serviceHost.Open();

        // The service can now be accessed.
        Console.WriteLine("The service is ready.");
        Console.WriteLine("Press <ENTER> to terminate service.");
        Console.WriteLine();
        Console.ReadLine();
    }
    catch (CommunicationException ex)
    {
        // Handle exception ...
    }
}
```  
  
 Nell'esempio seguente viene illustrato come configurare i timeout su un'associazione in un file di configurazione.  
  
```xml  
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding openTimeout="00:10:00"
                 closeTimeout="00:10:00"
                 sendTimeout="00:10:00"
                 receiveTimeout="00:10:00">
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```  
  
 Per altre informazioni su queste impostazioni, vedere la documentazione per la classe <xref:System.ServiceModel.Channels.Binding>.  
  
### <a name="client-side-timeouts"></a>Timeout lato client  
 Sul lato client:  
  
1. SendTimeout: usata per inizializzare OperationTimeout, che definisce l'intero processo di invio di un messaggio, inclusa la ricezione di un messaggio di risposta per un'operazione del servizio request/reply. Questo timeout si applica anche quando si inviano messaggi di risposta da un metodo del contratto di callback.  
  
2. OpenTimeout – utilizzato quando si aprono i canali quando non è specificato alcun valore di timeout esplicito.  
  
3. CloseTimeout – utilizzato quando si chiudono i canali quando non è specificato alcun valore di timeout esplicito.  
  
4. ReceiveTimeout – non viene utilizzato.  
  
### <a name="service-side-timeouts"></a>Timeout sul lato del servizioService-side Timeouts  
 Sul lato servizio:  
  
1. SendTimeout, OpenTimeout, CloseTimeout sono gli stessi del client.  
  
2. ReceiveTimeout: usata a livello del framework dei servizi per inizializzare un timeout di sessione inattiva che controlla la possibile durata dell'inattività di una sessione prima del timeout.
