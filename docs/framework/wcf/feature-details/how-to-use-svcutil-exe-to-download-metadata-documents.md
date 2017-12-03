---
title: 'Procedura: usare Svcutil.exe per scaricare documenti di metadati'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6868bbecd83305c07e0b547d0102d7bca48d41f8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Procedura: usare Svcutil.exe per scaricare documenti di metadati
È possibile utilizzare Svcutil.exe per scaricare i metadati dai servizi in esecuzione e salvarli in file locali. Per gli schemi URL HTTP e HTTPS, Svcutil.exe tenta di recuperare i metadati utilizzando WS-MetadataExchange e [individuazione del servizio Web XML](http://go.microsoft.com/fwlink/?LinkId=94950). Per tutti gli altri schemi URL, Svcutil.exe utilizza solo WS-MetadataExchange.  
  
 Per impostazione predefinita, Svcutil.exe utilizza le associazioni definite nella classe <xref:System.ServiceModel.Description.MetadataExchangeBindings>. Per configurare l'associazione utilizzata per WS-MetadataExchange, nel file di configurazione di Svcutil.exe (svcutil.exe.config) è necessario definire un endpoint client che utilizza il contratto `IMetadataExchange` e che ha lo stesso nome dello schema URI (Uniform Resource Identifier) dell'indirizzo dell'endpoint dei metadati.  
  
> [!CAUTION]
>  Quando si esegue Svcutil.exe per ottenere i metadati per un servizio che espone due metodi di servizio diverso i contratti che ognuno dei quali contiene un'operazione con lo stesso nome, Svcutil.exe viene visualizzato un errore indicante che, "Impossibile ottenere i metadati da..." Ad esempio, se si dispone di un servizio che espone un contratto di servizio denominato ICarService con un'operazione Get (Car c) e lo stesso servizio espone un contratto di servizio denominato IBookService con un'operazione Get (Book b). Per risolvere il problema, effettuare una delle operazioni seguenti:  
>   
>  -   Rinominare una delle operazioni.  
> -   Impostare <xref:System.ServiceModel.OperationContractAttribute.Name%2A> su un nome diverso.  
> -   Impostare uno degli spazi dei nomi delle operazioni su uno spazio dei nomi diverso, utilizzando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.  
  
### <a name="to-download-metadata-using-svcutilexe"></a>Per scaricare metadati utilizzando Svcutil.exe  
  
1.  Individuare lo strumento Svcutil.exe nel percorso seguente:  
  
     C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin  
  
2.  Al prompt dei comandi, avviare lo strumento utilizzando il formato seguente.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Per scaricare i metadati, è necessario specificare l'opzione `/t:metadata`. In caso contrario, verranno generati il codice client e la configurazione.  
  
3.  Il <`url`> argomento specifica l'URL a un endpoint di servizio che fornisce metadati o a un documento di metadati ospitato online. Il <`epr`> argomento specifica il percorso in un file XML contenente WS-Addressing `EndpointAddress` per un endpoint di servizio che supporta WS-MetadataExchange.  
  
 Per altre opzioni sull'utilizzo di questo strumento per il download dei metadati, vedere [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Esempio  
 Con il comando seguente vengono scaricati i documenti di metadati da un servizio in esecuzione.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
