---
title: Scegliere tra app Web tradizionali e a pagina singola
description: Progettare applicazioni Web moderne con ASP.NET Core e Microsoft Azure
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.openlocfilehash: bbb217b2f11901658fa70a5e5cff6521d157952c
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104766"
---
# <a name="choose-between-traditional-web-apps-and-single-page-apps-spas"></a>Scegliere tra app Web tradizionali e a pagina singola

> "Legge di Atwood: qualsiasi applicazione che può essere creata in JavaScript, finirà per essere creata in JavaScript".  
> _\- Jeff Atwood_

## <a name="summary"></a>Riepilogo

Attualmente esistono due approcci generali alla creazione di applicazioni Web: le applicazioni Web tradizionali che eseguono la maggior parte della logica dell'applicazione nel server e le applicazioni a pagina singola (SPA, Single Page Application) che eseguono la maggior parte della logica dell'interfaccia utente in un Web browser, comunicando con il server Web principalmente attraverso API Web. È anche possibile un approccio ibrido: l'esempio più semplice è l'hosting di una o più sottoapplicazioni a pagina singola in un'applicazione Web tradizionale più grande.

L'uso delle applicazioni Web tradizionali è consigliato quando:

-   I requisiti lato client dell'applicazione sono semplici o di sola lettura.

-   L'applicazione deve funzionare in browser che non supportano JavaScript.

-   Il team non ha dimestichezza con le tecniche di sviluppo di JavaScript o TypeScript.

È consigliabile usare un' applicazione a pagina singola quando:

-   L'applicazione deve esporre un'interfaccia utente avanzata con numerose funzionalità.

-   Il team ha familiarità con lo sviluppo in JavaScript e/o TypeScript.

-   L'applicazione deve già esporre un'API per altri client (interni o pubblici).

I framework delle applicazioni a pagina singola richiedono anche maggiori conoscenze a livello di architettura e sicurezza. Tali framework soggetti a maggior varianza rispetto alle applicazioni Web tradizionali, a causa di aggiornamenti frequenti e nuovi framework. La configurazione dei processi di compilazione e distribuzione automatizzati e l'uso di opzioni di distribuzione come i contenitori risultano più difficili con le applicazioni a pagina singola che con le app Web tradizionali.

I miglioramenti dell'esperienza utente offerti dal modello di applicazione a pagina singola devono essere valutati a fronte di queste considerazioni.

## <a name="when-to-choose-traditional-web-apps"></a>Quando scegliere le app Web tradizionali

Di seguito vengono descritti in modo più dettagliato i motivi indicati in precedenza per la scelta delle applicazioni Web tradizionali.

**L'applicazione ha requisiti lato client semplici o di sola lettura**

Molte applicazioni Web vengono usate principalmente in modalità di sola lettura dalla maggior parte degli utenti. Le applicazioni di sola lettura (o prevalentemente di sola lettura) tendono a essere molto più semplici rispetto a quelle che devono gestire e modificare grandi quantità di codice. Ad esempio un motore di ricerca può essere costituito da un singolo punto di ingresso con una casella di testo e da una seconda pagina per la visualizzazione dei risultati della ricerca. Qualsiasi utente anonimo può formulare richieste e la logica lato client necessaria è minima. In modo analogo, l'applicazione destinata al pubblico di un blog o di un sistema di gestione dei contenuti è in genere costituita soprattutto da contenuto, con funzionalità lato client limitate. Le applicazioni di questo tipo possono essere create in modo semplice come applicazioni Web tradizionali, che eseguono la logica nel server Web e restituiscono risultati in formato HTML da visualizzare nel browser. Il fatto che ogni pagina univoca del sito disponga di un proprio URL, al quale i motori di ricerca possono applicare un segnalibro e un indice (per impostazione predefinita, senza aggiungere questa operazione come funzionalità separata dell'applicazione) è un altro evidente vantaggio in questi scenari.

**L'applicazione deve funzionare in browser che non supportano JavaScript**

Le applicazioni Web che devono funzionare in browser con supporto limitato o senza supporto per JavaScript devono essere scritte con i flussi di lavoro tradizionali per le app Web (o almeno devono essere in grado di attivare il comportamento corrispondente se necessario). Per il funzionamento delle applicazioni a pagina singola, JavaScript deve essere disponibile sul lato client. In caso contrario, le applicazioni a pagina singola non rappresentano la scelta ottimale.

**Il team non ha dimestichezza con le tecniche di sviluppo di JavaScript o TypeScript**

Se il team non ha dimestichezza con JavaScript o TypeScript, ma ha familiarità con lo sviluppo di applicazioni Web lato server, probabilmente potrà produrre un'app Web tradizionale più rapidamente di un'applicazione a pagina singola. A meno che l'apprendimento della programmazione di applicazioni a pagina singola non sia un obiettivo o che sia necessaria l'esperienza utente offerta da un'applicazione a pagina singola, le app Web tradizionali sono una scelta più produttiva per i team che hanno già familiarità con lo sviluppo di queste app.

## <a name="when-to-choose-spas"></a>Quando scegliere le applicazioni a pagina singola

Di seguito è riportata una spiegazione più dettagliata dei casi in cui è opportuno scegliere l'approccio di sviluppo applicazione a pagina singola per l'app Web.

**L'applicazione deve esporre un'interfaccia utente avanzata con numerose funzionalità**

Le applicazioni a pagina singola supportano funzionalità lato client complete, che non richiedono di ricaricare la pagina quando gli utenti eseguono operazioni o passano da un'area all'altra dell'app. Le applicazioni a pagina singola vengono caricate rapidamente recuperando i dati in background e le singole azioni dell'utente risultano più rapide, perché pagine vengono ricaricate completamente solo in casi sporadici. Le applicazioni a pagina singola supportano gli aggiornamenti incrementali, salvando documenti o moduli completati solo parzialmente senza richiedere all'utente di fare clic su un pulsante per inoltrare un modulo. Le applicazioni a pagina singola supportano comportamenti lato client complessi, quali il trascinamento della selezione, con maggior facilità rispetto alle applicazioni tradizionali. Le applicazioni a pagina singola possono anche essere progettate per l'esecuzione in modalità non connessa mediante aggiornamento di un modello lato client che viene sincronizzato nel server quando viene ristabilita una connessione. È consigliabile scegliere un'applicazione a pagina singola se i requisiti dell'app includono funzionalità complete, che vanno oltre quelle offerte dai tipici form HTML.

Si noti che in molti casi le applicazioni a pagina singola devono implementare funzionalità che sono incorporate nelle app Web tradizionali, quali la visualizzazione nella barra dell'indirizzo di un URL corretto che rifletta l'operazione in corso (e l'autorizzazione degli utenti alla creazione di un segnalibro o un deep link a tale URL, per poter tornare alla pagina). Infine le applicazioni a pagina singola devono consentire agli utenti di usare i pulsanti Indietro e Avanti del browser con risultati prevedibili.

**Il team ha familiarità con lo sviluppo in JavaScript e/o TypeScript**

Per creare applicazioni a pagina singola è necessario avere dimestichezza con JavaScript e/o TypeScript e con le tecniche e le librerie della programmazione lato client. Il team deve essere in grado di creare codice JavaScript moderno tramite un framework per applicazioni a pagina singola come Angular.

> ### <a name="references--spa-frameworks"></a>Riferimenti: framework per applicazioni a pagina singola
> - **Angular**  
> <https://angular.io>
> - **Confronto tra diversi framework JavaScript**  
> <https://javascriptreport.com/the-ultimate-guide-to-javascript-frameworks/>

**L'applicazione deve già esporre un'API per altri client (interni o pubblici)**

Se si supporta già un'API Web per l'uso con altri client, può risultare meno oneroso creare un'implementazione di tipo applicazione a pagina singola che si avvale di tale API anziché riprodurre la logica nel formato lato server. Le applicazioni a pagina singola usano sistematicamente le API Web per eseguire query e aggiornare i dati quando gli utenti interagiscono con l'applicazione.

## <a name="decision-table--traditional-web-or-spa"></a>Tabella per la scelta tra app Web tradizionale o applicazione a pagina singola

La tabella seguente riepiloga alcuni fattori di base da considerare nella scelta tra un'applicazione Web tradizionale e un'applicazione a pagina singola.

  | **Fattore** | **App Web tradizionale** | **Applicazione a pagina singola** |
  |---|---|---|
  | Il team deve conoscere JavaScript o TypeScript | **Minimo** | **Obbligatorio** |
  | Supporto dei browser senza script | **Supportato** | **Non supportato** |
  | Comportamento minimo dell'applicazione lato client | **Adeguato** | **Eccessivo** |
  | Esigenza di un'interfaccia utente dettagliata e complessa | **Limitato** | **Adeguato** |

>[!div class="step-by-step"]
[Precedente](modern-web-applications-characteristics.md)
[Successivo](architectural-principles.md)
