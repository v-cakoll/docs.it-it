---
title: Integrazione della memorizzazione nella cache di ASP.NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d56c435088be383821d17250e230cae848d2bab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="aspnet-caching-integration"></a>Integrazione della memorizzazione nella cache di ASP.NET
In questo esempio viene descritto come usare la cache di output ASP.NET con il modello di programmazione HTTP Web WCF. Vedere il [servizio risorse di base](../../../../docs/framework/wcf/samples/basic-resource-service.md) esempio per una versione indipendente di questo scenario che illustra l'implementazione del servizio in modo approfondito. In questo argomento viene illustrata la funzionalità di integrazione della cache di output ASP.NET.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Integrazione con la cache di output ASP.NET  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a>Discussione  
 Nell'esempio viene usato <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> per la memorizzazione nella cache di output ASP.NET con il servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> viene applicato alle operazioni del servizio e fornisce il profilo della cache in un file di configurazione che deve essere applicato alle risposte dell'operazione specifica.  
  
 Nel file Service.cs del progetto di servizio di esempio, sia il `GetCustomer` e `GetCustomers` operazioni sono contrassegnate con il <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, che fornisce il nome del profilo della cache "CacheFor60Seconds". Nel file Web. config del progetto del servizio, il profilo della cache "CacheFor60Seconds" viene fornito con il <`caching`> dell'elemento di <`system.web`>. Per questo profilo di cache, il valore di `duration` attributo è "60", pertanto le risposte associate a questo profilo vengono memorizzati nella cache nella cache di output ASP.NET per 60 secondi. Inoltre, per questo profilo di cache di `varmByParam` attributo è impostato su "format" in questo caso richieste con valori diversi per il `format` query parametro stringa hanno le risposte memorizzate nella cache separatamente. Del infine, il profilo della cache `varyByHeader` attributo è impostato su "Accetto", in modo che le richieste con valori di intestazione Accept diversi delle risposte memorizzate nella cache separatamente.  
  
 Il file Program.cs nel progetto Client dimostra come è possibile creare tale client usando <xref:System.Net.HttpWebRequest>. È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio WCF. È infatti possibile accedere al servizio usando altre classi .NET Framework come la channel factory [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e <xref:System.Net.WebClient>. Altri esempi in SDK (ad esempio il [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) esempio e [la selezione automatica del formato](../../../../docs/framework/wcf/samples/automatic-format-selection.md) esempio) viene illustrato come utilizzare queste classi per comunicare con un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] servizio.  
  
## <a name="to-run-the-sample"></a>Per eseguire l'esempio  
 L'esempio è costituito da tre progetti:  
  
-   **Servizio**: progetto Web che include un servizio WCF HTTP ospitato in ASP.NET.  
  
-   **Client**: un progetto di applicazione console che effettua chiamate al servizio.  
  
-   **Comuni**: una libreria condivisa che contiene il tipo Customer usato dal client e servizio.  
  
 Quando viene eseguita l'applicazione console Client, il client effettua richieste al servizio e scrive le informazioni pertinenti dalle risposte nella finestra della console.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1.  Aprire la soluzione per l'esempio relativo all'integrazione della memorizzazione nella cache di ASP.NET.  
  
2.  Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3.  Se il **Esplora** finestra non è già aperta, premere CTRL + W + S.  
  
4.  Dal **Esplora** finestra fare clic destro la **servizio** del progetto e selezionare **Avvia nuova istanza**. Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.  
  
5.  Dal **Esplora** finestra fare clic destro la **Client** del progetto e selezionare **Avvia nuova istanza**.  
  
6.  Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.  
  
7.  Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
8.  Premere un tasto qualsiasi per chiudere l'applicazione console client.  
  
9. Premere MAIUSC+F5 per interrompere il debug del servizio.  
  
10. Nell'Area di notifica Windows, fare clic sull'icona del server di sviluppo ASP.NET e selezionare **arrestare**.
