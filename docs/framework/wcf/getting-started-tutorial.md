---
title: 'Esercitazione: Iniziare con le applicazioni di Windows Communication Foundation'
description: Queste esercitazioni vengono fornite informazioni introduttive per la creazione di applicazioni WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 66211cfcf2b742e43eccbefb2bc7c4bd1147b05b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58408860"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Esercitazione: Iniziare con le applicazioni di Windows Communication Foundation
La seguente serie di esercitazioni fornisce un'introduzione a Windows Communication Foundation (WCF) esperienza di programmazione. Eseguire queste esercitazioni nell'ordine fornirà informazioni introduttive sui passaggi necessari per creare le applicazioni WCF. Al termine, si otterrà un servizio WCF in esecuzione e un client WCF che chiama il servizio. 

L'esercitazione presuppone che si usa Visual Studio come ambiente di sviluppo. Se si usa un altro ambiente di sviluppo, ignorare le istruzioni specifiche di Visual Studio. 

Per le applicazioni WCF di esempio che è possibile scaricare ed eseguire, vedere [degli esempi Windows Communication Foundation](samples/index.md). Per un'introduzione agli esempi, vedere [esempio di Guida introduttiva](samples/getting-started-sample.md).

Per altre informazioni dettagliate sulla creazione di servizi e client, vedere [programmazione WCF di base](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Esercitazioni WCF

Le prime tre esercitazioni descrivono come definire un contratto di servizio WCF, la relativa implementazione e come ospitarlo. Il servizio creato è Self-hosted all'interno di un'applicazione console. È inoltre possibile ospitare servizi in Microsoft Internet Information Services (IIS). Per altre informazioni, vedere [Procedura: Ospitare un servizio WCF in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Anche se si usa codice per configurare il servizio in questa esercitazione, è anche possibile [configurare i servizi all'interno di un file di configurazione](configuring-services-using-configuration-files.md). 

- [Esercitazione: Definire un contratto di servizio](how-to-define-a-wcf-service-contract.md)

    Si crea un contratto WCF con un'interfaccia definita dall'utente. Questo contratto definisce la funzionalità esposte dal servizio.

- [Esercitazione: Implementare un contratto di servizio](how-to-implement-a-wcf-contract.md)

    Dopo aver definito un contratto, è necessario implementarla con una classe di servizio.

- [Esercitazione: Ospitare ed eseguire un servizio di base](how-to-host-and-run-a-basic-wcf-service.md)

    Configurare un endpoint per il servizio e ospitare il servizio in un'applicazione console. Per un servizio diventi attivo, è necessario configurarlo e ospitarlo all'interno di un ambiente di runtime. In questo ambiente di runtime viene creato il servizio e controlla il contesto e durata.

Le due esercitazioni descrivono come creare, configurare e usare un'applicazione client per chiamare le operazioni del servizio espone. I servizi pubblicano i metadati che definiscono le informazioni necessarie a un'applicazione client per comunicare con il servizio. Visual Studio consente di automatizzare il processo di accesso a questi metadati e lo usa per creare l'applicazione client per il servizio. Se si decide di non usare Visual Studio, è possibile usare la [strumento ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) invece.

- [Esercitazione: Creare un client](how-to-create-a-wcf-client.md)

    Recuperare i metadati per la creazione di un proxy client WCF da un servizio WCF. Recuperare i metadati usando Visual Studio per aggiungere un riferimento al servizio oppure è possibile usare lo strumento ServiceModel Metadata Utility Tool. Si specifica l'endpoint utilizzato dal client per accedere al servizio.

- [Esercitazione: Usare un client](how-to-use-a-wcf-client.md)

    Usare il proxy client WCF per chiamare le operazioni del servizio.

## <a name="reference"></a>Riferimenti

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Vedere anche

- [Panoramica concettuale](conceptual-overview.md)
- [Guida alla documentazione](guide-to-the-documentation.md)
- [Che cos'è Windows Communication Foundation](whats-wcf.md)
- [Dettagli delle funzionalità di WCF](feature-details/index.md)
- [Ciclo di programmazione di base](basic-programming-lifecycle.md)
- [Creazione di client](building-clients.md)
- [Programmazione WCF di base](basic-wcf-programming.md)
- [Procedura: Creare un contratto duplex](feature-details/how-to-create-a-duplex-contract.md)
- [Procedura: Servizi di accesso con un contratto duplex](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Strumento ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Procedura: Usare Svcutil.exe per scaricare documenti di metadati](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Procedura: Pubblicare i metadati per un servizio utilizzando un file di configurazione](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Uso di associazioni per configurare servizi e client](using-bindings-to-configure-services-and-clients.md)
- [Esempio introduttivo](samples/getting-started-sample.md)
- [Esempi di Windows Communication Foundation](samples/index.md)
- [Servizio indipendente](samples/self-host.md)


