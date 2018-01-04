---
title: 'Procedura: pubblicare metadati per un servizio usando codice'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 455929144f771128ca070cd02e65c919ce4c741f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a>Procedura: pubblicare metadati per un servizio usando codice
Questo è uno dei due argomenti in cui viene illustrato come pubblicare metadati per un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Esistono due modi per specificare come un servizio dovrebbe pubblicare metadati: usando un file di configurazione o il codice. In questo argomento viene illustrato come pubblicare metadati per un servizio utilizzando un codice.  
  
> [!CAUTION]
>  In questo argomento viene illustrato come pubblicare metadati in modo non sicuro. Qualsiasi client può recuperare i metadati dal servizio. Se è necessario che il servizio pubblichi metadati in modo sicuro. vedere [Endpoint di metadati protetto personalizzato](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]pubblicazione dei metadati in un file di configurazione, vedere [procedura: pubblicare metadati per un servizio utilizzando un File di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md). La pubblicazione di metadati consente ai client di recuperare i metadati usando una richiesta GET WS-Transfer o una richiesta HTTP/GET tramite la stringa di query `?wsdl`. Per essere certi che il codice funzioni, è necessario creare un servizio WCF di base. Nel codice seguente viene fornito un servizio indipendente di base.  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a>Per pubblicare metadati nel codice  
  
1.  All'interno del metodo principale di un'applicazione console, creare un'istanza di un oggetto <xref:System.ServiceModel.ServiceHost> passando il tipo di servizio e l'indirizzo di base.  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2.  Creare un blocco try subito sotto il codice per il passaggio 1. In tal modo verranno rilevate tutte le eccezioni generate mentre il servizio è in esecuzione.  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3.  Controllare se l'host del servizio contiene già un <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. In caso contrario, creare una nuova istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4.  Impostare la proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> su `true.`  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5.  <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contiene una proprietà <xref:System.ServiceModel.Description.MetadataExporter>. <xref:System.ServiceModel.Description.MetadataExporter> contiene una proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>. Impostare il valore della proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> su <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>. La proprietà <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> può essere impostata anche su <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>. Se impostato su <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> l'utilità di esportazione genera informazioni sui criteri con i metadati che "è conforme a WS-Policy 1.5. mentre se è impostata su <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>, l'utilità di esportazione genera informazioni sui criteri con i metadati conformi a WS-Policy 1.2.  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6.  Aggiungere l'istanza di <xref:System.ServiceModel.Description.ServiceMetadataBehavior> alla raccolta di comportamenti dell'host del servizio.  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7.  Aggiungere l'endpoint di scambio dei metadati all'host del servizio.  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8.  Aggiungere un endpoint dell'applicazione all'host del servizio.  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    >  Se non vengono aggiunti endpoint al servizio, il runtime aggiunge gli endpoint predefiniti. In questo esempio poiché l'oggetto <xref:System.ServiceModel.Description.ServiceMetadataBehavior> del servizio è impostato su `true`, nel servizio è abilitata la pubblicazione di metadati. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]gli endpoint predefiniti, vedere [configurazione semplificata](../../../../docs/framework/wcf/simplified-configuration.md) e [configurazione semplificata per i servizi WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
9. Aprire l'host del servizio e attendere le chiamate in ingresso. Quando l'utente preme il tasto INVIO, chiudere l'host del servizio.  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. Compilare ed eseguire l'applicazione console.  
  
11. Usare Internet Explorer per portarsi sull'indirizzo di base del servizio (http://localhost:8001/MetadataSample in questo esempio) e verificare che la pubblicazione dei metadati sia attivata. Dovrebbe venire visualizzata una pagina Web con scritto "Simple Service" in alto, seguito subito sotto da "È stato creato un servizio". Se così non fosse, all'inizio della pagina risultante verrà visualizzato il messaggio: "La pubblicazione dei metadati per il servizio è attualmente disabilitata".  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene illustrata l'implementazione di un servizio di base [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] che pubblica i metadati per il servizio nel codice.  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Ospitare un servizio WCF in un'applicazione gestita](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [Servizio indipendente](../../../../docs/framework/wcf/samples/self-host.md)  
 [Panoramica dell'architettura dei metadati](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [Uso di metadati](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [Procedura: Pubblicare metadati per un servizio usando un file di configurazione](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
