---
title: Uso dei servizi UDP
description: La classe UdpClient astrae i dettagli per creare un socket per richiedere e ricevere dati tramite UDP nell'.NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- protocols, UDP
- network resources, UDP
- requesting data from Internet, UDP
- UDP
- receiving data, UDP
- Internet, UDP
- broadcasting messages to multiple addresses
- data requests, UDP
- UdpClient class, about UdpClient class
- sending data, UDP
- application protocols, UDP
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
ms.openlocfilehash: 4c2e88492f737800151d30097719d7d011054a5e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501950"
---
# <a name="use-udp-services"></a><span data-ttu-id="0941f-103">Usare i servizi UDP</span><span class="sxs-lookup"><span data-stu-id="0941f-103">Use UDP services</span></span>

<span data-ttu-id="0941f-104">La classe <xref:System.Net.Sockets.UdpClient> comunica con i servizi di rete tramite UDP.</span><span class="sxs-lookup"><span data-stu-id="0941f-104">The <xref:System.Net.Sockets.UdpClient> class communicates with network services using UDP.</span></span> <span data-ttu-id="0941f-105">Le proprietà e i metodi della classe <xref:System.Net.Sockets.UdpClient> ottengono un'astrazione dei dettagli della creazione di un <xref:System.Net.Sockets.Socket> per la richiesta e la ricezione di dati tramite UDP.</span><span class="sxs-lookup"><span data-stu-id="0941f-105">The properties and methods of the <xref:System.Net.Sockets.UdpClient> class abstract the details of creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using UDP.</span></span>

<span data-ttu-id="0941f-106">Il protocollo UDP (User Datagram Protocol) è un protocollo semplice che tenta di recapitare i dati a un host remoto.</span><span class="sxs-lookup"><span data-stu-id="0941f-106">User Datagram Protocol (UDP) is a simple protocol that makes a best effort to deliver data to a remote host.</span></span> <span data-ttu-id="0941f-107">Tuttavia, poiché il protocollo UDP è un protocollo senza connessione, l'arrivo dei datagrammi UDP inviati all'endpoint remoto non è garantito, così come non è garantito che arrivino nella stessa sequenza con cui vengono inviati.</span><span class="sxs-lookup"><span data-stu-id="0941f-107">However, because the UDP protocol is a connectionless protocol, UDP datagrams sent to the remote endpoint are not guaranteed to arrive, nor are they guaranteed to arrive in the same sequence in which they are sent.</span></span> <span data-ttu-id="0941f-108">Le applicazioni che usano UDP devono essere preparate a gestire i datagrammi mancanti, duplicati e fuori sequenza.</span><span class="sxs-lookup"><span data-stu-id="0941f-108">Applications that use UDP must be prepared to handle missing, duplicate, and out-of-sequence datagrams.</span></span>

<span data-ttu-id="0941f-109">Per inviare un datagramma tramite UDP, è necessario conoscere l'indirizzo di rete del dispositivo di rete che ospita il servizio necessario e il numero della porta UDP usata dal servizio per comunicare.</span><span class="sxs-lookup"><span data-stu-id="0941f-109">To send a datagram using UDP, you must know the network address of the network device hosting the service you need and the UDP port number that the service uses to communicate.</span></span> <span data-ttu-id="0941f-110">IANA (Internet Assigned Numbers Authority) definisce i numeri di porta per i servizi comuni (vedere il [nome del servizio e il numero di porta del protocollo di trasporto](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span><span class="sxs-lookup"><span data-stu-id="0941f-110">The Internet Assigned Numbers Authority (IANA) defines port numbers for common services (see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="0941f-111">I servizi non presenti nell'elenco IANA possono avere numeri di porta nell'intervallo compreso tra 1.024 e 65.535.</span><span class="sxs-lookup"><span data-stu-id="0941f-111">Services not on the IANA list can have port numbers in the range 1,024 to 65,535.</span></span>

<span data-ttu-id="0941f-112">Gli indirizzi di rete speciali vengono usati per supportare i messaggi trasmessi UDP su reti IP.</span><span class="sxs-lookup"><span data-stu-id="0941f-112">Special network addresses are used to support UDP broadcast messages on IP-based networks.</span></span> <span data-ttu-id="0941f-113">Nelle informazioni seguenti viene usata la famiglia di indirizzi IP versione 4 usata in Internet a titolo di esempio.</span><span class="sxs-lookup"><span data-stu-id="0941f-113">The following discussion uses the IP version 4 address family used on the Internet as an example.</span></span>

<span data-ttu-id="0941f-114">Gli indirizzi IP versione 4 usano 32 bit per specificare un indirizzo di rete.</span><span class="sxs-lookup"><span data-stu-id="0941f-114">IP version 4 addresses use 32 bits to specify a network address.</span></span> <span data-ttu-id="0941f-115">Per gli indirizzi di classe C con una netmask 255.255.255.0, questi bit vengono suddivisi in quattro ottetti.</span><span class="sxs-lookup"><span data-stu-id="0941f-115">For class C addresses using a netmask of 255.255.255.0, these bits are separated into four octets.</span></span> <span data-ttu-id="0941f-116">Quando vengono espressi in formato decimale, i quattro ottetti formano la familiare notazione puntata costituita da quattro numeri, ad esempio 192.168.100.2.</span><span class="sxs-lookup"><span data-stu-id="0941f-116">When expressed in decimal, the four octets form the familiar dotted-quad notation, such as 192.168.100.2.</span></span> <span data-ttu-id="0941f-117">I primi due ottetti (192.168 in questo esempio) costituiscono il numero di rete, il terzo ottetto (100) definisce la subnet e l'ultimo ottetto (2) è l'identificatore dell'host.</span><span class="sxs-lookup"><span data-stu-id="0941f-117">The first two octets (192.168 in this example) form the network number, the third octet (100) defines the subnet, and the final octet (2) is the host identifier.</span></span>

<span data-ttu-id="0941f-118">L'impostazione di tutti i bit di un indirizzo IP su uno, o 255.255.255.255, costituisce l'indirizzo di trasmissione limitato.</span><span class="sxs-lookup"><span data-stu-id="0941f-118">Setting all the bits of an IP address to one, or 255.255.255.255, forms the limited broadcast address.</span></span> <span data-ttu-id="0941f-119">Se si invia un datagramma UDP a questo indirizzo, il messaggio viene recapitato a qualsiasi host nel segmento di rete locale.</span><span class="sxs-lookup"><span data-stu-id="0941f-119">Sending a UDP datagram to this address delivers the message to any host on the local network segment.</span></span> <span data-ttu-id="0941f-120">Dato che i router non inoltrano mai i messaggi inviati a questo indirizzo, solo gli host nel segmento di rete ricevono il messaggio trasmesso.</span><span class="sxs-lookup"><span data-stu-id="0941f-120">Because routers never forward messages sent to this address, only hosts on the network segment receive the broadcast message.</span></span>

<span data-ttu-id="0941f-121">Le trasmissioni possono essere indirizzate a parti specifiche di una rete impostando tutti i bit dell'identificatore di host.</span><span class="sxs-lookup"><span data-stu-id="0941f-121">Broadcasts can be directed to specific portions of a network by setting all bits of the host identifier.</span></span> <span data-ttu-id="0941f-122">Ad esempio, per inviare un messaggio trasmesso a tutti gli host della rete identificati dagli indirizzi IP che iniziano con 192.168.1, usare l'indirizzo 192.168.1.255.</span><span class="sxs-lookup"><span data-stu-id="0941f-122">For example, to send a broadcast to all hosts on the network identified by IP addresses starting with 192.168.1, use the address 192.168.1.255.</span></span>

<span data-ttu-id="0941f-123">Il codice dell'esempio seguente usa un elemento <xref:System.Net.Sockets.UdpClient> per ascoltare datagrammi UDP sulla porta 11.000.</span><span class="sxs-lookup"><span data-stu-id="0941f-123">The following code example uses a <xref:System.Net.Sockets.UdpClient> to listen for UDP datagrams on port 11,000.</span></span> <span data-ttu-id="0941f-124">Il client riceve una stringa di messaggio e scrive il messaggio nella console.</span><span class="sxs-lookup"><span data-stu-id="0941f-124">The client receives a message string and writes the message to the console.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class UDPListener
   Private Const listenPort As Integer = 11000

   Private Shared Sub StartListener()
      Dim listener As New UdpClient(listenPort)
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)
      Try
         While True
            Console.WriteLine("Waiting for broadcast")
            Dim bytes As Byte() = listener.Receive(groupEP)
            Console.WriteLine("Received broadcast from {0} :", groupEP)
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytes.Length))
         End While
      Catch e As SocketException
         Console.WriteLine(e)
      Finally
         listener.Close()
      End Try
   End Sub 'StartListener

   Public Shared Sub Main()
      StartListener()
   End Sub 'Main
End Class 'UDPListener
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class UDPListener
{
    private const int listenPort = 11000;

    private static void StartListener()
    {
        UdpClient listener = new UdpClient(listenPort);
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any, listenPort);

        try
        {
            while (true)
            {
                Console.WriteLine("Waiting for broadcast");
                byte[] bytes = listener.Receive(ref groupEP);

                Console.WriteLine($"Received broadcast from {groupEP} :");
                Console.WriteLine($" {Encoding.ASCII.GetString(bytes, 0, bytes.Length)}");
            }
        }
        catch (SocketException e)
        {
            Console.WriteLine(e);
        }
        finally
        {
            listener.Close();
        }
    }

    public static void Main()
    {
        StartListener();
    }
}
```

<span data-ttu-id="0941f-125">L'esempio di codice seguente usa un <xref:System.Net.Sockets.Socket> per inviare datagrammi UDP all'indirizzo di broadcast diretto 192.168.1.255 usando la porta 11.000.</span><span class="sxs-lookup"><span data-stu-id="0941f-125">The following code example uses a <xref:System.Net.Sockets.Socket> to send UDP datagrams to the directed broadcast address 192.168.1.255, using port 11,000.</span></span> <span data-ttu-id="0941f-126">Il client invia la stringa di messaggio specificata nella riga di comando.</span><span class="sxs-lookup"><span data-stu-id="0941f-126">The client sends the message string specified on the command line.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class Program
    Public Shared Sub Main(args() As [String])
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp)
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))
      Dim ep As New IPEndPoint(broadcast, 11000)
      s.SendTo(sendbuf, ep)
      Console.WriteLine("Message sent to the broadcast address")
   End Sub 'Main
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

class Program
{
    static void Main(string[] args)
    {
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp);

        IPAddress broadcast = IPAddress.Parse("192.168.1.255");

        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);

        s.SendTo(sendbuf, ep);

        Console.WriteLine("Message sent to the broadcast address");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="0941f-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0941f-127">See also</span></span>

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
