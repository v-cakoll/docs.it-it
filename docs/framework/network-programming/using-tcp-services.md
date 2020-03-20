---
title: Uso dei servizi TCP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
ms.openlocfilehash: 3678586647dcf9c47b4494197fbf56cab865b3d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039484"
---
# <a name="using-tcp-services"></a><span data-ttu-id="c4bc0-102">Uso dei servizi TCP</span><span class="sxs-lookup"><span data-stu-id="c4bc0-102">Using TCP Services</span></span>

<span data-ttu-id="c4bc0-103">La classe <xref:System.Net.Sockets.TcpClient> richiede i dati da una risorsa Internet tramite TCP.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-103">The <xref:System.Net.Sockets.TcpClient> class requests data from an Internet resource using TCP.</span></span> <span data-ttu-id="c4bc0-104">I metodi e le proprietà di **TcpClient** ottengono un'astrazione dei dettagli per creare un <xref:System.Net.Sockets.Socket> per la richiesta e la ricezione di dati tramite TCP.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-104">The methods and properties of **TcpClient** abstract the details for creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using TCP.</span></span> <span data-ttu-id="c4bc0-105">Dato che la connessione al dispositivo remoto è rappresentata come flusso, i dati possono essere letti e scritti con le tecniche di gestione dei flussi di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-105">Because the connection to the remote device is represented as a stream, data can be read and written with .NET Framework stream-handling techniques.</span></span>

<span data-ttu-id="c4bc0-106">Il protocollo TCP stabilisce una connessione con un endpoint remoto e quindi usa tale connessione per inviare e ricevere pacchetti di dati.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-106">The TCP protocol establishes a connection with a remote endpoint and then uses that connection to send and receive data packets.</span></span> <span data-ttu-id="c4bc0-107">TCP è responsabile di garantire che i pacchetti di dati vengano inviati all'endpoint e assemblati nell'ordine corretto all'arrivo.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-107">TCP is responsible for ensuring that data packets are sent to the endpoint and assembled in the correct order when they arrive.</span></span>

<span data-ttu-id="c4bc0-108">Per stabilire una connessione TCP, è necessario conoscere l'indirizzo del dispositivo di rete che ospita il servizio necessario ed è necessario conoscere la porta TCP usata dal servizio per comunicare.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-108">To establish a TCP connection, you must know the address of the network device hosting the service you need and you must know the TCP port that the service uses to communicate.</span></span> <span data-ttu-id="c4bc0-109">IANA (Internet Assigned Numbers Authority) definisce i numeri di porta per i servizi comuni. Vedere [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registro dei numeri di porta per nomi di servizio e protocolli di trasporto).</span><span class="sxs-lookup"><span data-stu-id="c4bc0-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="c4bc0-110">I servizi non presenti nell'elenco IANA possono avere numeri di porta nell'intervallo da 1.024 a 65.535.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-110">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>

<span data-ttu-id="c4bc0-111">Nell'esempio seguente viene illustrata la configurazione di un TcpClient per la connessione a un server di database temporale sulla porta TCP 13:The following example demonstrates setting up a **TcpClient** to connect to a time server on TCP port 13:</span><span class="sxs-lookup"><span data-stu-id="c4bc0-111">The following example demonstrates setting up a **TcpClient** to connect to a time server on TCP port 13:</span></span>

```vb
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeClient
    Private const portNum As Integer = 13
    Private const hostName As String = "host.contoso.com"

    ' Entry point  that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Try
            Dim client As New TcpClient(hostName, portNum)

            Dim ns As NetworkStream = client.GetStream()

            Dim bytes(1024) As Byte
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)

            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))

        Catch e As Exception
            Console.WriteLine(e.ToString())
        End Try

        client.Close()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net.Sockets;
using System.Text;

public class TcpTimeClient
{
    private const int portNum = 13;
    private const string hostName = "host.contoso.com";

    public static int Main(String[] args)
    {
        try
        {
            var client = new TcpClient(hostName, portNum);

            NetworkStream ns = client.GetStream();

            byte[] bytes = new byte[1024];
            int bytesRead = ns.Read(bytes, 0, bytes.Length);

            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));

            client.Close();

        }
        catch (Exception e)
        {
            Console.WriteLine(e.ToString());
        }

        return 0;
    }
}
```

<span data-ttu-id="c4bc0-112"><xref:System.Net.Sockets.TcpListener>viene utilizzato per monitorare una porta TCP per le richieste in ingresso e quindi creare un **Socket** o un **TcpClient** che gestisce la connessione al client.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-112"><xref:System.Net.Sockets.TcpListener> is used to monitor a TCP port for incoming requests and then create either a **Socket** or a **TcpClient** that manages the connection to the client.</span></span> <span data-ttu-id="c4bc0-113">Il metodo <xref:System.Net.Sockets.TcpListener.Start%2A> abilita l'ascolto sulla porta e il metodo <xref:System.Net.Sockets.TcpListener.Stop%2A> lo disabilita.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-113">The <xref:System.Net.Sockets.TcpListener.Start%2A> method enables listening, and the <xref:System.Net.Sockets.TcpListener.Stop%2A> method disables listening on the port.</span></span> <span data-ttu-id="c4bc0-114">Il metodo <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> accetta le richieste di connessione in ingresso e crea un **TcpClient** per gestire la richiesta e il metodo <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> accetta le richieste di connessione in ingresso e crea un **Socket** per gestire la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-114">The <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> method accepts incoming connection requests and creates a **TcpClient** to handle the request, and the <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> method accepts incoming connection requests and creates a **Socket** to handle the request.</span></span>

<span data-ttu-id="c4bc0-115">L'esempio seguente dimostra la creazione di un server di riferimento ora di rete con **TcpListener** per monitorare la porta TCP 13.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-115">The following example demonstrates creating a network time server using a **TcpListener** to monitor TCP port 13.</span></span> <span data-ttu-id="c4bc0-116">Quando viene accettata una richiesta di connessione in ingresso, il server di riferimento ora risponde con la data e ora correnti dal server host.</span><span class="sxs-lookup"><span data-stu-id="c4bc0-116">When an incoming connection request is accepted, the time server responds with the current date and time from the host server.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeServer

    Private const portNum As Integer = 13

    ' Entry point that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Dim done As Boolean = False

        Dim listener As New TcpListener(IPAddress.Any, portNum)

        listener.Start()

        While Not done
            Console.Write("Waiting for connection...")
            Dim client As TcpClient = listener.AcceptTcpClient()

            Console.WriteLine("Connection accepted.")
            Dim ns As NetworkStream = client.GetStream()

            Dim byteTime As Byte() = _
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())

            Try
                ns.Write(byteTime, 0, byteTime.Length)
                ns.Close()
                client.Close()
            Catch e As Exception
                Console.WriteLine(e.ToString())
            End Try
        End While

        listener.Stop()

        Return 0
    End Function
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class TcpTimeServer
{

    private const int portNum = 13;

    public static int Main(String[] args)
    {
        bool done = false;

        var listener = new TcpListener(IPAddress.Any, portNum);

        listener.Start();

        while (!done)
        {
            Console.Write("Waiting for connection...");
            TcpClient client = listener.AcceptTcpClient();

            Console.WriteLine("Connection accepted.");
            NetworkStream ns = client.GetStream();

            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());

            try
            {
                ns.Write(byteTime, 0, byteTime.Length);
                ns.Close();
                client.Close();
            }
            catch (Exception e)
            {
                Console.WriteLine(e.ToString());
            }
        }

        listener.Stop();

        return 0;
    }

}
```
