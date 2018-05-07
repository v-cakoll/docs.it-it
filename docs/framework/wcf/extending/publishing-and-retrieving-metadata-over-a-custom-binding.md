---
title: Pubblicazione e recupero di metadati su un'associazione personalizzata
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 607cf70e8e226e6c97a785f2478ad3a655b21a7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Pubblicazione e recupero di metadati su un'associazione personalizzata
La classe <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> fornisce supporto per l'aggiunta di endpoint dei metadati a un servizio. Tali endpoint dei metadati possono rispondere alle richieste HTTP GET a un URL che ha un `?wsdl` querystring e alle richieste GET WS-Transfer come definito nella specifica WS-MetadataExchange (MEX). Gli endpoint MEX implementano il contratto <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType>.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Pubblicazione di metadati su un'associazione personalizzata  
 Gli endpoint di metadati GET di HTTP e di HTTPS vengono attivati impostando le proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> o <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> su `true`. Non è possibile configurare le associazioni per questi endpoint.  
  
 Il <xref:System.ServiceModel.Description.IMetadataExchange> contratto, tuttavia, può essere utilizzato con qualsiasi endpoint, compresi quelli che utilizzano associazioni personalizzate, poiché <xref:System.ServiceModel.Description.IMetadataExchange> gli endpoint sono identici a qualsiasi altro endpoint di servizio Windows Communication Foundation (WCF). Se si sa come modificare la configurazione di un'associazione fornita dal sistema o come configurare un elemento <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>, è possibile configurare un'associazione da utilizzare con un endpoint <xref:System.ServiceModel.Description.IMetadataExchange>.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Recupero di metadati su un'associazione personalizzata  
 I metadati possono essere recuperati da endpoint di metadati Get HTTP e Get HTTPS utilizzando richieste GET HTTP o HTTPS standard.  
  
 Per recuperare metadati da un endpoint di metadati MEX è generalmente possibile utilizzare una delle associazioni MEX standard supportate in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Per altre informazioni, vedere <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. Il tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> e lo strumento Svcutil.exe consentono di selezionare automaticamente una di queste associazioni MEX standard in base all'indirizzo dell'endpoint dei metadati specificato.  
  
 Se un endpoint di metadati MEX utilizza un'associazione diversa dalle associazioni MEX standard, è possibile configurare l'associazione utilizzata da <xref:System.ServiceModel.Description.MetadataExchangeClient> mediante codice o fornendo una configurazione dell'endpoint del client <xref:System.ServiceModel.Description.IMetadataExchange>. Lo strumento Svcutil.exe carica automaticamente dal file di configurazione una configurazione dell'endpoint del client <xref:System.ServiceModel.Description.IMetadataExchange> che ha lo stesso nome dello schema URI per l'indirizzo dell'endpoint dei metadati.  
  
## <a name="security"></a>Sicurezza  
 Quando si pubblicano metadati su un'associazione personalizzata, accertarsi che l'associazione fornisca il supporto di sicurezza necessario per i metadati. Per impedire la diffusione di informazioni, ad esempio, e fare in modo che il client sia autorizzato a ottenere i metadati, è possibile rendere più protetti i metadati e l'applicazione configurando l'endpoint <xref:System.ServiceModel.Description.IMetadataExchange> perché richieda l'autenticazione e la crittografia. L'esempio [Endpoint di metadati protetto personalizzato](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) illustra questo scenario.  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione dei servizi](../../../../docs/framework/wcf/securing-services.md)  
 [Associazioni WS-MetadataExchange](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)  
 [Procedura: Configurare un'associazione WS-Metadata Exchange personalizzata](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [Procedura: Recuperare metadati attraverso un'associazione non MEX](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
