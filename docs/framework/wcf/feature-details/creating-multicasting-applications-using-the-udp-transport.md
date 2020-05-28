---
title: Creazione di applicazioni multicasting usando il trasporto UDP
ms.date: 03/30/2017
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
ms.openlocfilehash: 40944129ce3b01d8422d5aba4cfbf913c56265ed
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144630"
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a>Creazione di applicazioni multicasting usando il trasporto UDP
Le applicazioni multicasting inviano piccoli messaggi a numerosi destinatari contemporaneamente senza la necessità di stabilire connessioni punto a punto. In queste applicazioni viene data più importanza alla velocità che all'affidabilità. In altre parole, è più importante inviare dati in modo tempestivo che garantire l'effettiva ricezione degli specifici messaggi. In WCF è ora previsto il supporto della scrittura di applicazioni multicasting con <xref:System.ServiceModel.UdpBinding>. Questo trasporto è utile negli scenari in cui un servizio deve spedire contemporaneamente piccoli messaggi a una serie di client. Un'applicazione di teleborsa è un esempio di servizio di questo tipo.  
  
## <a name="implementing-a-multicast-application"></a>Implementazione di un'applicazione multicast  
 Per implementare un'applicazione multicast, definire un contratto di servizio e, per ogni componente software che deve rispondere ai messaggi multicast, implementare il contratto di servizio. Ad esempio, per un'applicazione di teleborsa potrebbe essere definito un contratto di servizio:  
  
```csharp
// Shared contracts between the client and the service  
[ServiceContract]
interface IStockTicker
{
    [OperationContract(IsOneWay = true)]
    void SendStockInfo(StockInfo[] stockInfo);
}

[DataContract]
class StockInfo
{
    [DataMember]
    public string Symbol;

    [DataMember]
    public float Price;

    public StockInfo(string symbol, float price)
    {
        this.Symbol = symbol;
        this.Price = price;
    }
}
```  
  
 In ogni applicazione in cui si desidera ricevere messaggi multicast deve essere ospitato un servizio che espone questa interfaccia.  Ad esempio, di seguito è riportato un esempio di codice che illustra come ricevere messaggi multicast:  
  
```csharp
// Service Address
string serviceAddress = "soap.udp://224.0.0.1:40000";
// Binding
UdpBinding myBinding = new UdpBinding();
// Host
ServiceHost host = new ServiceHost(typeof(StockTickerService), new Uri(serviceAddress));
// Add service endpoint
host.AddServiceEndpoint(typeof(IStockTicker), myBinding, string.Empty);
// Openup the service host
host.Open();

Console.WriteLine("Start receiving stock information");
Console.ReadLine();
```  
  
 Nell'applicazione viene specificato un indirizzo UDP a cui tutti i servizi saranno in attesa. Viene creato un nuovo oggetto <xref:System.ServiceModel.ServiceHost> e un endpoint del servizio viene esposto tramite <xref:System.ServiceModel.UdpBinding>. L'oggetto <xref:System.ServiceModel.ServiceHost> viene quindi aperto e inizierà l'attesa dei messaggi in arrivo.  
  
 In questo tipo di scenario è il client che invia effettivamente i messaggi multicast. Ogni servizio in attesa all'indirizzo UDP corretto riceverà i messaggi multicast. Di seguito è riportato un esempio di un client che invia i messaggi multicast:  
  
```csharp
// Multicast Address
string serviceAddress = "soap.udp://224.0.0.1:40000";

// Binding
UdpBinding myBinding = new UdpBinding();

// Channel factory
ChannelFactory<IStockTicker> factory
    = new ChannelFactory<IStockTicker>(myBinding,
                new EndpointAddress(serviceAddress));

// Call service
IStockTicker proxy = factory.CreateChannel();

while (true)
{
    // This will continue to mulicast stock information
    proxy.SendStockInfo(GetStockInfo());
    Console.WriteLine($"sent stock info at {DateTime.Now}");
    // Wait for one second before sending another update
    System.Threading.Thread.Sleep(new TimeSpan(0, 0, 1));
}
```  
  
 Questo codice genera informazioni sulla borsa e utilizza il contratto di servizio IStockTicker per inviare messaggi multicast di chiamata ai servizi in attesa all'indirizzo UDP corretto.  
  
### <a name="udp-and-reliable-messaging"></a>UDP e messaggistica affidabile  
  L'associazione UDP non supporta la messaggistica affidabile a causa della semplicità del protocollo UDP. Se è necessario verificare che i messaggi vengano ricevuti da un endpoint remoto, utilizzare un trasporto che supporti la messaggistica affidabile, come HTTP o TCP. Per ulteriori informazioni sulla messaggistica affidabile, vedere <https://go.microsoft.com/fwlink/?LinkId=231830> .  
  
### <a name="two-way-multicast-messaging"></a>Messaggistica multicast bidirezionale  
 Mentre i messaggi multicast sono generalmente unidirezionali, UdpBinding supporta lo scambio di messaggi request/reply. I messaggi inviati tramite il trasporto UDP contengono sia l'indirizzo del mittente sia quello del destinatario. È necessario prestare attenzione quando si utilizza l'indirizzo del mittente poiché potrebbe essere modificato in modo intenzionalmente dannoso durante il trasferimento.  L'indirizzo può essere controllato utilizzando il codice seguente:  
  
```csharp
if (address.AddressFamily == AddressFamily.InterNetwork)
{
    // IPv4
    byte[] addressBytes = address.GetAddressBytes();
    return ((addressBytes[0] & 0xE0) == 0xE0);
}
else
{
    // IPv6
    return address.IsIPv6Multicast;
}
```  
  
 Questo codice controlla il primo byte dell'indirizzo del mittente per verificare se contiene 0xE0, cioè se si tratta di un indirizzo multicast.  
  
### <a name="security-considerations"></a>Considerazioni relative alla sicurezza  
 Se si è in attesa di messaggi multicast, un pacchetto ICMP viene inviato al router per notificare che l'utente è in attesa all'indirizzo multicast. Chiunque disponga delle autorizzazioni nella subnet locale può essere in attesa di questi tipi di pacchetti e determinare l'indirizzo multicast e la porta su cui l'utente è in ascolto.  
  
 Non utilizzare l'indirizzo IP del mittente per nessun fine di sicurezza. Queste informazioni possono essere sottoposte a spoofing e possono causare l'invio di risposte al computer sbagliato da parte di un'applicazione. Un modo per limitare questa minaccia consiste nell'abilitare la sicurezza a livello di messaggio. A livello di rete, è possibile utilizzare anche IPSec (Internet Protocol Security) e/o Protezione accesso alla rete.
