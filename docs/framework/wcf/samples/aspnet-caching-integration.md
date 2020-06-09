---
title: Integrazione della memorizzazione nella cache di ASP.NET
ms.date: 03/30/2017
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
ms.openlocfilehash: c541f3caad8a500b9fdb33d00b58706bac876e37
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594751"
---
# <a name="aspnet-caching-integration"></a>Integrazione della memorizzazione nella cache di ASP.NET

In questo esempio viene descritto come usare la cache di output ASP.NET con il modello di programmazione HTTP Web WCF. In questo argomento viene illustrata la funzionalità di integrazione della cache di output ASP.NET.

## <a name="demonstrates"></a>Dimostra

Integrazione con la cache di output ASP.NET

> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`

## <a name="discussion"></a>Discussione

Nell'esempio viene utilizzato <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> per utilizzare la memorizzazione nella cache dell'output ASP.NET con il servizio Windows Communication Foundation (WCF). <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> viene applicato alle operazioni del servizio e fornisce il profilo della cache in un file di configurazione che deve essere applicato alle risposte dell'operazione specifica.

Nel file Service.cs del progetto di servizio di esempio, entrambe le `GetCustomer` `GetCustomers` operazioni e sono contrassegnate con <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> , che fornisce il nome del profilo della cache "CacheFor60Seconds". Nel file Web. config del progetto di servizio, il profilo della cache "CacheFor60Seconds" viene fornito nell'elemento < `caching` > di < `system.web` >. Per questo profilo di cache, il valore dell' `duration` attributo è "60", quindi le risposte associate a questo profilo vengono memorizzate nella cache di output ASP.NET per 60 secondi. Per questo profilo della cache, inoltre, l' `varmByParam` attributo è impostato su "Format", pertanto le risposte alle richieste con valori diversi per il `format` parametro della stringa di query vengono memorizzate nella cache separatamente. Infine, l'attributo del profilo della cache `varyByHeader` è impostato su "Accept", pertanto le risposte alle richieste con valori di intestazione Accept diversi sono memorizzate nella cache separatamente.

Il file Program.cs nel progetto Client dimostra come è possibile creare tale client usando <xref:System.Net.HttpWebRequest>. È importante sottolineare che quella descritta è solo una delle modalità per accedere a un servizio WCF. È anche possibile accedere al servizio utilizzando altre classi .NET Framework come la channel factory WCF e <xref:System.Net.WebClient> . Altri esempi nell'SDK, ad esempio l'esempio di [servizio http di base](basic-http-service.md) , illustrano come usare queste classi per comunicare con un servizio WCF.

## <a name="to-run-the-sample"></a>Per eseguire l'esempio

L'esempio è costituito da tre progetti:

- **Servizio**: un progetto di applicazione Web che include un servizio HTTP WCF ospitato in ASP.NET.

- **Client**: un progetto di applicazione console che effettua chiamate al servizio.

- **Common**: una libreria condivisa che contiene il tipo di cliente utilizzato dal client e dal servizio.

Quando viene eseguita l'applicazione console Client, il client effettua richieste al servizio e scrive le informazioni pertinenti dalle risposte nella finestra della console.

#### <a name="to-run-the-sample"></a>Per eseguire l'esempio

1. Aprire la soluzione per l'esempio relativo all'integrazione della memorizzazione nella cache di ASP.NET.

2. Premere CTRL+MAIUSC+B per compilare la soluzione.

3. Se la finestra **Esplora soluzioni** non è già aperta, premere CTRL + W + S.

4. Nella finestra di **Esplora soluzioni** , fare clic con il pulsante destro del mouse sul progetto di **servizio** e scegliere **Avvia nuova istanza**. Verrà avviato il server di sviluppo ASP.NET che ospita il servizio.

5. Nella finestra di **Esplora soluzioni** , fare clic con il pulsante destro del mouse sul progetto **client** e scegliere **Avvia nuova istanza**.

6. Verrà visualizzata la finestra della console client in cui sono inclusi l'URI del servizio in esecuzione e l'URI della pagina della Guida HTML per il servizio in esecuzione. In qualsiasi momento è possibile visualizzare la pagina della Guida HTML digitando l'URI della pagina della Guida in un browser.

7. Durante l'esecuzione dell'esempio, il client scrive lo stato dell'attività corrente.

8. Premere un tasto qualsiasi per chiudere l'applicazione console client.

9. Premere MAIUSC+F5 per interrompere il debug del servizio.

10. Nell'area di notifica di Windows fare clic con il pulsante destro del mouse sull'icona del server di sviluppo ASP.NET e scegliere **Arresta**.
