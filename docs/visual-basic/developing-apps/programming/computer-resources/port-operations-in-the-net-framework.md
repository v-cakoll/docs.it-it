---
title: Operazioni sulle porte in .NET Framework
ms.date: 07/20/2015
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
ms.openlocfilehash: 0ef0b8a7aec40603185d227d972cea655fd238c1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360137"
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a>Operazioni sulle porte in .NET Framework con Visual Basic

È possibile accedere alle porte seriali del computer attraverso le classi .NET Framework nello spazio nomi <xref:System.IO.Ports?displayProperty=nameWithType>. La classe più importante, <xref:System.IO.Ports.SerialPort>, fornisce un framework per l'I/O sincrono e basato su eventi, l'accesso agli stati di blocco e interruzione, l'accesso alle proprietà del driver seriale. È possibile eseguire il wrapping della classe in un oggetto <xref:System.IO.Stream>, accessibile attraverso la proprietà <xref:System.IO.Ports.SerialPort.BaseStream>. Il wrapping di <xref:System.IO.Ports.SerialPort> in un oggetto <xref:System.IO.Stream> consente di accedere alla porta seriale attraverso le classi che usano i flussi. Lo spazio dei nomi include le enumerazioni che semplificano il controllo delle porte seriali.

Il modo più semplice per creare un oggetto <xref:System.IO.Ports.SerialPort> consiste nell'usare il metodo <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.

> [!NOTE]
> Non è possibile usare le classi .NET Framework per accedere direttamente ad altri tipi di porte, quali le porte parallele, le porte USB e così via.

## <a name="enumerations"></a>Enumerazioni

In questa tabella sono elencate e descritte le enumerazioni principali usate per l'accesso alla porta seriale:

|Enumerazione|Descrizione|
|---|---|
|<xref:System.IO.Ports.Handshake>|Specifica il protocollo di controllo usato per stabilire la comunicazione della porta seriale per un oggetto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.Parity>|Specifica il bit di parità per un oggetto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialData>|Specifica il tipo di carattere ricevuto sulla porta seriale dell'oggetto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialError>|Specifica gli errori che si verificano nell'oggetto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.SerialPinChange>|Specifica il tipo di modifica eseguita nell'oggetto <xref:System.IO.Ports.SerialPort>.|
|<xref:System.IO.Ports.StopBits>|Specifica il numero di bit di interruzione usati nell'oggetto <xref:System.IO.Ports.SerialPort>.|

## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.Devices.Ports>
- [Accesso alle porte del computer](accessing-the-computer-s-ports.md)
