---
title: 'Procedura: usare Svcutil.exe per scaricare documenti di metadati'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 359cdb58ef65c9fb69c0ecfc759f70164a369cce
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212109"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Procedura: usare Svcutil.exe per scaricare documenti di metadati
È possibile utilizzare Svcutil.exe per scaricare i metadati dai servizi in esecuzione e salvarli in file locali. Per gli schemi URL HTTP e HTTPS, Svcutil. exe tenta di recuperare i metadati utilizzando WS-MetadataExchange e l' [individuazione del servizio Web XML](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100)). Per tutti gli altri schemi URL, Svcutil.exe utilizza solo WS-MetadataExchange.  
  
 Per impostazione predefinita, Svcutil.exe utilizza le associazioni definite nella classe <xref:System.ServiceModel.Description.MetadataExchangeBindings>. Per configurare l'associazione utilizzata per WS-MetadataExchange, nel file di configurazione di Svcutil.exe (svcutil.exe.config) è necessario definire un endpoint client che utilizza il contratto `IMetadataExchange` e che ha lo stesso nome dello schema URI (Uniform Resource Identifier) dell'indirizzo dell'endpoint dei metadati.  
  
> [!CAUTION]
> Quando si esegue Svcutil. exe per ottenere i metadati per un servizio che espone due contratti di servizio diversi che contengono ciascuno un'operazione con lo stesso nome, Svcutil. exe Visualizza un errore che informa che "non è possibile ottenere metadati da...". Se, ad esempio, si dispone di un servizio che espone un contratto di servizio denominato `ICarService` con un'operazione `Get(Car c)` e lo stesso servizio espone un contratto di servizio denominato `IBookService` che dispone di un'operazione `Get(Book b)`. Per risolvere il problema, effettuare una delle operazioni seguenti:
>
> - Rinominare una delle operazioni.
> - Impostare <xref:System.ServiceModel.OperationContractAttribute.Name%2A> su un nome diverso.
> - Impostare uno degli spazi dei nomi delle operazioni su uno spazio dei nomi diverso, utilizzando la proprietà <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.
  
## <a name="to-download-metadata-using-svcutilexe"></a>Per scaricare metadati utilizzando Svcutil.exe  
  
1. Individuare lo strumento Svcutil.exe nel percorso seguente:  
  
     C:\Program Files\Microsoft SDKs\Windows\v1.0.\bin  
  
2. Al prompt dei comandi, avviare lo strumento utilizzando il formato seguente.  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Per scaricare i metadati, è necessario specificare l'opzione `/t:metadata`. In caso contrario, verranno generati il codice client e la configurazione.  
  
3. L'argomento <`url`> specifica l'URL di un endpoint del servizio che fornisce metadati o a un documento di metadati ospitato online. L'argomento <`epr`> specifica il percorso di un file XML che contiene un `EndpointAddress` WS-Addressing per un endpoint del servizio che supporta WS-MetadataExchange.  
  
 Per altre opzioni sull'uso di questo strumento per il download dei metadati, vedere [ServiceModel Metadata Utility Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Esempio  
 Con il comando seguente vengono scaricati i documenti di metadati da un servizio in esecuzione.  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Vedere anche

- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
