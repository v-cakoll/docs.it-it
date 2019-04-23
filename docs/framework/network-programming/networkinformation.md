---
title: NetworkInformation
ms.date: 03/30/2017
helpviewer_keywords:
- Network
ms.assetid: 31b44dd3-b903-4a48-8419-40419a3e4038
ms.openlocfilehash: 0820ad6a6d5000ef7ea575e856d883ba5325b1b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230980"
---
# <a name="networkinformation"></a>NetworkInformation
Lo spazio dei nomi <xref:System.Net.NetworkInformation> consente di raccogliere informazioni sugli eventi, le modifiche, le statistiche e le proprietà della rete. È anche possibile determinare se un host remoto è raggiungibile tramite la classe <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType>.  
  
## <a name="network-availability-and-events"></a>Disponibilità ed eventi della rete  
 La classe <xref:System.Net.NetworkInformation.NetworkChange?displayProperty=nameWithType> consente di determinare se l'indirizzo di rete o la disponibilità sono cambiati. Per usare questa classe, creare un gestore eventi per elaborare la modifica e associarlo a un <xref:System.Net.NetworkInformation.NetworkAddressChangedEventHandler> o <xref:System.Net.NetworkInformation.NetworkAvailabilityChangedEventHandler>. Per altre informazioni, vedere [Procedura: Rilevare la disponibilità della rete e le modifiche all'indirizzo](../../../docs/framework/network-programming/how-to-detect-network-availability-and-address-changes.md).  
  
## <a name="network-statistics-and-properties"></a>Statistiche e proprietà della rete  
 È possibile raccogliere le statistiche e le proprietà della rete in base a un'interfaccia o a un protocollo. Le classi <xref:System.Net.NetworkInformation.NetworkInterface>, <xref:System.Net.NetworkInformation.NetworkInterfaceType> e <xref:System.Net.NetworkInformation.PhysicalAddress> forniscono informazioni su una particolare interfaccia di rete, mentre le classi <xref:System.Net.NetworkInformation.IPInterfaceProperties>, <xref:System.Net.NetworkInformation.IPGlobalProperties>, <xref:System.Net.NetworkInformation.IPGlobalStatistics>, <xref:System.Net.NetworkInformation.TcpStatistics> e <xref:System.Net.NetworkInformation.UdpStatistics> offrono informazioni sui pacchetti del livello 3 e 4. Per altre informazioni, vedere [Procedura: Ottenere informazioni su interfacce e protocolli](../../../docs/framework/network-programming/how-to-get-interface-and-protocol-information.md).  
  
## <a name="determine-if-a-remote-host-is-reachable"></a>Determinare se un host remoto è raggiungibile  
 È possibile usare la classe <xref:System.Net.NetworkInformation.Ping> per determinare se un host remoto è attivo, in rete e raggiungibile. Per altre informazioni, vedere [Procedura: Eseguire il ping di un host](../../../docs/framework/network-programming/how-to-ping-a-host.md).  
  
## <a name="see-also"></a>Vedere anche

- [Esempi di programmazione di rete](../../../docs/framework/network-programming/network-programming-samples.md)
- [Esempio di tecnologia per le informazioni di rete](https://go.microsoft.com/fwlink/?LinkID=179564)
- [Esempio di tecnologia NetStatTool](https://go.microsoft.com/fwlink/?LinkID=179562)
- [Esempio di tecnologia client ping](https://go.microsoft.com/fwlink/?LinkID=179565)
