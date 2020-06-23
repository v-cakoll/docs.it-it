---
title: Configurazione dei valori di timeout per un'associazione
description: Informazioni su come gestire le impostazioni di timeout per i binding WCF per migliorare le prestazioni, l'usabilità e la sicurezza del servizio.
ms.date: 03/30/2017
ms.assetid: b5c825a2-b48f-444a-8659-61751ff11d34
ms.openlocfilehash: c41824a242d9b42290183cd70b9acf5b8ee59e6b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245115"
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
  
2. OpenTimeout: usato per l'apertura di canali quando non è specificato alcun valore di timeout esplicito.  
  
3. CloseTimeout: usato per chiudere i canali quando non è specificato alcun valore di timeout esplicito.  
  
4. ReceiveTimeout: non viene utilizzato.  
  
### <a name="service-side-timeouts"></a>Timeout lato servizio  
 Sul lato servizio:  
  
1. SendTimeout nell'elemento, OpenTimeout, CloseTimeout sono identici a quelli del client.  
  
2. ReceiveTimeout: usata a livello del framework dei servizi per inizializzare un timeout di sessione inattiva che controlla la possibile durata dell'inattività di una sessione prima del timeout.
