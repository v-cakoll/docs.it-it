---
title: Uso dei servizi UDP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 86f44c5aa4c744ab6966f0cb6b3834dd1f5f0f48
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="using-udp-services"></a>Uso dei servizi UDP
La classe <xref:System.Net.Sockets.UdpClient> comunica con i servizi di rete tramite UDP. Le proprietà e i metodi della classe <xref:System.Net.Sockets.UdpClient> ottengono un'astrazione dei dettagli della creazione di un <xref:System.Net.Sockets.Socket> per la richiesta e la ricezione di dati tramite UDP.  
  
 Il protocollo UDP (User Datagram Protocol) è un protocollo semplice che tenta di recapitare i dati a un host remoto. Tuttavia, poiché il protocollo UDP è un protocollo senza connessione, l'arrivo dei datagrammi UDP inviati all'endpoint remoto non è garantito, così come non è garantito che arrivino nella stessa sequenza con cui vengono inviati. Le applicazioni che usano UDP devono essere preparate a gestire i datagrammi mancanti, duplicati e fuori sequenza.  
  
 Per inviare un datagramma tramite UDP, è necessario conoscere l'indirizzo di rete del dispositivo di rete che ospita il servizio necessario e il numero della porta UDP usata dal servizio per comunicare. IANA (Internet Assigned Numbers Authority) definisce i numeri di porta per i servizi comuni (vedere www.iana.org/assignments/port-numbers). I servizi non presenti nell'elenco IANA possono avere numeri di porta nell'intervallo da 1.024 a 65.535.  
  
 Gli indirizzi di rete speciali vengono usati per supportare i messaggi trasmessi UDP su reti IP. Nelle informazioni seguenti viene usata la famiglia di indirizzi IP versione 4 usata in Internet a titolo di esempio.  
  
 Gli indirizzi IP versione 4 usano 32 bit per specificare un indirizzo di rete. Per gli indirizzi di classe C con una netmask 255.255.255.0, questi bit vengono suddivisi in quattro ottetti. Quando vengono espressi in formato decimale, i quattro ottetti formano la familiare notazione puntata costituita da quattro numeri, ad esempio 192.168.100.2. I primi due ottetti (192.168 in questo esempio) costituiscono il numero di rete, il terzo ottetto (100) definisce la subnet e l'ultimo ottetto (2) è l'identificatore dell'host.  
  
 L'impostazione di tutti i bit di un indirizzo IP su uno, o 255.255.255.255, costituisce l'indirizzo di trasmissione limitato. Se si invia un datagramma UDP a questo indirizzo, il messaggio viene recapitato a qualsiasi host nel segmento di rete locale. Dato che i router non inoltrano mai i messaggi inviati a questo indirizzo, solo gli host nel segmento di rete ricevono il messaggio trasmesso.  
  
 Le trasmissioni possono essere indirizzate a parti specifiche di una rete impostando tutti i bit dell'identificatore di host. Ad esempio, per inviare un messaggio trasmesso a tutti gli host della rete identificati dagli indirizzi IP che iniziano con 192.168.1, usare l'indirizzo 192.168.1.255.  
  
 L'esempio di codice seguente usa un <xref:System.Net.Sockets.UdpClient> per l'ascolto dei datagrammi UDP inviati all'indirizzo di broadcast diretto 192.168.1.255 sulla porta 11.000. Il client riceve una stringa di messaggio e scrive il messaggio nella console.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class UDPListener  
   Private Const listenPort As Integer = 11000  
  
   Private Shared Sub StartListener()  
      Dim done As Boolean = False  
      Dim listener As New UdpClient(listenPort)  
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)  
      Try  
         While Not done  
            Console.WriteLine("Waiting for broadcast")  
            Dim bytes As Byte() = listener.Receive(groupEP)  
            Console.WriteLine("Received broadcast from {0} :", _  
                groupEP.ToString())   
            Console.WriteLine( _  
                Encoding.ASCII.GetString(bytes, 0, bytes.Length))  
            Console.WriteLine()  
         End While  
      Catch e As Exception  
         Console.WriteLine(e.ToString())  
      Finally  
         listener.Close()  
      End Try  
   End Sub 'StartListener  
  
   Public Shared Function Main() As Integer  
      StartListener()  
      Return 0  
   End Function 'Main  
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
        bool done = false;  
  
        UdpClient listener = new UdpClient(listenPort);  
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any,listenPort);  
  
        try   
        {  
            while (!done)   
            {  
                Console.WriteLine("Waiting for broadcast");  
                byte[] bytes = listener.Receive( ref groupEP);  
  
                Console.WriteLine("Received broadcast from {0} :\n {1}\n",  
                    groupEP.ToString(),  
                    Encoding.ASCII.GetString(bytes,0,bytes.Length));  
            }  
  
        }   
        catch (Exception e)   
        {  
            Console.WriteLine(e.ToString());  
        }  
        finally  
        {  
            listener.Close();  
        }  
    }  
  
    public static int Main()   
    {  
        StartListener();  
  
        return 0;  
    }  
}  
```  
  
 L'esempio di codice seguente usa un <xref:System.Net.Sockets.UdpClient> per inviare datagrammi UDP all'indirizzo di broadcast diretto 192.168.1.255 usando la porta 11.000. Il client invia la stringa di messaggio specificata nella riga di comando.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class Program  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
          ProtocolType.Udp)  
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")  
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))  
      Dim ep As New IPEndPoint(broadcast, 11000)  
      s.SendTo(sendbuf, ep)  
      Console.WriteLine("Message sent to the broadcast address")  
   End Function 'Main  
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
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
            ProtocolType.Udp);  
  
        IPAddress broadcast = IPAddress.Parse("192.168.1.255");  
  
        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);  
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);  
  
        s.SendTo(sendbuf, ep);  
  
        Console.WriteLine("Message sent to the broadcast address");  
    }  
}  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.Sockets.UdpClient>  
 <xref:System.Net.IPAddress>  
 
