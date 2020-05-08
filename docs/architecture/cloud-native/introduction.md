---
title: Introduzione alle applicazioni cloud native
description: Informazioni sul cloud-native computing
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: e1f7683b6f3722bb91e611f199f2e9ce2bbefc63
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895527"
---
# <a name="introduction-to-cloud-native-applications"></a>Introduzione alle applicazioni cloud native

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Un altro giorno, in ufficio, a lavorare su "la prossima grande cosa".

Il cellulare squilla. Si tratta di un Recruiter gentile, ovvero quello che chiama due volte al giorno per i nuovi processi.

Ma questa volta è diversa: avvio, equità e abbondanza di finanziamenti.

La menzione della tecnologia cloud e all'avanguardia ti permette di inserirti sul perimetro.

È possibile procedere in modo rapido per alcune settimane e si è ora un nuovo dipendente in una sessione di progettazione che progetta un'applicazione di eCommerce principale. Si prevede di partecipare ad altri siti di eCommerce principali.

Come verrà compilato?

Se si seguono le linee guida degli ultimi 15 anni, probabilmente si creerà il sistema illustrato nella figura 1,1.

![Progettazione monolitica tradizionale](./media/monolithic-design.png)

**Figura 1-1**. Progettazione monolitica tradizionale

Si crea un'applicazione principale di grandi dimensioni contenente tutta la logica di dominio. Sono inclusi moduli quali identità, catalogo, ordinamento e altro ancora. L'app principale comunica con un database relazionale di grandi dimensioni. Il nucleo espone la funzionalità tramite un'interfaccia HTML.

Congratulazioni!  È stata appena creata un'applicazione monolitica.

Non è tutto negativo. I monoliti offrono alcuni vantaggi distinti. Ad esempio, sono semplici da...

- build
- test
- distribuire
- risolvere i problemi
- scala

Molte app riuscite attualmente disponibili sono state create come Monolith. L'app è un hit e continua ad evolversi, iterazione dopo l'iterazione, aggiungendo altre funzionalità.

A un certo punto, tuttavia, si inizia a provare a disagio. Si perde il controllo dell'applicazione. Con il passare del tempo, la sensazione diventa più intensa e infine si entra in uno stato noto come **ciclo di paura**.

- L'app è diventata talmente complicata che nessuno lo riconosce.
- Si temono di apportare modifiche. ogni modifica presenta effetti collaterali indesiderati e costosi.
- Le nuove funzionalità e correzioni diventano difficili da implementare e dispendiose in termini di tempo.
- Ogni versione può richiedere una distribuzione completa dell'intera applicazione.
- Un componente instabile può arrestarsi in modo anomalo nell'intero sistema.
- Le nuove tecnologie e i Framework non sono un'opzione.
- È difficile implementare le metodologie di distribuzione agile.
- L'erosione dell'architettura imposta in, in quanto la codebase si deteriora con "casi speciali" senza terminazione.
- I consulenti indicano di riscriverlo.

Molte organizzazioni hanno affrontato il ciclo di paure monolitico adottando un approccio nativo al cloud per la creazione di sistemi. La figura 1-2 Mostra lo stesso sistema creato applicando tecniche e procedure native del cloud.

![Progettazione nativa del cloud](./media/cloud-native-design.png)

**Figura 1-2**. Progettazione nativa del cloud

Si noti il modo in cui l'applicazione è scomposta in un set di microservizi isolati di piccole dimensioni. Ogni servizio è indipendente e incapsula il proprio codice, i dati e le dipendenze. Ogni viene distribuito in un contenitore software e gestito da un agente di orchestrazione dei contenitori. Invece di un database relazionale di grandi dimensioni, ogni servizio è proprietario del proprio archivio dati, il tipo di che varia in base alle esigenze dei dati. Si noti che alcuni servizi dipendono da un database relazionale, ma altri nei database NoSQL. Un servizio archivia lo stato in una cache distribuita. Si noti il modo in cui tutto il traffico viene indirizzato attraverso un servizio gateway API responsabile del routing del traffico ai servizi back-end di base e dell'applicazione di molte problematiche trasversali. In particolare, l'applicazione sfrutta appieno le funzionalità di scalabilità e resilienza disponibili nelle piattaforme cloud moderne.

### <a name="cloud-native-computing"></a>Elaborazione nativa del cloud

OK... Abbiamo appena usato il termine "*cloud native*". Il primo pensiero potrebbe essere "che cosa significa esattamente?" Un'altra parola d'altro settore inventata dai fornitori di software per commercializzare più cose? "

Fortunatamente è molto diverso e speriamo che questo libro consenta di convincerlo.

Nell'arco di un breve periodo di tempo, cloud native è diventato una tendenza di guida nel settore del software. Si tratta di un nuovo modo per considerare la creazione di sistemi complessi e di grandi dimensioni, un approccio che sfrutta appieno le moderne procedure di sviluppo del software, le tecnologie e l'infrastruttura cloud. L'approccio modifica la modalità di progettazione, implementazione, distribuzione e rendere operativo dei sistemi.

A differenza dell'hype continuo che guida il nostro settore, il cloud nativo è "*per la realtà*". Si consideri il [cloud native Computing Foundation](https://www.cncf.io/) (CNCF), un consorzio di oltre 300 aziende principali con una carta per rendere il computer nativo dal cloud onnipresente tra tecnologie e stack cloud. In qualità di uno dei gruppi open source più influenti, ospita molti dei progetti open source più veloci, in GitHub. Sono inclusi progetti come [Kubernetes](https://kubernetes.io/), [Prometeo](https://prometheus.io/), [Helm](https://helm.sh/), [inviato](https://www.envoyproxy.io/)e [gRPC](https://grpc.io/).

Il CNCF promuove un ecosistema di Open Source e neutralità del fornitore. In seguito, vengono presentati i principi, i modelli e le procedure consigliate native del cloud, indipendenti dalla tecnologia. Allo stesso tempo, verranno illustrati i servizi e l'infrastruttura disponibili nel cloud Microsoft Azure per la creazione di sistemi nativi del cloud.

Che cos'è esattamente il cloud nativo? Torna indietro, rilassati e ti aiuteremo a esplorare questo nuovo mondo.

>[!div class="step-by-step"]
>[Precedente](index.md)
>[successivo](definition.md)
