---
title: "Procedura: Rilevare la disponibilità della rete e le modifiche all'indirizzo"
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: d4377115-4a76-4848-ab23-4898d65c771c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: c0357c4000a7efdb838a40f2f3f907c1dd313c58
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2018
ms.locfileid: "47193122"
---
# <a name="how-to-detect-network-availability-and-address-changes"></a><span data-ttu-id="a9a51-102">Procedura: Rilevare la disponibilità della rete e le modifiche all'indirizzo</span><span class="sxs-lookup"><span data-stu-id="a9a51-102">How to: Detect Network Availability and Address Changes</span></span>
<span data-ttu-id="a9a51-103">Questo esempio mostra come rilevare le modifiche apportate all'indirizzo di rete di un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a9a51-103">This sample shows how to detect changes in the network address of an interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9a51-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9a51-104">Example</span></span>  
  
```  
using System;  
using System.Net;  
using System.Net.NetworkInformation;  
  
namespace Examples.Net.AddressChanges  
{  
    public class NetworkingExample  
    {  
        public static void Main()  
        {  
            NetworkChange.NetworkAddressChanged += new   
             NetworkAddressChangedEventHandler(AddressChangedCallback);  
            Console.WriteLine("Listening for address changes. Press any key to exit.");  
            Console.ReadLine();  
        }  
        static void AddressChangedCallback(object sender, EventArgs e)  
        {  
  
            NetworkInterface[] adapters = NetworkInterface.GetAllNetworkInterfaces();  
            foreach(NetworkInterface n in adapters)  
            {  
                Console.WriteLine("   {0} is {1}", n.Name, n.OperationalStatus);  
            }  
        }  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a9a51-105">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a9a51-105">Compiling the Code</span></span>  
 <span data-ttu-id="a9a51-106">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9a51-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a9a51-107">Riferimenti allo spazio dei nomi **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="a9a51-107">References to the **System.Net** namespace.</span></span>
