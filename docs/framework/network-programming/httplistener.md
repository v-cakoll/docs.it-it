---
title: HttpListener
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: db2c42dab15b4282c5474c50f970ffe47a101215
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393452"
---
# <a name="httplistener"></a>HttpListener
La classe <xref:System.Net.HttpListener> fornisce un listener del protocollo HTTP controllato a livello di codice. Il listener è attivo per la durata dell'oggetto <xref:System.Net.HttpListener> e viene eseguito all'interno dell'applicazione.  
  
## <a name="httpsys"></a>HTTP.SYS  
 La classe <xref:System.Net.HttpListener> si basa su HTTP.sys, il listener in modalità kernel che gestisce tutto il traffico HTTP per Windows. HTTP.sys fornisce la gestione della connessione, la limitazione della larghezza di banda e la registrazione del server Web. Usare lo strumento `HttpCfg.exe` per aggiungere i certificati SSL. Per altre informazioni, vedere la documentazione per lo strumento [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) nella documentazione relativa all'[API Server](http://go.microsoft.com/fwlink/?LinkID=178285).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 [HTTP Server](http://go.microsoft.com/fwlink/?LinkID=178285) (Server HTTP)  
 [Security Enhancements in Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286) (Miglioramenti della sicurezza in Internet Information Services)  
 [HttpListener ASPX Host Application Sample](http://go.microsoft.com/fwlink/?LinkID=179560) (Esempio di applicazione host ASPX HttpListener)  
 [HttpListener Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179558) (Esempio di tecnologia HttpListener)  
 [Esempi di programmazione di rete](../../../docs/framework/network-programming/network-programming-samples.md)
