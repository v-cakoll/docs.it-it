---
title: Creazione di richieste Internet
description: Informazioni su come le applicazioni creano istanze di WebRequest tramite il metodo WebRequest. Create, che crea una classe derivata basata sullo schema URI passato.
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
ms.openlocfilehash: 389c7bf5969eca4322aa680a6f28dec0b899709a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325640"
---
# <a name="create-internet-requests"></a>Creare richieste Internet

Le applicazioni creano istanze di <xref:System.Net.WebRequest> con il metodo <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>. <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>è un metodo statico che crea una classe derivata da <xref:System.Net.WebRequest> in base allo schema URI passato.  
  
## <a name="web-file-and-ftp-requests"></a>Richieste Web, file e FTP

.NET Framework fornisce la <xref:System.Net.HttpWebRequest> classe, derivata da `WebRequest` , per gestire le richieste HTTP e HTTPS. Nella maggior parte dei casi, la `WebRequest` classe fornisce tutte le proprietà necessarie per effettuare una richiesta. Tuttavia, se necessario, è possibile eseguire il cast di `WebRequest` oggetti creati dal `WebRequest.Create` metodo al `HttpWebRequest` tipo per accedere alle proprietà specifiche di http della richiesta. Analogamente, l' `HttpWebResponse` oggetto gestisce le risposte dalle richieste HTTP e HTTPS. Per accedere alle proprietà specifiche di HTTP dell' `HttpWebResponse` oggetto, è necessario eseguire il cast `WebResponse` degli oggetti al `HttpWebResponse` tipo.  
  
.NET Framework fornisce anche le <xref:System.Net.FileWebRequest> <xref:System.Net.FileWebResponse> classi e per gestire le richieste di risorse che usano lo schema URI "file:". Analogamente, sono disponibili le classi <xref:System.Net.FtpWebRequest> e <xref:System.Net.FtpWebResponse> per la gestione delle richieste di risorse che usano lo schema "ftp:". Se la richiesta riguarda una risorsa che usa uno di questi schemi, è possibile usare il `WebRequest.Create` metodo per ottenere un oggetto con cui eseguire la richiesta.  
  
Per gestire le richieste che usano altri protocolli a livello di applicazione, implementare classi specifiche del protocollo derivate da `WebRequest` e `WebResponse` . Per ulteriori informazioni, vedere [programmazione di protocolli di collegamento](programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>Vedi anche

- [Procedura: Richiedere dati con la classe WebRequest](how-to-request-data-using-the-webrequest-class.md)
- [Richiesta di dati](requesting-data.md)
