---
title: Integrazione della memorizzazione nella cache di ASP.NET
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: 989f10defa3cde2885d9002b2189751dfe2b920a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587661"
---
# <a name="aspnet-caching-integration"></a>Integrazione della memorizzazione nella cache di ASP.NET
In questo esempio viene descritto come usare la cache di output ASP.NET con il modello di programmazione HTTP Web WCF. In questo argomento viene illustrata la funzionalità di integrazione della cache di output ASP.NET.  
  
## <a name="demonstrates"></a>Dimostrazione  
 Integrazione con la cache di output ASP.NET  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a>Discussione  
 L'esempio Usa il <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> ASP.NET di usare la cache di output con il servizio Windows Communication Foundation (WCF). <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> viene applicato alle operazioni del servizio e fornisce il profilo della cache in un file di configurazione che deve essere applicato alle risposte dell'operazione specifica.  
  
 Nel file Service.cs del progetto di servizio di esempio, sia la `GetCustomer` e `GetCustomers` operazioni sono contrassegnate con il <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, che fornisce il nome del profilo della cache "CacheFor60Seconds". Nel file Web. config del progetto Service il profilo della cache "CacheFor60Seconds" viene fornito con il <`caching`> dell'elemento <`system.web`>. Per questo profilo della cache, il valore della `duration` attributo è "60", pertanto le risposte associate a questo profilo vengono memorizzati nella cache nella cache di output ASP.NET per 60 secondi. Inoltre, per questo profilo della cache, il `varmByParam` attributo è impostato su "format" in questo caso richieste con valori diversi per il `format` query parametro della stringa hanno le relative risposte memorizzate nella cache separatamente. Del infine, il profilo della cache `varyByHeader` attributo è impostato su "Accept", in modo che le richieste con valori di intestazione Accept diversi hanno le relative risposte memorizzate nella cache separatamente.  
  
 Il file Program.cs nel progetto Client dimostra come è possibile creare tale client usando <xref:System.Net.HttpWebRequest>. È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio WCF. È anche possibile accedere al servizio utilizzando altre classi di .NET Framework, ad esempio la channel factory WCF e <xref:System.Net.WebClient>. Altri esempi in SDK (ad esempio la [servizio HTTP di base](../../../../docs/framework/wcf/samples/basic-http-service.md) esempio) illustrano come usare queste classi per comunicare con un servizio WCF.  
  
## <a name="to-run-the-sample"></a>Per eseguire l'esempio  
 L'esempio è costituito da tre progetti:  
  
- **Servizio**: Un progetto di applicazione Web che include un servizio WCF HTTP ospitato in ASP.NET.  
  
- **Client**: Progetto di applicazione console che effettua chiamate al servizio.  
  
- **Common**: Una libreria condivisa che contiene il tipo Customer usato dal servizio e client.  
  
 Quando viene eseguita l'applicazione console Client, il client effettua richieste al servizio e scrive le informazioni pertinenti dalle risposte nella finestra della console.  
  
#### <a name="to-run-the-sample"></a>Per eseguire l'esempio  
  
1. Aprire la soluzione per l'esempio relativo all'integrazione della memorizzazione nella cache di ASP.NET.  
  
2. Per compilare la soluzione, premere CTRL+MAIUSC+B.  
  
3. Se il **Esplora soluzioni** finestra non è già aperta, premere CTRL + W + S.  
  
4. Dal **Esplora soluzioni** a destra fare clic sulla **Service** del progetto e selezionare **Avvia nuova istanza**. Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.  
  
5. Dal **Esplora soluzioni** a destra fare clic sulla **Client** del progetto e selezionare **Avvia nuova istanza**.  
  
6. Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.  
  
7. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.  
  
8. Premere un tasto qualsiasi per chiudere l'applicazione console client.  
  
9. Premere MAIUSC+F5 per interrompere il debug del servizio.  
  
10. Nell'Area di notifica Windows, fare clic con il pulsante destro sull'icona del server di sviluppo ASP.NET e selezionare **arrestare**.
