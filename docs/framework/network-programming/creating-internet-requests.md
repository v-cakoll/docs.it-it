---
title: Creazione di richieste Internet
description: Informazioni su come le applicazioni creano istanze di WebRequest tramite WebRequest. Create, un metodo statico che crea una classe derivata basata sullo schema URI passato.
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
ms.openlocfilehash: 598ef9d44737ef6b33af833cbfb7788170165588
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502626"
---
# <a name="creating-internet-requests"></a>Creazione di richieste Internet
Le applicazioni creano istanze di <xref:System.Net.WebRequest> con il metodo <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>. Questo è un metodo statico che crea una classe derivata da **WebRequest** in base allo schema URI passato.  
  
## <a name="web-file-and-ftp-requests"></a>Web, file e richieste FTP  
 .NET Framework contiene la classe <xref:System.Net.HttpWebRequest>, derivata da **WebRequest**, per gestire richieste HTTP e HTTPS. Nella maggior parte dei casi, la classe **WebRequest** fornisce tutte le proprietà necessarie per effettuare una richiesta. Se necessario, tuttavia, è possibile eseguire il cast degli oggetti **WebRequest** creati dal metodo **WebRequest.Create** al tipo **HttpWebRequest** per accedere alle proprietà specifiche di HTTP della richiesta. Analogamente, l'oggetto **HttpWebResponse** gestisce le risposte alle richieste provenienti da HTTP e da HTTPS. Per accedere alle proprietà specifiche di HTTP dell'oggetto **HttpWebResponse**, è necessario eseguire il cast degli oggetti **WebResponse** al tipo **HttpWebResponse**.  
  
 .NET Framework mette a disposizione anche le classi <xref:System.Net.FileWebRequest> e <xref:System.Net.FileWebResponse> per la gestione delle richieste di risorse che usano lo schema URI "file:". Analogamente, sono disponibili le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse> per la gestione delle richieste di risorse che usano lo schema "ftp:". Se la richiesta riguarda una risorsa che usa uno di questi schemi, è possibile usare il metodo **WebRequest** per ottenere un oggetto con cui effettuare la richiesta.  
  
 Per gestire le richieste che usano altri protocolli a livello di applicazione, è necessario implementare classi specifiche del protocollo derivate da **WebRequest** e **WebResponse**. Per ulteriori informazioni, vedere [programmazione di protocolli di collegamento](programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Richiedere dati con la classe WebRequest](how-to-request-data-using-the-webrequest-class.md)
- [Richiesta di dati](requesting-data.md)
