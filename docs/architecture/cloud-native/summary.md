---
title: Summary
description: Riepilogo delle conclusioni principali dell'architettura di app .NET native del cloud per Azure per la guida/e-book.
ms.date: 04/29/2020
ms.openlocfilehash: 97f20771aae73ed88d2dadefa7ba89d64eb62fcd
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82899696"
---
# <a name="summary"></a>Summary

In sintesi, di seguito sono riportate alcune importanti conclusioni di questa guida:

- Il **cloud nativo** si basa sulla progettazione di applicazioni moderne che adottano modifiche rapide, scalabilità e resilienza, in ambienti moderni e dinamici come cloud pubblici, privati e ibridi.

- ** [Cloud native Computing Foundation](https://www.cncf.io/) (CNCF)** è un consorzio open source influente di oltre 300 aziende principali. È responsabile di guidare l'adozione di un calcolo nativo del cloud tra tecnologie e stack cloud.

- Le **linee guida CNCF** consigliano che le applicazioni native del cloud abbraccino sei pilastri importanti, come illustrato nella figura 12-1:

  ![Pilastri di base nativi del cloud](./media/cloud-native-foundational-pillars.png)

  **Figura 12-1**. Pilastri di base nativi del cloud

- Questi pilastri nativi del cloud includono:
  - Il cloud e il modello di servizio sottostante
  - Principi di progettazione moderni
  - Microservizi
  - Contenitori e orchestrazione di contenitori
  - Servizi di supporto basati sul cloud, ad esempio database e broker di messaggi
  - Automazione, inclusa l'infrastruttura come codice e la distribuzione del codice

- **Kubernetes** è l'ambiente di hosting preferito per la maggior parte delle applicazioni native del cloud. I servizi più piccoli e semplici sono talvolta ospitati in piattaforme senza server, ad esempio funzioni di Azure. Tra le numerose funzionalità di automazione principali, entrambi gli ambienti forniscono la scalabilità automatica per gestire i volumi di carico di lavoro fluttuanti.

- La **comunicazione tra servizi** diventa una decisione di progettazione significativa quando si costruisce un'applicazione nativa del cloud. Le applicazioni in genere espongono un gateway API per gestire la comunicazione del client front-end. I microservizi back-end tentano quindi di comunicare tra loro implementando modelli di comunicazione asincrona, quando possibile.

- **gRPC** è un Framework moderno e a prestazioni elevate che evolve il protocollo RPC (Remote Procedure Call) obsoleto. Le applicazioni native del cloud spesso adottano gRPC per semplificare la messaggistica tra i servizi back-end. gRPC Usa HTTP/2 per il protocollo di trasporto. Può essere fino a 8x più velocemente rispetto alla serializzazione JSON con dimensioni del messaggio 60-80% inferiori. gRPC è open source e gestito da cloud native Computing Foundation (CNCF).

- **I dati distribuiti** sono un modello spesso implementato da applicazioni native del cloud. Le applicazioni segregano la funzionalità aziendale in microservizi piccoli e indipendenti. Ogni microservizio incapsula le dipendenze, i dati e lo stato. Il modello di database condiviso classico si evolve in uno dei numerosi database più piccoli, ognuno dei quali è allineato a un microservizio. Quando il fumo si cancella, emergiamo con una progettazione che espone un `database-per-microservice` modello.

- I **database no-SQL** fanno riferimento ad archivi dati non relazionali a prestazioni elevate. Si distinguono per la facilità d'uso, la scalabilità, la resilienza e le caratteristiche di disponibilità. Servizi di volume elevato che richiedono tempi di risposta di sottosecondo favoriscono gli archivi dati NoSQL. La proliferazione delle tecnologie NoSQL per i sistemi distribuiti nativi del cloud non può essere sovrastata.

- **NewSQL** è una tecnologia di database emergente che combina la scalabilità distribuita di NoSQL e le garanzie ACID di un database relazionale. I database NewSQL sono destinati a sistemi aziendali che devono elaborare volumi elevati di dati, in ambienti distribuiti, con una completa conformità transazionale/ACID. Cloud native Computing Foundation (CNCF) offre diversi progetti di database NewSQL.

- La **resilienza** è la capacità del sistema di reagire agli errori e rimane comunque funzionante. I sistemi nativi cloud adottano l'architettura distribuita in cui l'errore è inevitabile. Le applicazioni devono essere create per rispondere in modo elegante a un errore e tornare rapidamente a uno stato completamente funzionante.

- Le **reti mesh di servizi** sono un livello di infrastruttura configurabile con funzionalità predefinite per gestire la comunicazione dei servizi e altre complicazioni incrociate. Disaccoppiano le responsabilità trasversali dal codice aziendale. Queste responsabilità si spostano in un proxy del servizio. Definito come `Sidecar pattern`, il proxy viene distribuito in un processo separato per garantire l'isolamento dal codice business.

- L' **osservabilità** è una considerazione di progettazione fondamentale per le applicazioni native del cloud. Poiché i servizi vengono distribuiti in un cluster di nodi, la registrazione centralizzata, il monitoraggio e gli avvisi, diventano obbligatori. Monitoraggio di Azure è una raccolta di strumenti basati sul cloud progettati per fornire visibilità sullo stato del sistema.

- L' **infrastruttura come codice** è una procedura ampiamente accettata che automatizza il provisioning della piattaforma. L'infrastruttura e le distribuzioni sono automatiche, coerenti e ripetibili. Strumenti come Azure Resource Manager, bonifica e l'interfaccia della riga di comando di Azure consentono di creare script in modo dichiarativo dell'infrastruttura cloud necessaria.

- L' **automazione del codice** è un requisito per le applicazioni native del cloud. I sistemi di integrazione continua/recapito continuo moderni contribuiscono a soddisfare questo principio. Forniscono passaggi di compilazione e distribuzione distinti che consentono di garantire codice coerente e di qualità. La fase di compilazione trasforma il codice in un artefatto binario. La fase di rilascio preleva l'artefatto binario, applica la configurazione dell'ambiente esterno e lo distribuisce in un ambiente specificato. Azure DevOps e GitHub sono ambienti DevOps con funzionalità complete.

>[!div class="step-by-step"]
>[Indietro](application-bundles.md)
