---
title: Introduzione alle applicazioni cloud native
description: Scopri di più sull'elaborazione nativa del cloud
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: c9ffd34ec3deb04abddbbf85a9e5a6ed2b57c8f9
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989051"
---
# <a name="introduction-to-cloud-native-applications"></a>Introduzione alle applicazioni cloud native

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Un altro giorno, in ufficio, a lavorare su "la prossima grande cosa".

Il tuo cellulare squilla. È il tuo amichevole reclutatore - quello che ti chiama due volte al giorno per nuovi lavori.

Ma questa volta è diverso: start-up, equità, e un sacco di finanziamenti.

La menzione del cloud e della tecnologia all'avanguardia ti spinge oltre l'edge.

Avanti rapidamente un paio di settimane e ora sei un nuovo dipendente in una sessione di progettazione che progetta un'importante applicazione di e-commerce. Si sta andando a completare con altri siti di e-commerce leader.

Come lo costruirete?

Se si seguono le indicazioni degli ultimi 15 anni, molto probabilmente si creerà il sistema illustrato nella Figura 1.1.

![Design monolitico tradizionale](./media/monolithic-design.png)

**Figura 1-1**. Design monolitico tradizionale

Si costruisce un'applicazione di base di grandi dimensioni contenente tutta la logica di dominio. Include moduli come Identity, Catalog, Ordering e altro ancora. L'app di base comunica con un database relazionale di grandi dimensioni. Il nucleo espone funzionalità tramite un'interfaccia HTML.

Congratulazioni!  Hai appena creato un'applicazione monolitica.

Non tutto è male. I monoliti offrono alcuni vantaggi distinti. Ad esempio, sono semplici da...

- build
- test
- distribuire
- Risolvere
- scala

Molte app di successo che esistono oggi sono state create come monoliti. L'applicazione è un successo e continua ad evolversi, iterazione dopo iterazione, aggiungendo sempre più funzionalità.

Ad un certo punto, però, si inizia a sentirsi a disagio. Ti ritrovi a perdere il controllo dell'applicazione. Col passare del tempo, la sensazione diventa più intensa e alla fine si entra in uno stato noto come il ciclo della **paura**.

- L'applicazione è diventata così schiacciante complicato che nessuna persona lo capisce.
- Si teme di apportare modifiche - ogni modifica ha effetti collaterali involontari e costosi.
- Le nuove funzionalità/correzioni diventano difficili, dispendiose in termini di tempo e costose da implementare.
- Ogni versione è piccola come richiede una distribuzione completa dell'intera applicazione.
- Un componente instabile può causare l'arresto anomalo dell'intero sistema.
- Le nuove tecnologie e i nuovi framework non sono un'opzione.
- È difficile implementare metodologie di distribuzione agile.
- L'erosione architettonica si instaede quando la base di codice si deteriora con "casi speciali" senza fine.
- I consulenti ti dicono di riscriverlo.

Molte organizzazioni hanno affrontato il ciclo della paura monolitica adottando un approccio cloud-native alla costruzione di sistemi. Nella figura 1-2 è illustrato lo stesso sistema creato applicando tecniche e procedure native nel cloud.

![Progettazione nativa cloud](./media/cloud-native-design.png)

**Figura 1-2**. Progettazione nativa del cloud

Si noti come l'applicazione viene scomposta in un set di piccoli microservizi isolati. Ogni servizio è indipendente e incapsula il proprio codice, i dati e le dipendenze. Ognuno viene distribuito in un contenitore software e gestito da un agente di orchestrazione del contenitore. Invece di un database relazionale di grandi dimensioni, ogni servizio è proprietario di un proprio archivio dati, il cui tipo varia in base alle esigenze dei dati. Si noti come alcuni servizi dipendono da un database relazionale, ma altri su database NoSQL.Note how some services depend on a relational database, but other on NoSQL databases. Un servizio archivia il proprio stato in una cache distribuita. Si noti il modo in cui tutto il traffico viene instradato tramite un servizio gateway API responsabile del routing del traffico ai servizi back-end principali e dell'applicazione di molti problemi trasversali. Ancora più importante, l'applicazione sfrutta appieno le funzionalità di scalabilità e resilienza presenti nelle moderne piattaforme cloud.

### <a name="cloud-native-computing"></a>Cloud-native computing

Hmm... Abbiamo appena usato il termine,*"Cloud Native".* Per prima cosa pensavi: "Che cosa significa esattamente?" Un'altra parola d'ordine del settore inventata dai fornitori di software per commercializzare più roba?"

Fortunatamente è molto diverso e spero che questo libro vi aiuterà a convincervi.

In breve tempo, cloud native è diventato una tendenza trainante nel settore del software. È un nuovo modo di pensare alla creazione di sistemi complessi di grandi dimensioni, un approccio che sfrutta appieno le moderne pratiche, tecnologie e infrastruttura cloud per lo sviluppo software. L'approccio cambia il modo in cui progetti, implementi, distribuisci e operativizzi i sistemi.

A differenza del continuo hype che guida il nostro settore, il cloud native è "*per davvero*". Si consideri la [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), un consorzio di oltre 300 grandi aziende con una carta per rendere il cloud-native computing oniquo attraverso la tecnologia e gli stack cloud. Come uno dei gruppi open source più influenti, ospita molti dei progetti open source in più rapida crescita in GitHub. Includono progetti come [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/)e [gRPC](https://grpc.io/).

Il CNCF promuove un ecosistema di neutralità open source e vendor. Seguendo questo vantaggio, presentiamo principi, modelli e best practice indipendenti dal cloud che sono indipendenti dalla tecnologia. Allo stesso tempo, vengono illustrati i servizi e l'infrastruttura disponibili nel cloud di Microsoft Azure per la costruzione di sistemi nativi cloud.

Quindi, che cosa è esattamente Cloud Native? Siedi, rilassati e lascia che ti aiutiamo a esplorare questo nuovo mondo.

>[!div class="step-by-step"]
>[Successivo](index.md)
>[precedente](definition.md)
