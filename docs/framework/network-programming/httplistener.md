---
title: HttpListener
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b4b8c1e916aa9382d156a197fa15c2e72e900a1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="httplistener"></a>HttpListener
La classe <xref:System.Net.HttpListener> fornisce un listener del protocollo HTTP controllato a livello di codice. Il listener è attivo per la durata dell'oggetto <xref:System.Net.HttpListener> e viene eseguito all'interno dell'applicazione.  
  
## <a name="httpsys"></a>HTTP.SYS  
 La classe <xref:System.Net.HttpListener> si basa su HTTP.sys, il listener in modalità kernel che gestisce tutto il traffico HTTP per Windows. HTTP.sys fornisce la gestione della connessione, la limitazione della larghezza di banda e la registrazione del server Web. Usare lo strumento `HttpCfg.exe` per aggiungere i certificati SSL. Per altre informazioni, vedere la documentazione per lo strumento [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) nella documentazione relativa all'[API Server](http://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [Server HTTP](http://go.microsoft.com/fwlink/?LinkID=178285)  
 [Miglioramenti della sicurezza in Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286)  
 [HttpListener ASPX Host Application Sample](http://go.microsoft.com/fwlink/?LinkID=179560) (Esempio di applicazione host ASPX HttpListener)  
 [HttpListener Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179558) (Esempio di tecnologia HttpListener)  
 [Esempi di programmazione di rete](../../../docs/framework/network-programming/network-programming-samples.md)
