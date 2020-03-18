---
title: Linee guida per le librerie .NET open source
description: Procedure consigliate per gli sviluppatori nella creazione di librerie .NET di qualità.
ms.date: 10/17/2018
ms.openlocfilehash: 4c76dfae6ffc39df7f15381be64e33657067d79d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "76731432"
---
# <a name="open-source-library-guidance"></a>Linee guida per le librerie open source

Questo materiale sussidiario offre indicazioni agli sviluppatori per la creazione di librerie .NET di qualità. Questa documentazione è incentrata sul *cosa* e sul *perché* compilare una libreria .NET, non sul *come* eseguire l'operazione.

Aspetti delle librerie .NET open source di qualità:

> [!div class="checklist"]
>
> * **Inclusive**: le librerie .NET di qualità in genere supportano molti linguaggi di programmazione, piattaforme e applicazioni.
> * **Stabili**: le librerie .NET di qualità coesistono nell'ecosistema .NET e vengono eseguite in applicazioni compilate con molte librerie.
> * **Progettate per l'evoluzione**: le librerie .NET di qualità devono migliorare ed evolvere nel tempo, supportando gli utenti esistenti.
> * **Sottoponibili a debug**: le librerie .NET devono usare gli strumenti più aggiornati, in modo da creare un'esperienza di debug ottimale per gli utenti.
> * **Attendibili**: le librerie .NET devono risultare attendibili per gli sviluppatori grazie alla pubblicazione in NuGet con le procedure di sicurezza consigliate.

> [!div class="nextstepaction"]
> [Guida introduttiva](./get-started.md)

## <a name="types-of-recommendations"></a>Tipi di suggerimenti

Ogni articolo presenta quattro tipi di suggerimenti: **Da fare**, **Da considerare**, **Da evitare** e **Da non fare**. Il tipo di suggerimento indica quanto è importante che venga osservato.

È opportuno seguire quasi sempre un suggerimento di tipo **Da fare**. Ad esempio:

✔️ DA FARE Distribuire la libreria usando un pacchetto NuGet.

In genere è utile osservare le indicazioni di tipo **Da considerare**, ma esistono eccezioni giustificate alla regola e il fatto di non osservarla non deve rappresentare un problema:

✔️ DA CONSIDERARE Usare [SemVer 2.0.0](https://semver.org/) per la gestione versioni del pacchetto NuGet.

I suggerimenti di tipo **Da evitare** si riferiscono a operazioni in genere non consigliabili, ma che talvolta possono avere un'utilità:

❌AVOID NuGet riferimenti al pacchetto che richiedono una versione esatta.

E infine, i suggerimenti di tipo **Da non fare** indicano operazioni che quasi sempre è necessario evitare:

❌NON pubblicare versioni con nome sicuro e senza nome sicuro della libreria. Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.

>[!div class="step-by-step"]
>[Avanti](get-started.md)
