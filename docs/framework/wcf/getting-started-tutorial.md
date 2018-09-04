---
title: Introduzione a Tutorial1
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], getting started
- Windows Communication Foundation [WCF], getting started
- getting started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: e5a07e5264c715f568121403721a3c844b903d99
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43553077"
---
# <a name="getting-started-tutorial"></a>Esercitazione introduttiva
Gli argomenti contenuti in questa sezione sono utili per fornire una rapida descrizione a Windows Communication Foundation (WCF) esperienza di programmazione. Vengono ideati per essere completati secondo l'ordine dell'elenco posto nella parte inferiore di questo argomento. Esecuzione di questa esercitazione offre informazioni introduttive sui passaggi necessari per creare applicazioni client e servizio WCF. Un servizio espone uno o più endpoint, ciascuno dei quali espone una o più operazioni del servizio. Il *endpoint* di un servizio specifica un indirizzo in cui è possibile trovare il servizio, un'associazione che contiene le informazioni che descrivono come un client deve comunicare con il servizio e un contratto che definisce la funzionalità fornita dal servizio ai propri client.  
  
 Seguendo la sequenza degli argomenti di questa esercitazione si otterrà un servizio funzionante e un client che chiama il servizio. Nei primi tre argomenti viene descritto come definire e implementare un contratto di servizio, nonché come ospitare il servizio. Il servizio creato è self-hosted all'interno di un'applicazione console. I servizi possono anche essere ospitati in Internet Information Services (IIS). Per altre informazioni su come eseguire questa operazione, vedere [procedura: ospitare un servizio WCF in IIS](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md). Il servizio viene configurato nel codice; tuttavia, i servizi possono essere configurati anche all'interno di un file di configurazione. Per altre informazioni sull'uso di un file di configurazione, vedere [configurazione di servizi tramite file di configurazione](../../../docs/framework/wcf/configuring-services-using-configuration-files.md).  
  
 Nei tre argomenti successivi viene descritto come creare un proxy client, configurare l'applicazione client e usare il proxy client per chiamare l'operazione del servizio esposta da quest'ultimo. I servizi pubblicano i metadati che definiscono le informazioni necessarie a un'applicazione client per comunicare con il servizio. In [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] il processo di accesso a questi metadati viene automatizzato e i metadati vengono usati per creare e configurare l'applicazione client per il servizio. Se non si usa [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)], è possibile usare il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per costruire e configurare l'applicazione client per il servizio.  
  
 In tutti gli argomenti di questa sezione si presuppone l'uso di Visual Studio 2011 come ambiente di sviluppo. Se si usa un altro ambiente di sviluppo, ignorare le istruzioni specifiche di Visual Studio.  
  
> [!NOTE]
>  Se si esegue [!INCLUDE[wv](../../../includes/wv-md.md)] o versioni successive del sistema operativo Windows, è necessario avviare Visual Studio nel menu Start e facendo clic con il pulsante destro Visual Studio 2011 e selezionando **Esegui come amministratore**. Per avviare sempre Visual Studio 2011 come amministratore è possibile creare una soluzione rapida, fare clic con il pulsante destro di scelta rapida, scegliere Proprietà, selezionare la **Compatibility** e selezionare il **Esegui questo programma come amministratore** casella di controllo. Quando si avvia Visual Studio 2011 con questo collegamento, verrà sempre eseguito con diritti di amministratore.  
  
 Per le applicazioni di esempio che possono essere scaricate sul disco rigido ed eseguire, vedere gli argomenti in [degli esempi Windows Communication Foundation](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91). In questo argomento, vedere, in particolare, il [introduttiva](../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
 Per altre informazioni dettagliate sulla creazione di servizi e client, vedere [programmazione WCF di base](../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Definire un contratto di servizio](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 Viene descritto come creare un contratto WCF tramite un'interfaccia definita dall'utente. Il contratto definisce la funzionalità esposta dal servizio.  
  
 [Procedura: Implementare un contratto di servizio](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 Viene descritto come implementare un contratto di servizio. Una volta definito, un contratto deve essere implementato con una classe di servizio.  
  
 [Procedura: Ospitare ed eseguire un servizio di base](../../../docs/framework/wcf/how-to-host-and-run-a-basic-wcf-service.md)  
 Viene descritto come configurare un endpoint per il servizio nel codice e come ospitare il servizio in un'applicazione console. Per diventare attivo, un servizio deve essere configurato e ospitato all'interno di un ambiente di runtime. Questo ambiente crea il servizio e ne controlla contesto e durata.  
  
 [Procedura: Creare un client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 Viene descritto come recuperare i metadati usati per creare un proxy client WCF da un servizio WCF. In questo processo viene usata la funzionalità Aggiungi riferimento al servizio di Visual Studio 2011.  
  
 [Procedura: Configurare un client](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
 Viene descritto come configurare un client WCF. La configurazione del client richiede la specifica dell'endpoint usato dal client per accedere al servizio.  
  
 [Procedura: Usare un client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)  
 Viene descritto come usare il proxy client WCF per richiamare operazioni del servizio.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.ServiceModel.ServiceContractAttribute>  
  
 <xref:System.ServiceModel.OperationContractAttribute>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Esempi di Windows Communication Foundation](https://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [Ciclo di vita della programmazione di base](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica dei concetti](../../../docs/framework/wcf/conceptual-overview.md)  
 [Guida alla documentazione](../../../docs/framework/wcf/guide-to-the-documentation.md)  
 [Informazioni su Windows Communication Foundation](../../../docs/framework/wcf/whats-wcf.md)  
 [Dettagli delle funzionalità di WCF](../../../docs/framework/wcf/feature-details/index.md)
