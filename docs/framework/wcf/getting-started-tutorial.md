---
title: 'Esercitazione: Introduzione alle applicazioni Windows Communication FoundationTutorial: Get started with Windows Communication Foundation applications'
description: Queste esercitazioni fornisce un'introduzione per la creazione di applicazioni WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: df73f953372202796cebce9d3e3f28bd617c67ef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184117"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a>Esercitazione: Introduzione alle applicazioni Windows Communication FoundationTutorial: Get started with Windows Communication Foundation applications
La serie di esercitazioni seguente introduce l'esperienza di programmazione di Windows Communication Foundation (WCF). L'utilizzo di queste esercitazioni nell'ordine offre una comprensione introduttiva dei passaggi necessari per creare applicazioni WCF. Al termine, si dirà un servizio WCF in esecuzione e un client WCF che chiama il servizio.

L'esercitazione presuppone che si sta utilizzando Visual Studio come ambiente di sviluppo. Se si utilizza un altro ambiente di sviluppo, ignorare le istruzioni specifiche di Visual Studio.If you're using another development environment, ignore the Visual Studio-specific instructions.

Per applicazioni WCF di esempio che è possibile scaricare ed eseguire, vedere Esempi di [Windows Communication Foundation](samples/index.md). Per un'introduzione agli esempi, vedere [Esempio introduttivo.](samples/getting-started-sample.md)

Per informazioni più approfondite sulla creazione di servizi e client, vedere [Programmazione WCF di base](basic-wcf-programming.md).

## <a name="wcf-tutorials"></a>Esercitazioni di WCFWCF tutorials

Le prime tre esercitazioni descrivono come definire un contratto di servizio WCF, come implementarlo e come ospitarlo. Il servizio creato è indipendente all'interno di un'applicazione console. È inoltre possibile ospitare servizi in Microsoft Internet Information Services (IIS). Per ulteriori informazioni, vedere [procedura: ospitare un servizio WCF in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md). Sebbene si utilizzi il codice per configurare il servizio nell'esercitazione, è anche possibile configurare i [servizi all'interno](configuring-services-using-configuration-files.md)di un file di configurazione.

- [Esercitazione: Definire un contratto di servizioTutorial: Define a service contract](how-to-define-a-wcf-service-contract.md)

    Creare un contratto WCF con un'interfaccia definita dall'utente. Questo contratto definisce la funzionalità esposta dal servizio.

- [Esercitazione: Implementare un contratto di servizioTutorial: Implement a service contract](how-to-implement-a-wcf-contract.md)

    Dopo aver definito un contratto, è necessario implementarlo con una classe di servizio.

- [Esercitazione: Ospitare ed eseguire un servizio di baseTutorial: Host and run a basic service](how-to-host-and-run-a-basic-wcf-service.md)

    Configurare un endpoint per il servizio e ospitarlo in un'applicazione console. Affinché un servizio diventi attivo, è necessario configurarlo e ospitarlo all'interno di un ambiente di runtime. Questo ambiente di runtime crea il servizio e ne controlla il contesto e la durata.

Nelle due esercitazioni successive viene descritto come creare, configurare e usare un'applicazione client per chiamare le operazioni esposte dal servizio. I servizi pubblicano i metadati che definiscono le informazioni necessarie a un'applicazione client per comunicare con il servizio. Visual Studio automatizza il processo di accesso a questi metadati e lo usa per costruire l'applicazione client per il servizio. Se si decide di non utilizzare Visual Studio, è possibile utilizzare [lo strumento ServiceModel Metadata Utility Tool (*Svcutil.exe*).](servicemodel-metadata-utility-tool-svcutil-exe.md)

- [Esercitazione: Creare un clientTutorial: Create a client](how-to-create-a-wcf-client.md)

    Recuperare i metadati per la creazione di un proxy client WCF da un servizio WCF. È possibile recuperare i metadati utilizzando Visual Studio per aggiungere un riferimento al servizio oppure è possibile utilizzare lo strumento ServiceModel Metadata Utility. Specificare l'endpoint utilizzato dal client per accedere al servizio.

- [Esercitazione: Usare un clientTutorial: Use a client](how-to-use-a-wcf-client.md)

    Utilizzare il proxy client WCF per chiamare le operazioni del servizio.

## <a name="reference"></a>Informazioni di riferimento

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a>Vedere anche

- [Informazioni generali](conceptual-overview.md)
- [Guida alla documentazione](guide-to-the-documentation.md)
- [Che cos'è Windows Communication Foundation](whats-wcf.md)
- [Dettagli della funzionalità WCFWCF feature details](feature-details/index.md)
- [Ciclo di vita di programmazione di baseBasic programming lifecycle](basic-programming-lifecycle.md)
- [Costruire clienti](building-clients.md)
- [Programmazione WCF di baseBasic WCF programming](basic-wcf-programming.md)
- [Procedura: creare un contratto duplexHow to: Create a duplex contract](feature-details/how-to-create-a-duplex-contract.md)
- [Procedura: accedere ai servizi con un contratto duplexHow to: Access services with a duplex contract](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [Strumento ServiceModel Metadata Utility (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Procedura: utilizzare Svcutil.exe per scaricare documenti di metadatiHow to: Use Svcutil.exe to download metadata documents](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [Procedura: pubblicare metadati per un servizio usando un file di configurazioneHow to: Publish metadata for a service using a configuration file](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Utilizzo di associazioni per configurare servizi e clientUsing bindings to configure services and clients](using-bindings-to-configure-services-and-clients.md)
- [Esempio introduttivo](samples/getting-started-sample.md)
- [Esempi di Windows Communication Foundation](samples/index.md)
- [Servizio indipendente](samples/self-host.md)
