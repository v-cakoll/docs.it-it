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
# <a name="httplistener"></a><span data-ttu-id="f768f-102">HttpListener</span><span class="sxs-lookup"><span data-stu-id="f768f-102">HttpListener</span></span>
<span data-ttu-id="f768f-103">La classe <xref:System.Net.HttpListener> fornisce un listener del protocollo HTTP controllato a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="f768f-103">The <xref:System.Net.HttpListener> class provides a programmatically controlled HTTP protocol listener.</span></span> <span data-ttu-id="f768f-104">Il listener è attivo per la durata dell'oggetto <xref:System.Net.HttpListener> e viene eseguito all'interno dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f768f-104">The listener is active for the lifetime of the <xref:System.Net.HttpListener> object and runs within your application.</span></span>  
  
## <a name="httpsys"></a><span data-ttu-id="f768f-105">HTTP.SYS</span><span class="sxs-lookup"><span data-stu-id="f768f-105">HTTP.SYS</span></span>  
 <span data-ttu-id="f768f-106">La classe <xref:System.Net.HttpListener> si basa su HTTP.sys, il listener in modalità kernel che gestisce tutto il traffico HTTP per Windows.</span><span class="sxs-lookup"><span data-stu-id="f768f-106">The <xref:System.Net.HttpListener> class is built on top of HTTP.sys, which is the kernel mode listener that handles all HTTP traffic for Windows.</span></span> <span data-ttu-id="f768f-107">HTTP.sys fornisce la gestione della connessione, la limitazione della larghezza di banda e la registrazione del server Web.</span><span class="sxs-lookup"><span data-stu-id="f768f-107">HTTP.sys provides connection management, bandwidth throttling, and Web server logging.</span></span> <span data-ttu-id="f768f-108">Usare lo strumento `HttpCfg.exe` per aggiungere i certificati SSL.</span><span class="sxs-lookup"><span data-stu-id="f768f-108">Use the `HttpCfg.exe` tool to add SSL certificates.</span></span> <span data-ttu-id="f768f-109">Per altre informazioni, vedere la documentazione per lo strumento [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) nella documentazione relativa all'[API Server](http://go.microsoft.com/fwlink/?LinkID=178285).</span><span class="sxs-lookup"><span data-stu-id="f768f-109">For more information, see the documentation on the [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) tool in the [Server](http://go.microsoft.com/fwlink/?LinkID=178285) documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f768f-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f768f-110">See Also</span></span>  
 <xref:System.Net.HttpListener>  
 <xref:System.Net.HttpWebRequest>  
 <xref:System.Net.HttpWebResponse>  
 <span data-ttu-id="f768f-111">[HTTP Server](http://go.microsoft.com/fwlink/?LinkID=178285) (Server HTTP)</span><span class="sxs-lookup"><span data-stu-id="f768f-111">[HTTP Server](http://go.microsoft.com/fwlink/?LinkID=178285)</span></span>  
 <span data-ttu-id="f768f-112">[Security Enhancements in Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286) (Miglioramenti della sicurezza in Internet Information Services)</span><span class="sxs-lookup"><span data-stu-id="f768f-112">[Security Enhancements in Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286)</span></span>  
 <span data-ttu-id="f768f-113">[HttpListener ASPX Host Application Sample](http://go.microsoft.com/fwlink/?LinkID=179560) (Esempio di applicazione host ASPX HttpListener)</span><span class="sxs-lookup"><span data-stu-id="f768f-113">[HttpListener ASPX Host Application Sample](http://go.microsoft.com/fwlink/?LinkID=179560)</span></span>  
 <span data-ttu-id="f768f-114">[HttpListener Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179558) (Esempio di tecnologia HttpListener)</span><span class="sxs-lookup"><span data-stu-id="f768f-114">[HttpListener Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179558)</span></span>  
 [<span data-ttu-id="f768f-115">Esempi di programmazione di rete</span><span class="sxs-lookup"><span data-stu-id="f768f-115">Network Programming Samples</span></span>](../../../docs/framework/network-programming/network-programming-samples.md)
