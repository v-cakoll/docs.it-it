---
title: 'Procedura: Ottenere informazioni su interfacce e protocolli'
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: fd88d26c-4063-495e-a253-736ac3e6b23f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: ae4eb38c72a7f7629cea0f8137a4337553457808
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200906"
---
# <a name="how-to-get-interface-and-protocol-information"></a><span data-ttu-id="0d8fc-102">Procedura: Ottenere informazioni su interfacce e protocolli</span><span class="sxs-lookup"><span data-stu-id="0d8fc-102">How to: Get Interface and Protocol Information</span></span>
<span data-ttu-id="0d8fc-103">Questo esempio mostra come leggere le statistiche TCP di un'interfaccia di rete.</span><span class="sxs-lookup"><span data-stu-id="0d8fc-103">This sample shows how to read the TCP statistics of a network interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d8fc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d8fc-104">Example</span></span>  
  
```  
public static void ShowTcpStatistics(NetworkInterfaceComponent version)  
{  
    IPGlobalProperties properties =  
          IPGlobalProperties.GetIPGlobalProperties();  
    TcpStatistics tcpstat = null;  
    Console.WriteLine("");  
    switch (version)  
    {  
        case NetworkInterfaceComponent.IPv4:  
             tcpstat = properties.GetTcpIPv4Statistics();  
            Console.WriteLine("TCP/IPv4 Statistics:");  
            break;  
        case NetworkInterfaceComponent.IPv6:  
            tcpstat = properties.GetTcpIPv6Statistics();  
            Console.WriteLine("TCP/IPv6 Statistics:");  
            break;  
        default:  
            throw new ArgumentException("version");  
            break;  
    }  
    Console.WriteLine("  Minimum Transmission Timeout. : {0}",   
        tcpstat.MinimumTransmissionTimeout);  
    Console.WriteLine("  Maximum Transmission Timeout. : {0}",   
        tcpstat.MaximumTransmissionTimeout);  
  
    Console.WriteLine("  Connection Data:");  
    Console.WriteLine("      Current : {0}",   
    tcpstat.CurrentConnections);  
    Console.WriteLine("      Cumulative : {0}",   
        tcpstat.CumulativeConnections);  
    Console.WriteLine("      Initiated  : {0}",   
        tcpstat.ConnectionsInitiated);  
    Console.WriteLine("      Accepted : {0}",   
        tcpstat.ConnectionsAccepted);  
    Console.WriteLine("      Failed Attempts : {0}",   
        tcpstat.FailedConnectionAttempts);  
    Console.WriteLine("      Reset : {0}",   
        tcpstat.ResetConnections);  
  
    Console.WriteLine("");  
    Console.WriteLine("  Segment Data:");  
    Console.WriteLine("      Received  ................... : {0}",   
        tcpstat.SegmentsReceived);  
    Console.WriteLine("      Sent : {0}",   
        tcpstat.SegmentsSent);  
    Console.WriteLine("      Retransmitted : {0}",   
        tcpstat.SegmentsResent);  
  
    Console.WriteLine("");  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d8fc-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0d8fc-105">Compiling the Code</span></span>  
 <span data-ttu-id="0d8fc-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d8fc-106">This example requires:</span></span>  
  
-   <span data-ttu-id="0d8fc-107">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="0d8fc-107">References to the **System.Net** namespace.</span></span>
