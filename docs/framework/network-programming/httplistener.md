---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
ms.openlocfilehash: d3fecb9fe78ca54f68d3c5a97dae5d5dd9fbb28d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075418"
---
# <a name="httplistener"></a>HttpListener
La classe <xref:System.Net.HttpListener> fornisce un listener del protocollo HTTP controllato a livello di codice. Il listener è attivo per la durata dell'oggetto <xref:System.Net.HttpListener> e viene eseguito all'interno dell'applicazione.  
  
## <a name="httpsys"></a>HTTP.SYS  
 La classe <xref:System.Net.HttpListener> si basa su HTTP.sys, il listener in modalità kernel che gestisce tutto il traffico HTTP per Windows. HTTP.sys fornisce la gestione della connessione, la limitazione della larghezza di banda e la registrazione del server Web. Usare lo strumento `HttpCfg.exe` per aggiungere i certificati SSL. Per altre informazioni, vedere la documentazione per lo strumento [HttpCfg.exe](https://go.microsoft.com/fwlink/?LinkID=178284) nella documentazione relativa all'[API Server](https://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.HttpWebResponse>
- [HTTP Server (Server HTTP)](https://go.microsoft.com/fwlink/?LinkID=178285)
- [Miglioramenti della sicurezza in Internet Information Services](https://go.microsoft.com/fwlink/?LinkID=178286)
- [HttpListener ASPX Host Application Sample (Esempio di applicazione host ASPX HttpListener)](https://go.microsoft.com/fwlink/?LinkID=179560)
- [Esempio di tecnologia HttpListener](https://go.microsoft.com/fwlink/?LinkID=179558)
- [Esempi di programmazione di rete](../../../docs/framework/network-programming/network-programming-samples.md)
