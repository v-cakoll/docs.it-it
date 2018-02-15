---
title: Scegliere tra le app web tradizionali e singola pagina
description: Architetto moderne applicazioni web con ASP.NET Core e Microsoft Azure
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: eb830ede1b644700a80f0e9fac2f3608deb88276
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Scegliere tra le app Web tradizionali e singola pagina (stabilimenti termali)

> "Diritto del Atwood: qualsiasi applicazione che può essere scritta in JavaScript, infine verrà scritto in JavaScript."  
> _\- Jeff Atwood_

## <a name="summary"></a>Riepilogo

Esistono due approcci generali per la creazione di applicazioni web oggi: applicazioni web tradizionali che eseguono la maggior parte della logica dell'applicazione sul server e applicazioni a pagina singola (stabilimenti termali) che eseguono la maggior parte della logica dell'interfaccia utente in un web browser, comunicazione con il server web principalmente tramite l'API web. Un approccio ibrido è anche possibile, il più semplice da host a uno o più simile a SPA secondario applicazioni complete all'interno di un'applicazione web tradizionale più grande.

È necessario utilizzare le applicazioni web tradizionali quando:

-   I requisiti dell'applicazione sul lato client sono semplici o di sola lettura.

-   L'applicazione deve funzionare in browser senza supporto JavaScript.

-   Il team non ha dimestichezza con le tecniche di sviluppo JavaScript o TypeScript.

È consigliabile utilizzare un SPA quando:

-   L'applicazione deve esporre un'interfaccia utente avanzata con numerose funzionalità.

-   Il team è familiare con lo sviluppo di JavaScript e/o TypeScript.

-   L'applicazione deve già espongono un'API per gli altri client (interno o pubblico).

Inoltre, il Framework SPA richiede maggiore dell'architettura e l'esperienza di sicurezza. Si verifica maggiore varianza a causa di aggiornamenti frequenti e nuovi Framework rispetto alle applicazioni web tradizionali. Configurazione dei processi di compilazione e distribuzione automatizzati e che utilizzano le opzioni di distribuzione come contenitori sono più difficili con applicazioni di SPA rispetto alle App web tradizionali.

Miglioramenti nell'esperienza utente resa possibile dal modello SPA devono essere confrontati con queste considerazioni.

## <a name="when-to-choose-traditional-web-apps"></a>Quando scegli App web tradizionali

Di seguito viene fornita una spiegazione più dettagliata dei motivi indicati in precedenza per il prelievo di applicazioni web tradizionali.

**L'applicazione ha requisiti semplici, possibilmente in sola lettura, sul lato client**

Molte applicazioni web vengono utilizzate principalmente in una modalità di sola lettura per la maggior parte degli utenti. Applicazioni di sola lettura (o prevalentemente di sola lettura) tendono a essere molto più semplice rispetto a quelli che gestiscono e modificare un notevole dello stato. Ad esempio, un motore di ricerca può essere costituito da un singolo punto di ingresso con una casella di testo e una seconda pagina per visualizzare i risultati della ricerca. Gli utenti anonimi è possono apportare facilmente le richieste ed è necessario per la logica sul lato client. Analogamente, applicazione pubblico di un blog o nel contenuto gestione del sistema in genere è costituito principalmente contenuto con piccolo comportamento sul lato client. Tali applicazioni facilmente compilate come applicazioni web tradizionale basato su server che eseguono la logica nel server web e il rendering di HTML da visualizzare nel browser. Il fatto che ogni pagina del sito univoco dispone del proprio URL che può essere rimossa e indicizzato dai motori di ricerca (impostazione predefinita, senza dover aggiungere questo elemento come funzionalità separata dell'applicazione) è anche un evidente vantaggio in tali scenari.

**L'applicazione deve funzionare in browser senza supporto JavaScript**

Applicazioni Web che richiedono la funzione nei browser con limitato o nessun supporto JavaScript devono essere scritto utilizzando flussi di lavoro app web tradizionali o almeno in grado di eseguire il fallback a tale comportamento. Per funzionare; stabilimenti termali richiedono JavaScript sul lato client Se non è disponibile, stabilimenti termali non sono una buona scelta.

**Il team non ha dimestichezza con le tecniche di sviluppo JavaScript o TypeScript**

Se il team non ha dimestichezza con JavaScript o TypeScript, ma ha familiarità con lo sviluppo di applicazioni web sul lato server, probabilmente sarà in grado di fornire più rapidamente un SPA un'app web tradizionali. A meno che l'apprendimento di stabilimenti termali programma è un obiettivo o l'esperienza utente offerta da un SPA è necessario, App web tradizionali sono una scelta più produttiva per i team che hanno già familiarità con la compilazione.

## <a name="when-to-choose-spas"></a>Quando scegliere stabilimenti termali

Di seguito viene fornita una spiegazione più dettagliata del momento in cui scegliere uno stile di applicazioni a pagina singola di sviluppo per l'app web.

**L'applicazione deve esporre un'interfaccia utente avanzata con molte funzionalità**

Stabilimenti termali possono supportare funzionalità complete di sul lato client che non richiede il ricaricamento della pagina come utenti di eseguono azioni o passare tra le aree dell'app. Stabilimenti termali possono caricare più rapidamente, recupero dei dati in background, e le azioni utente sono più reattive poiché Ricarica pagina intera è rari. Stabilimenti termali possono supportare gli aggiornamenti incrementali, salvataggio form completata parzialmente o documenti senza che sia necessario fare clic su un pulsante per inviare un form. Stabilimenti termali possono supportare i comportamenti sul lato client complessi, ad esempio di trascinamento e rilascio, molto più rapidamente rispetto alle applicazioni tradizionali. Stabilimenti termali possono essere progettate per l'esecuzione in modalità disconnessa, effettuare aggiornamenti a un modello sul lato client che vengono sincronizzati infine al server quando viene ristabilita una connessione. È consigliabile scegliere un'applicazione di tipo SPA se i requisiti dell'app includono funzionalità complete che vanno oltre cosa offre tipico form HTML.

Si noti che spesso stabilimenti termali necessario per implementare le funzionalità incorporate per App web tradizionali, ad esempio la visualizzazione di un URL significativo indirizzo barra che riflettono l'operazione corrente (e che consente agli utenti di segnalibro o un collegamento diretto a questo URL per restituire a esso). Stabilimenti termali, inoltre, devono consentire agli utenti di utilizzare il browser pulsanti Indietro e avanti con risultati che non sorprendere li.

**Il team ha familiarità con lo sviluppo di JavaScript e/o TypeScript**

La scrittura stabilimenti termali richiede una certa familiarità con JavaScript e/o TypeScript e tecniche di programmazione sul lato client e librerie. Il team deve essere competente nella scrittura moderni JavaScript con un framework di SPA come angolare.

> ### <a name="references--spa-frameworks"></a>Riferimenti: Framework SPA
> - **AngularJS**  
> <https://angularjs.org/>
> - **Confronto di 4 Framework JavaScript comuni**  
> <https://www.developereconomics.com/feature-comparison-of-4-popular-js-mv-frameworks>

**L'applicazione deve già espongono un'API per gli altri client (interno o pubblico)**

Se si sta già di supportare un'API web per l'utilizzo da altri client, potrebbe essere necessario meno lavoro richiesto per creare un'implementazione di SPA che sfrutta queste API, anziché riprodurre la logica del form sul lato server. Stabilimenti termali usano ampiamente API web per query e aggiornare i dati quando gli utenti interagiscono con l'applicazione.

## <a name="decision-table--traditional-web-or-spa"></a>Tabella decisioni – Web tradizionali o SPA

La tabella decisioni seguente vengono riepilogati alcuni dei fattori da considerare nella scelta tra un'applicazione web tradizionale e un SPA base.

  | **Fattore** | **App Web tradizionali** | **Applicazione a pagina singola** |
  |---|---|---|
  | Conoscenza obbligatorie del Team con JavaScript o TypeScript | **Minimal** | **Obbligatorio** |
  | Supportare i browser senza script | **Supportato** | Non è supportato |
  | Comportamento dell'applicazione sul lato Client minima | **Well-Suited** | **Eccessivi** |
  | Requisiti dell'interfaccia utente dettagliate e complesse | **Limitato** | **Well-Suited** |

>[!div class="step-by-step"]
[Precedente] (modern-web-applicazioni-characteristics.md) [successivo](architectural-principles.md)
