---
title: Creazione di applicazioni multicasting usando il trasporto UDP
ms.date: 03/30/2017
ms.assetid: 7485154a-6e85-4a67-a9d4-9008e741d4df
ms.openlocfilehash: 6825aaafe87ae362fd9266f7c7a82a36d054a69f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185249"
---
# <a name="creating-multicasting-applications-using-the-udp-transport"></a><span data-ttu-id="73fc9-102">Creazione di applicazioni multicasting usando il trasporto UDP</span><span class="sxs-lookup"><span data-stu-id="73fc9-102">Creating Multicasting Applications using the UDP Transport</span></span>
<span data-ttu-id="73fc9-103">Le applicazioni multicasting inviano piccoli messaggi a numerosi destinatari contemporaneamente senza la necessità di stabilire connessioni punto a punto.</span><span class="sxs-lookup"><span data-stu-id="73fc9-103">Multicasting applications send small messages to a large number of recipients at the same time without the need to establish point to point connections.</span></span> <span data-ttu-id="73fc9-104">In queste applicazioni viene data più importanza alla velocità che all'affidabilità.</span><span class="sxs-lookup"><span data-stu-id="73fc9-104">The emphasis of such applications is speed over reliability.</span></span> <span data-ttu-id="73fc9-105">In altre parole, è più importante inviare dati in modo tempestivo che garantire l'effettiva ricezione degli specifici messaggi.</span><span class="sxs-lookup"><span data-stu-id="73fc9-105">In other words, it is more important to send timely data than to ensure any specific message is actually received.</span></span> <span data-ttu-id="73fc9-106">In WCF è ora previsto il supporto della scrittura di applicazioni multicasting con <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="73fc9-106">WCF now supports writing multicasting applications using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="73fc9-107">Questo trasporto è utile negli scenari in cui un servizio deve spedire contemporaneamente piccoli messaggi a una serie di client.</span><span class="sxs-lookup"><span data-stu-id="73fc9-107">This transport is useful in scenarios where a service needs to send out small messages to a number of clients simultaneously.</span></span> <span data-ttu-id="73fc9-108">Un'applicazione di teleborsa è un esempio di servizio di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="73fc9-108">A stock ticker application is an example of such a service.</span></span>  
  
## <a name="implementing-a-multicast-application"></a><span data-ttu-id="73fc9-109">Implementazione di un'applicazione multicast</span><span class="sxs-lookup"><span data-stu-id="73fc9-109">Implementing a Multicast Application</span></span>  
 <span data-ttu-id="73fc9-110">Per implementare un'applicazione multicast, definire un contratto di servizio e, per ogni componente software che deve rispondere ai messaggi multicast, implementare il contratto di servizio.</span><span class="sxs-lookup"><span data-stu-id="73fc9-110">To implement a multicast application, define a service contract and for each software component that needs to respond to the multicast messages, implement the service contract.</span></span> <span data-ttu-id="73fc9-111">Ad esempio, per un'applicazione di teleborsa potrebbe essere definito un contratto di servizio:</span><span class="sxs-lookup"><span data-stu-id="73fc9-111">For example, a stock ticker application might define a service contract:</span></span>  
  
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
  
 <span data-ttu-id="73fc9-112">In ogni applicazione in cui si desidera ricevere messaggi multicast deve essere ospitato un servizio che espone questa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="73fc9-112">Each application that wants to receive multicast messages must host a service that exposes this interface.</span></span>  <span data-ttu-id="73fc9-113">Ad esempio, di seguito è riportato un esempio di codice che illustra come ricevere messaggi multicast:</span><span class="sxs-lookup"><span data-stu-id="73fc9-113">For example, here is a code sample that illustrates how to receive multicast messages:</span></span>  
  
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
  
 <span data-ttu-id="73fc9-114">Nell'applicazione viene specificato un indirizzo UDP a cui tutti i servizi saranno in attesa.</span><span class="sxs-lookup"><span data-stu-id="73fc9-114">The application specifies the UDP address that all services will be listening on.</span></span> <span data-ttu-id="73fc9-115">Viene creato un nuovo oggetto <xref:System.ServiceModel.ServiceHost> e un endpoint del servizio viene esposto tramite <xref:System.ServiceModel.UdpBinding>.</span><span class="sxs-lookup"><span data-stu-id="73fc9-115">A new <xref:System.ServiceModel.ServiceHost> is created and a service endpoint is exposed using the <xref:System.ServiceModel.UdpBinding>.</span></span> <span data-ttu-id="73fc9-116">L'oggetto <xref:System.ServiceModel.ServiceHost> viene quindi aperto e inizierà l'attesa dei messaggi in arrivo.</span><span class="sxs-lookup"><span data-stu-id="73fc9-116">The <xref:System.ServiceModel.ServiceHost> is then opened and will start listening for incoming messages.</span></span>  
  
 <span data-ttu-id="73fc9-117">In questo tipo di scenario è il client che invia effettivamente i messaggi multicast.</span><span class="sxs-lookup"><span data-stu-id="73fc9-117">In this type of a scenario it is the client that actually sends out multicast messages.</span></span> <span data-ttu-id="73fc9-118">Ogni servizio in attesa all'indirizzo UDP corretto riceverà i messaggi multicast.</span><span class="sxs-lookup"><span data-stu-id="73fc9-118">Each service that is listening at the correct UDP address will receive the multicast messages.</span></span> <span data-ttu-id="73fc9-119">Di seguito è riportato un esempio di un client che invia i messaggi multicast:</span><span class="sxs-lookup"><span data-stu-id="73fc9-119">Here is an example of a client that sends out multicast messages:</span></span>  
  
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
  
 <span data-ttu-id="73fc9-120">Questo codice genera informazioni sulla borsa e utilizza il contratto di servizio IStockTicker per inviare messaggi multicast di chiamata ai servizi in attesa all'indirizzo UDP corretto.</span><span class="sxs-lookup"><span data-stu-id="73fc9-120">This code generates stock information and then uses the service contract IStockTicker to send multicast messages to call services listening on the correct UDP address.</span></span>  
  
### <a name="udp-and-reliable-messaging"></a><span data-ttu-id="73fc9-121">UDP e messaggistica affidabile</span><span class="sxs-lookup"><span data-stu-id="73fc9-121">UDP and Reliable Messaging</span></span>  
 <span data-ttu-id="73fc9-122">L'associazione UDP non supporta la messaggistica affidabile a causa della semplicità del protocollo UDP.</span><span class="sxs-lookup"><span data-stu-id="73fc9-122">The UDP binding does not support reliable messaging because of the lightweight nature of the UDP protocol.</span></span> <span data-ttu-id="73fc9-123">Se è necessario verificare che i messaggi vengano ricevuti da un endpoint remoto, utilizzare un trasporto che supporti la messaggistica affidabile, come HTTP o TCP.</span><span class="sxs-lookup"><span data-stu-id="73fc9-123">If you need to confirm that messages are received by a remote endpoint, use a transport that supports reliable messaging like  HTTP or TCP.</span></span> <span data-ttu-id="73fc9-124">Per ulteriori informazioni sulla messaggistica affidabile, vederehttps://go.microsoft.com/fwlink/?LinkId=231830</span><span class="sxs-lookup"><span data-stu-id="73fc9-124">For more information about reliable messaging see https://go.microsoft.com/fwlink/?LinkId=231830</span></span>  
  
### <a name="two-way-multicast-messaging"></a><span data-ttu-id="73fc9-125">Messaggistica multicast bidirezionale</span><span class="sxs-lookup"><span data-stu-id="73fc9-125">Two-way Multicast Messaging</span></span>  
 <span data-ttu-id="73fc9-126">Mentre i messaggi multicast sono generalmente unidirezionali, UdpBinding supporta lo scambio di messaggi request/reply.</span><span class="sxs-lookup"><span data-stu-id="73fc9-126">While multicast messages are generally one-way, the UdpBinding does support request/reply message exchange.</span></span> <span data-ttu-id="73fc9-127">I messaggi inviati tramite il trasporto UDP contengono sia l'indirizzo del mittente sia quello del destinatario.</span><span class="sxs-lookup"><span data-stu-id="73fc9-127">Messages sent using the UDP transport contain both a From and To address.</span></span> <span data-ttu-id="73fc9-128">È necessario prestare attenzione quando si utilizza l'indirizzo del mittente poiché potrebbe essere modificato in modo intenzionalmente dannoso durante il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="73fc9-128">Care must be taken when using the From address as it could be maliciously changed en-route.</span></span>  <span data-ttu-id="73fc9-129">L'indirizzo può essere controllato utilizzando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="73fc9-129">The address can be checked using the following code:</span></span>  
  
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
  
 <span data-ttu-id="73fc9-130">Questo codice controlla il primo byte dell'indirizzo del mittente per verificare se contiene 0xE0, cioè se si tratta di un indirizzo multicast.</span><span class="sxs-lookup"><span data-stu-id="73fc9-130">This code checks the first byte of the From address to see if it contains 0xE0 which signifies that the address is a multi-cast address.</span></span>  
  
### <a name="security-considerations"></a><span data-ttu-id="73fc9-131">Considerazioni relative alla sicurezza</span><span class="sxs-lookup"><span data-stu-id="73fc9-131">Security Considerations</span></span>  
 <span data-ttu-id="73fc9-132">Se si è in attesa di messaggi multicast, un pacchetto ICMP viene inviato al router per notificare che l'utente è in attesa all'indirizzo multicast.</span><span class="sxs-lookup"><span data-stu-id="73fc9-132">When listening for multicast messages an ICMP packet is sent to the router notifying it you are listening on the multicast address.</span></span> <span data-ttu-id="73fc9-133">Chiunque disponga delle autorizzazioni nella subnet locale può essere in attesa di questi tipi di pacchetti e determinare l'indirizzo multicast e la porta su cui l'utente è in ascolto.</span><span class="sxs-lookup"><span data-stu-id="73fc9-133">Anyone on the local subnet who has permissions could listen for these types of packets and determine which multicast address and port you are listening on.</span></span>  
  
 <span data-ttu-id="73fc9-134">Non utilizzare l'indirizzo IP del mittente per nessun fine di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="73fc9-134">Do not use the IP address of the sender for any security purposes.</span></span> <span data-ttu-id="73fc9-135">Queste informazioni possono essere sottoposte a spoofing e possono causare l'invio di risposte al computer sbagliato da parte di un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="73fc9-135">This information can be spoofed and can cause an application to send responses to the wrong machine.</span></span> <span data-ttu-id="73fc9-136">Un modo per limitare questa minaccia consiste nell'abilitare la sicurezza a livello di messaggio.</span><span class="sxs-lookup"><span data-stu-id="73fc9-136">One way to mitigate this threat is to enable message level security.</span></span> <span data-ttu-id="73fc9-137">A livello di rete, è possibile utilizzare anche IPSec (Internet Protocol Security) e/o Protezione accesso alla rete.</span><span class="sxs-lookup"><span data-stu-id="73fc9-137">At the network level IPSec  (Internet Protocol Security) and/or NAP (Network Access Protection) could also be used.</span></span>
