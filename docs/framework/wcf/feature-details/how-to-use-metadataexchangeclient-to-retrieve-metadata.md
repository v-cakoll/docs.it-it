---
title: 'Procedura: usare MetadataExchangeClient per il recupero di metadati'
ms.date: 03/30/2017
ms.assetid: 0754e9dc-13c5-45c2-81b5-f3da466e5a87
ms.openlocfilehash: 1df4bc156485108dc0c11d597b268864c9656b1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-metadataexchangeclient-to-retrieve-metadata"></a>Procedura: usare MetadataExchangeClient per il recupero di metadati
Utilizzare la classe <xref:System.ServiceModel.Description.MetadataExchangeClient> per scaricare metadati utilizzando il protocollo WS-MetadataExchange (MEX). I file dei metadati recuperati vengono restituiti come oggetti <xref:System.ServiceModel.Description.MetadataSet>. L'oggetto <xref:System.ServiceModel.Description.MetadataSet> restituito contiene una raccolta di oggetti <xref:System.ServiceModel.Description.MetadataSection>, ognuno dei quali contiene a sua volta un sottolinguaggio dei metadati specifici e un identificatore. I metadati restituiti possono essere scritti in file o, se contengono documenti WSDL (Web Services Description Language), possono essere importati utilizzando <xref:System.ServiceModel.Description.WsdlImporter>.  
  
 I costruttori <xref:System.ServiceModel.Description.MetadataExchangeClient> che accettano un indirizzo utilizzano l'associazione sulla classe statica <xref:System.ServiceModel.Description.MetadataExchangeBindings> che corrisponde allo schema URI (Uniform Resource Identifier) dell'indirizzo. In alternativa, è possibile utilizzare il costruttore <xref:System.ServiceModel.Description.MetadataExchangeClient>, che consente di specificare in modo esplicito l'associazione da utilizzare. L'associazione specificata viene utilizzata per risolvere tutti i riferimenti ai metadati.  
  
 Esattamente come qualsiasi altro client di Windows Communication Foundation (WCF), il <xref:System.ServiceModel.Description.MetadataExchangeClient> tipo fornisce un costruttore per il caricamento di configurazioni dell'endpoint client utilizzando il nome di configurazione dell'endpoint. La configurazione dell'endpoint specificata deve contenere il contratto <xref:System.ServiceModel.Description.IMetadataExchange>. Poiché l'indirizzo nella configurazione dell'endpoint non viene caricato, è necessario utilizzare uno degli overload <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> che accettano un indirizzo. Quando si specifica l'indirizzo dei metadati utilizzando un'istanza della classe <xref:System.ServiceModel.EndpointAddress>, la classe <xref:System.ServiceModel.Description.MetadataExchangeClient> presuppone che l'indirizzo punti a un endpoint MEX. Se si specifica l'indirizzo dei metadati come URL, è necessario specificare anche quale <xref:System.ServiceModel.Description.MetadataExchangeClientMode> utilizzare, MEX o HTTP GET.  
  
> [!IMPORTANT]
>  Per impostazione predefinita, la classe <xref:System.ServiceModel.Description.MetadataExchangeClient> risolve tutti i riferimenti, comprese le importazioni e le inclusioni dello schema WSDL e XML. Questa funzionalità può essere disattivata impostando la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> su `false`. È possibile controllare il numero massimo di riferimenti da risolvere utilizzando la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.MaximumResolvedReferences%2A>. Tale proprietà può essere utilizzata insieme alla proprietà `MaxReceivedMessageSize` sull'associazione per controllare la quantità di metadati recuperata.  
  
### <a name="to-use-metadataexchangeclient-to-obtain-metadata"></a>Per utilizzare MetadataExchangeClient per ottenere metadati  
  
1.  Creare un nuovo oggetto <xref:System.ServiceModel.Description.MetadataExchangeClient> specificando in modo esplicito un'associazione, un nome di configurazione dell'endpoint o l'indirizzo dei metadati.  
  
2.  Configurare <xref:System.ServiceModel.Description.MetadataExchangeClient> in base alle esigenze. Ad esempio, è possibile specificare credenziali da utilizzare quando si richiedono metadati, controllare il modo in cui vengono risolti i riferimenti ai metadati e impostare la proprietà <xref:System.ServiceModel.Description.MetadataExchangeClient.OperationTimeout%2A> per controllare il tempo entro cui la richiesta deve restituire i metadati prima del timout.  
  
3.  Ottenere l'oggetto <xref:System.ServiceModel.Description.MetadataSet> contenete i metadati recuperati chiamando uno dei metodi <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>. Si noti che è possibile utilizzare solo l'overload <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> che non accetta argomenti nel caso in cui sia stato specificato in modo esplicito un indirizzo durante la costruzione di <xref:System.ServiceModel.Description.MetadataExchangeClient>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrato come utilizzare <xref:System.ServiceModel.Description.MetadataExchangeClient> per scaricare ed enumerare i file di metadati.  

 [!code-csharp[MetadataResolver#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/metadataresolver/cs/client.cs#3)]  

## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare questo esempio di codice, è necessario fare riferimento all'assembly System.ServiceModel.dll e importare lo spazio dei nomi <xref:System.ServiceModel.Description>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.MetadataResolver>  
 <xref:System.ServiceModel.Description.MetadataExchangeClient>  
 <xref:System.ServiceModel.Description.WsdlImporter>
