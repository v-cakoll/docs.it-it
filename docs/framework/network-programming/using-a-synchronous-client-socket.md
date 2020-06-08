---
title: Uso di un socket client sincrono
description: Questo esempio mostra un socket client sincrono nella .NET Framework, che sospende il programma dell'applicazione durante il completamento dell'operazione di rete.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- synchronous client sockets
- Socket class, synchronous client sockets
- receiving data, sockets
- sockets, synchronous client sockets
- protocols, sockets
- Internet, sockets
- client sockets
ms.assetid: 945d00c6-7202-466c-9df9-140b84156d43
ms.openlocfilehash: ef682af33c10cf06ffc398c22e4a7dc1adf8290e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502067"
---
# <a name="using-a-synchronous-client-socket"></a><span data-ttu-id="e553e-103">Uso di un socket client sincrono</span><span class="sxs-lookup"><span data-stu-id="e553e-103">Using a Synchronous Client Socket</span></span>
<span data-ttu-id="e553e-104">Un socket client sincrono sospende il programma dell'applicazione in attesa del completamento dell'operazione di rete.</span><span class="sxs-lookup"><span data-stu-id="e553e-104">A synchronous client socket suspends the application program while the network operation completes.</span></span> <span data-ttu-id="e553e-105">I socket sincroni non sono adatti per le applicazioni che fanno un uso massiccio della rete per le loro operazioni, ma consentono di abilitare l'accesso semplice ai servizi di rete per altre applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e553e-105">Synchronous sockets are not suitable for applications that make heavy use of the network for their operation, but they can enable simple access to network services for other applications.</span></span>  
  
 <span data-ttu-id="e553e-106">Per l'invio di dati, passare una matrice di byte a uno dei metodi di invio dei dati della classe <xref:System.Net.Sockets.Socket> (<xref:System.Net.Sockets.Socket.Send%2A> e <xref:System.Net.Sockets.Socket.SendTo%2A>).</span><span class="sxs-lookup"><span data-stu-id="e553e-106">To send data, pass a byte array to one of the <xref:System.Net.Sockets.Socket> class's send-data methods (<xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.SendTo%2A>).</span></span> <span data-ttu-id="e553e-107">L'esempio seguente codifica una stringa in un buffer di matrice di byte usando la proprietà <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> e quindi trasmette il buffer al dispositivo di rete usando il metodo **Send**.</span><span class="sxs-lookup"><span data-stu-id="e553e-107">The following example encodes a string into a byte array buffer using the <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType> property and then transmits the buffer to the network device using the **Send** method.</span></span> <span data-ttu-id="e553e-108">Il metodo **Send** restituisce il numero di byte inviati al dispositivo di rete.</span><span class="sxs-lookup"><span data-stu-id="e553e-108">The **Send** method returns the number of bytes sent to the network device.</span></span>  
  
```vb  
Dim msg As Byte() = _  
    System.Text.Encoding.ASCII.GetBytes("This is a test.")  
Dim bytesSent As Integer = s.Send(msg)  
```  
  
```csharp  
byte[] msg = System.Text.Encoding.ASCII.GetBytes("This is a test");  
int bytesSent = s.Send(msg);  
```  
  
 <span data-ttu-id="e553e-109">Il metodo **Send** rimuove i byte dal buffer e li accoda con l'interfaccia di rete per l'invio al dispositivo di rete.</span><span class="sxs-lookup"><span data-stu-id="e553e-109">The **Send** method removes the bytes from the buffer and queues them with the network interface to be sent to the network device.</span></span> <span data-ttu-id="e553e-110">L'interfaccia di rete potrebbe non inviare i dati immediatamente, ma li invierà alla fine, a condizione che la connessione venga chiusa normalmente con il metodo <xref:System.Net.Sockets.Socket.Shutdown%2A>.</span><span class="sxs-lookup"><span data-stu-id="e553e-110">The network interface might not send the data immediately, but it will send it eventually, as long as the connection is closed normally with the <xref:System.Net.Sockets.Socket.Shutdown%2A> method.</span></span>  
  
 <span data-ttu-id="e553e-111">Per ricevere dati da un dispositivo di rete, passare un buffer a uno dei metodi per la ricezione dei dati della classe **Socket** (<xref:System.Net.Sockets.Socket.Receive%2A> e <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span><span class="sxs-lookup"><span data-stu-id="e553e-111">To receive data from a network device, pass a buffer to one of the **Socket** class's receive-data methods (<xref:System.Net.Sockets.Socket.Receive%2A> and <xref:System.Net.Sockets.Socket.ReceiveFrom%2A>).</span></span> <span data-ttu-id="e553e-112">I socket sincroni sospenderanno l'applicazione fino a quando i byte vengono ricevuti dalla rete o fino alla chiusura del socket.</span><span class="sxs-lookup"><span data-stu-id="e553e-112">Synchronous sockets will suspend the application until bytes are received from the network or until the socket is closed.</span></span> <span data-ttu-id="e553e-113">L'esempio seguente riceve dati dalla rete e successivamente li visualizza nella console.</span><span class="sxs-lookup"><span data-stu-id="e553e-113">The following example receives data from the network and then displays it on the console.</span></span> <span data-ttu-id="e553e-114">L'esempio presuppone che i dati provenienti dalla rete siano testo con codifica ASCII.</span><span class="sxs-lookup"><span data-stu-id="e553e-114">The example assumes that the data coming from the network is ASCII-encoded text.</span></span> <span data-ttu-id="e553e-115">Il metodo **Receive** restituisce il numero di byte ricevuti dalla rete.</span><span class="sxs-lookup"><span data-stu-id="e553e-115">The **Receive** method returns the number of bytes received from the network.</span></span>  
  
```vb  
Dim bytes(1024) As Byte  
Dim bytesRec = s.Receive(bytes)  
Console.WriteLine("Echoed text = {0}", _  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec))  
```  
  
```csharp  
byte[] bytes = new byte[1024];  
int bytesRec = s.Receive(bytes);  
Console.WriteLine("Echoed text = {0}",  
    System.Text.Encoding.ASCII.GetString(bytes, 0, bytesRec));  
```  
  
 <span data-ttu-id="e553e-116">Quando il socket non è più necessario, è necessario rilasciarlo chiamando il metodo <xref:System.Net.Sockets.Socket.Shutdown%2A> e poi il metodo **Close**.</span><span class="sxs-lookup"><span data-stu-id="e553e-116">When the socket is no longer needed, you need to release it by calling the <xref:System.Net.Sockets.Socket.Shutdown%2A> method and then calling the **Close** method.</span></span> <span data-ttu-id="e553e-117">L'esempio seguente illustra come rilasciare un **Socket**.</span><span class="sxs-lookup"><span data-stu-id="e553e-117">The following example releases a **Socket**.</span></span> <span data-ttu-id="e553e-118">L'enumerazione <xref:System.Net.Sockets.SocketShutdown> definisce le costanti che indicano se il socket deve essere chiuso per l'invio, per la ricezione o per entrambi.</span><span class="sxs-lookup"><span data-stu-id="e553e-118">The <xref:System.Net.Sockets.SocketShutdown> enumeration defines constants that indicate whether the socket should be closed for sending, for receiving, or for both.</span></span>  
  
```vb  
s.Shutdown(SocketShutdown.Both)  
s.Close()  
```  
  
```csharp  
s.Shutdown(SocketShutdown.Both);  
s.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="e553e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e553e-119">See also</span></span>

- [<span data-ttu-id="e553e-120">Uso di un socket client asincrono</span><span class="sxs-lookup"><span data-stu-id="e553e-120">Using an Asynchronous Client Socket</span></span>](using-an-asynchronous-client-socket.md)
- [<span data-ttu-id="e553e-121">Attesa con socket</span><span class="sxs-lookup"><span data-stu-id="e553e-121">Listening with Sockets</span></span>](listening-with-sockets.md)
- [<span data-ttu-id="e553e-122">Esempio di socket client sincrono</span><span class="sxs-lookup"><span data-stu-id="e553e-122">Synchronous Client Socket Example</span></span>](synchronous-client-socket-example.md)
