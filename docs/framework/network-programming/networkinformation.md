---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: bc0604fd33d06521727c9aa0302ed313d8a2305f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "74428236"
---
# <a name="networkinformation"></a>NetworkInformation
Lo spazio dei nomi <xref:System.Net.NetworkInformation> consente di raccogliere informazioni sugli eventi, le modifiche, le statistiche e le proprietà della rete. È anche possibile determinare se un host remoto è raggiungibile tramite la classe <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType>.  
  
## <a name="network-availability-and-events"></a>Disponibilità ed eventi della rete  
 La classe <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> consente di determinare se l'indirizzo di rete o la disponibilità sono cambiati. Per usare questa classe, creare un gestore eventi per elaborare la modifica e associarlo a un <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> o <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>. Per altre informazioni, vedere [Procedura: Rilevare la disponibilità della rete e le modifiche all'indirizzo](how-to-detect-network-availability-and-address-changes.md).  
  
## <a name="network-statistics-and-properties"></a>Statistiche e proprietà della rete  
 È possibile raccogliere le statistiche e le proprietà della rete in base a un'interfaccia o a un protocollo. Le classi <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> e <xref:System.Net.NetworkInformation.PhysicalAddress> forniscono informazioni su una particolare interfaccia di rete, mentre le classi <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> e <xref:System.Net.NetworkInformation.UdpStatistics> offrono informazioni sui pacchetti del livello 3 e 4. Per altre informazioni, vedere [Procedura: Ottenere informazioni su interfacce e protocolli](how-to-get-interface-and-protocol-information.md).  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>Determinare se un host remoto è raggiungibile  
 È possibile usare la classe <xref:System.Net.NetworkInformation.Ping> per determinare se un host remoto è attivo, in rete e raggiungibile. Per altre informazioni, vedere [Procedura: Eseguire il ping di un host](how-to-ping-a-host.md).  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di programmazione di rete](network-programming-samples.md)

<!-- to-do: review sample links
- [Network Information Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Network%20Information)
- [NetStat Tool Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=NetStat%20Tool)
- [Ping Client Technology Sample](https://archive.msdn.microsoft.com/nclsamples/Wiki/View.aspx?title=Ping%20Client)
-->
