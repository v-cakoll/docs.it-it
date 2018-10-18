---
title: Linee guida per le librerie open source
description: Procedure consigliate per gli sviluppatori nella creazione di librerie .NET di qualità.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 50fb745f7eb65abcaca76cebaf9991c48f559e59
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374901"
---
# <a name="open-source-library-guidance"></a>Linee guida per le librerie open source

Questo materiale sussidiario offre indicazioni agli sviluppatori per la creazione di librerie .NET di qualità. Questa documentazione è incentrata sul *cosa* e sul *perché* compilare una libreria .NET, non sul *come* eseguire l'operazione.

Aspetti delle librerie .NET open source di qualità:

> [!div class="checklist"]
> * **Inclusive**: le librerie .NET di qualità in genere supportano varie piattaforme e applicazioni.
> * **Stabili**: le librerie .NET di qualità coesistono nell'ecosistema .NET e vengono eseguite in applicazioni compilate con molte librerie.
> * **Progettate per l'evoluzione**: le librerie .NET di qualità devono migliorare ed evolvere nel tempo, supportando gli utenti esistenti.
> * **Sottoponibili a debug**: le librerie .NET devono usare gli strumenti più aggiornati, in modo da creare un'esperienza di debug ottimale per gli utenti.
> * **Attendibili**: le librerie .NET devono risultare attendibili per gli sviluppatori grazie alla pubblicazione in NuGet con le procedure di sicurezza consigliate.

> [!div class="nextstepaction"]
> [Introduzione](./get-started.md)

## <a name="recommendations"></a>Suggerimenti

Ogni articolo include un elenco di indicazioni per la libreria .NET, con le notazioni **Da fare**, **Da considerare**, **Da evitare** e **Da non fare**. La formulazione di ogni indicazione indica quanto è importante che venga osservata.

Un'indicazione di tipo **Da fare** va seguita nella maggior parte dei casi:

**✔️ DA FARE** Distribuire la libreria usando un pacchetto NuGet.

In genere è utile osservare le indicazioni di tipo **Da considerare**, ma esistono eccezioni giustificate alla regola e il fatto di non osservarla non deve rappresentare un problema:

**✔️ DA CONSIDERARE** Usare [SemVer 2.0.0](https://semver.org/) per la gestione versioni del pacchetto NuGet.

Le indicazioni di tipo **Da evitare** riguardano operazioni in genere non consigliabili, ma che talvolta possono avere un'utilità:

**❌ DA EVITARE** Riferimenti ai pacchetti NuGet che richiedono una versione esatta.

Infine **Da non fare** indica un'azione da evitare nella maggior parte dei casi:

**❌ DA NON FARE** Pubblicare versioni con nome sicuro e non sicuro della stessa libreria. Ad esempio, `Contoso.Api` e `Contoso.Api.StrongNamed`.

>[!div class="step-by-step"]
[avanti](./get-started.md)
