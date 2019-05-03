---
title: Creazione di richieste Internet
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 2a4915796310e4f6899d833f20bc5260e0ee032b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59171032"
---
# <a name="creating-internet-requests"></a>Creazione di richieste Internet
Le applicazioni creano istanze di <xref:System.Net.WebRequest> con il metodo <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>. Questo è un metodo statico che crea una classe derivata da **WebRequest** in base allo schema URI passato.  
  
## <a name="web-file-and-ftp-requests"></a>Web, file e richieste FTP  
 .NET Framework contiene la classe <xref:System.Net.HttpWebRequest>, derivata da **WebRequest**, per gestire richieste HTTP e HTTPS. Nella maggior parte dei casi, la classe **WebRequest** fornisce tutte le proprietà necessarie per effettuare una richiesta. Se necessario, tuttavia, è possibile eseguire il cast degli oggetti **WebRequest** creati dal metodo **WebRequest.Create** al tipo **HttpWebRequest** per accedere alle proprietà specifiche di HTTP della richiesta. Analogamente, l'oggetto **HttpWebResponse** gestisce le risposte alle richieste provenienti da HTTP e da HTTPS. Per accedere alle proprietà specifiche di HTTP dell'oggetto **HttpWebResponse**, è necessario eseguire il cast degli oggetti **WebResponse** al tipo **HttpWebResponse**.  
  
 .NET Framework mette a disposizione anche le classi <xref:System.Net.FileWebRequest> e <xref:System.Net.FileWebResponse> per la gestione delle richieste di risorse che usano lo schema "file:" URI. Analogamente, sono disponibili le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse> per la gestione delle richieste di risorse che usano lo schema "ftp:". Se la richiesta riguarda una risorsa che usa uno di questi schemi, è possibile usare il metodo **WebRequest** per ottenere un oggetto con cui effettuare la richiesta.  
  
 Per gestire le richieste che usano altri protocolli a livello di applicazione, è necessario implementare classi specifiche del protocollo derivate da **WebRequest** e **WebResponse**. Per altre informazioni, vedere [Programmazione di protocolli di collegamento](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Richiedere dati con la classe WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
- [Richiesta di dati](../../../docs/framework/network-programming/requesting-data.md)
