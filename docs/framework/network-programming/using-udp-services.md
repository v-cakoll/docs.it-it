---
title: Uso dei servizi UDP
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
ms.openlocfilehash: 477095ada6e44f66cbc60cd80375da9a87f38e39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180613"
---
# <a name="using-udp-services"></a>Uso dei servizi UDP
La classe <xref:System.Net.Sockets.UdpClient> comunica con i servizi di rete tramite UDP. Le proprietà e i metodi della classe <xref:System.Net.Sockets.UdpClient> ottengono un'astrazione dei dettagli della creazione di un <xref:System.Net.Sockets.Socket> per la richiesta e la ricezione di dati tramite UDP.

Il protocollo UDP (User Datagram Protocol) è un protocollo semplice che tenta di recapitare i dati a un host remoto. Tuttavia, poiché il protocollo UDP è un protocollo senza connessione, l'arrivo dei datagrammi UDP inviati all'endpoint remoto non è garantito, così come non è garantito che arrivino nella stessa sequenza con cui vengono inviati. Le applicazioni che usano UDP devono essere preparate a gestire i datagrammi mancanti, duplicati e fuori sequenza.

Per inviare un datagramma tramite UDP, è necessario conoscere l'indirizzo di rete del dispositivo di rete che ospita il servizio necessario e il numero della porta UDP usata dal servizio per comunicare. IANA (Internet Assigned Numbers Authority) definisce i numeri di porta per i servizi comuni. Vedere [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro dei numeri di porta per nomi di servizio e protocolli di trasporto). I servizi non presenti nell'elenco IANA possono avere numeri di porta nell'intervallo da 1.024 a 65.535.

Gli indirizzi di rete speciali vengono usati per supportare i messaggi trasmessi UDP su reti IP. Nelle informazioni seguenti viene usata la famiglia di indirizzi IP versione 4 usata in Internet a titolo di esempio.

Gli indirizzi IP versione 4 usano 32 bit per specificare un indirizzo di rete. Per gli indirizzi di classe C con una netmask 255.255.255.0, questi bit vengono suddivisi in quattro ottetti. Quando vengono espressi in formato decimale, i quattro ottetti formano la familiare notazione puntata costituita da quattro numeri, ad esempio 192.168.100.2. I primi due ottetti (192.168 in questo esempio) costituiscono il numero di rete, il terzo ottetto (100) definisce la subnet e l'ultimo ottetto (2) è l'identificatore dell'host.

L'impostazione di tutti i bit di un indirizzo IP su uno, o 255.255.255.255, costituisce l'indirizzo di trasmissione limitato. Se si invia un datagramma UDP a questo indirizzo, il messaggio viene recapitato a qualsiasi host nel segmento di rete locale. Dato che i router non inoltrano mai i messaggi inviati a questo indirizzo, solo gli host nel segmento di rete ricevono il messaggio trasmesso.

Le trasmissioni possono essere indirizzate a parti specifiche di una rete impostando tutti i bit dell'identificatore di host. Ad esempio, per inviare un messaggio trasmesso a tutti gli host della rete identificati dagli indirizzi IP che iniziano con 192.168.1, usare l'indirizzo 192.168.1.255.

Il codice dell'esempio seguente usa un elemento <xref:System.Net.Sockets.UdpClient> per ascoltare datagrammi UDP sulla porta 11.000. Il client riceve una stringa di messaggio e scrive il messaggio nella console.

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

L'esempio di codice seguente usa un <xref:System.Net.Sockets.Socket> per inviare datagrammi UDP all'indirizzo di broadcast diretto 192.168.1.255 usando la porta 11.000. Il client invia la stringa di messaggio specificata nella riga di comando.

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

## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
