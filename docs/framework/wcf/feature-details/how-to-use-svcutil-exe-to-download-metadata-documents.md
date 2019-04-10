---
title: 'Procedura: Usare Svcutil.exe per scaricare documenti di metadati'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: cc9fc4acaeafe4583b1e85a24cab97af1689c638
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328348"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Procedura: Usare Svcutil.exe per scaricare documenti di metadati
È possibile utilizzare Svcutil.exe per scaricare i metadati dai servizi in esecuzione e salvarli in file locali. Per schemi URL HTTP e HTTPS, Svcutil.exe tenta di recuperare i metadati tramite WS-MetadataExchange e [Individuazione servizio Web XML](https://go.microsoft.com/fwlink/?LinkId=94950). Per tutti gli altri schemi URL, Svcutil.exe utilizza solo WS-MetadataExchange.  
  
 Per impostazione predefinita, Svcutil.exe utilizza le associazioni definite nella classe <xref:System.ServiceModel.Description.MetadataExchangeBindings>. Per configurare l'associazione utilizzata per WS-MetadataExchange, nel file di configurazione di Svcutil.exe (svcutil.exe.config) è necessario definire un endpoint client che utilizza il contratto `IMetadataExchange` e che ha lo stesso nome dello schema URI (Uniform Resource Identifier) dell'indirizzo dell'endpoint dei metadati.  
  
> [!CAUTION]
> Quando in esecuzione Svcutil.exe per ottenere i metadati per un servizio che espone due servizi diversi contratti che ognuno dei quali contiene un'operazione con lo stesso nome, Svcutil.exe viene visualizzato un errore indicante che, "Non è possibile ottenere i metadati da..." Ad esempio, se si dispone di un servizio che espone un contratto di servizio denominato `ICarService` che dispone di un'operazione `Get(Car c)` e lo stesso servizio espone un contratto di servizio denominato `IBookService` dotato di un'operazione `Get(Book b)`. Per risolvere il problema, effettuare una delle operazioni seguenti:
>
> - Rinominare una delle operazioni.
> - Impostare <xref:System.ServiceModel.OperationContractAttribute.Name%2A> su un nome diverso.
> - Impostare uno degli spazi dei nomi delle operazioni su uno spazio dei nomi diverso, utilizzando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Per scaricare metadati utilizzando Svcutil.exe  
  
1. Individuare lo strumento Svcutil.exe nel percorso seguente:  
  
     C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin  
  
2. Al prompt dei comandi, avviare lo strumento utilizzando il formato seguente.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Per scaricare i metadati, è necessario specificare l'opzione `/t:metadata`. In caso contrario, verranno generati il codice client e la configurazione.  
  
3. Il <`url`> argomento specifica l'URL a un endpoint del servizio che fornisce metadati o a un documento di metadati ospitato online. Il <`epr`> argomento specifica il percorso in un file XML contenente un WS-Addressing `EndpointAddress` per un endpoint di servizio che supporta WS-MetadataExchange.  
  
 Per altre opzioni sull'uso di questo strumento per il download dei metadati, vedere [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Esempio  
 Con il comando seguente vengono scaricati i documenti di metadati da un servizio in esecuzione.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Vedere anche

- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
