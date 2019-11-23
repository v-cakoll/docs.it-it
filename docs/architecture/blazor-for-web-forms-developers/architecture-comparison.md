---
title: Confronto tra architetture di ASP.NET Web Forms e Blazer
description: Informazioni sul confronto tra le architetture di ASP.NET Web Form e blazer.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 8ff733178e684666b69859bfab8b79fbad1fdff6
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "72520317"
---
# <a name="architecture-comparison-of-aspnet-web-forms-and-blazor"></a>Confronto tra architetture di ASP.NET Web Forms e Blazer

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Anche se ASP.NET Web Forms e blazer presentano molti concetti simili, esistono differenze nel modo in cui funzionano. Questo capitolo esamina i lavori interni e le architetture di ASP.NET Web Forms e blazer.

## <a name="aspnet-web-forms"></a>Web Form ASP.NET

Il framework Web Form ASP.NET si basa su un'architettura incentrata sulle pagine. Ogni richiesta HTTP per una posizione nell'app è una pagina separata con cui ASP.NET risponde. Quando vengono richieste le pagine, il contenuto del browser viene sostituito con i risultati della pagina richiesta.

Le pagine sono costituite dai componenti seguenti:

- Markup HTML
- Codice C# o Visual Basic
- Classe code-behind che contiene le funzionalità per la logica e la gestione degli eventi
- Controls

I controlli sono unità riutilizzabili dell'interfaccia utente Web a cui è possibile inserire e interagire a livello di codice in una pagina. Le pagine sono costituite da file che terminano con *. aspx* contenente markup, controlli e codice. Le classi code-behind si trovano in file con lo stesso nome di base e con estensione *aspx.cs* o *aspx. vb* , a seconda del linguaggio di programmazione usato. È interessante notare che il server Web interpreta il contenuto dei file con *estensione aspx* e li compila ogni volta che vengono modificati. Questa ricompilazione si verifica anche se il server Web è già in esecuzione.

I controlli possono essere compilati con markup e recapitati come controlli utente. Un controllo utente deriva dalla classe `UserControl` e ha una struttura simile alla pagina. Il markup per i controlli utente viene archiviato in un file con *estensione ascx* . Una classe code-behind associata si trova in un file con estensione *ascx.cs* o *ascx. vb* . I controlli possono anche essere compilati completamente con codice, ereditando dalla classe di base `WebControl` o `CompositeControl`.

Le pagine hanno anche un ciclo di vita completo degli eventi. Ogni pagina genera eventi per gli eventi di inizializzazione, caricamento, pre-rendering e scaricamento che si verificano durante l'esecuzione del codice della pagina per ogni richiesta da parte del runtime di ASP.NET.

I controlli in una pagina in genere eseguono il postback alla stessa pagina in cui è stato presentato il controllo e includono un payload da un campo modulo nascosto denominato `ViewState`. Il campo `ViewState` contiene informazioni sullo stato dei controlli nel momento in cui sono stati sottoposti a rendering e presentati nella pagina, consentendo al runtime di ASP.NET di confrontare e identificare le modifiche nel contenuto inviato al server.

## <a name="blazor"></a>Blazor

Blazer è un Framework dell'interfaccia utente Web sul lato client simile a quello dei Framework front-end JavaScript come angolare o React. Blazer gestisce le interazioni dell'utente ed esegue il rendering degli aggiornamenti dell'interfaccia utente necessari. Blazer *non è* basato su un modello Request/Reply. Le interazioni dell'utente vengono gestite come eventi che non si trovano nel contesto di una particolare richiesta HTTP.

Le app blazer sono costituite da uno o più componenti radice di cui viene eseguito il rendering in una pagina HTML.

![Componenti di Blazer in HTML](./media/architecture-comparison/blazor-components-in-html.png)

Il modo in cui l'utente specifica la posizione in cui devono essere visualizzati i componenti e il modo in cui i componenti vengono collegati per le interazioni utente è l'hosting specifico del [modello](hosting-models.md)

I [componenti](components.md) blazer sono classi .NET che rappresentano una porzione riutilizzabile dell'interfaccia utente. Ogni componente mantiene il proprio stato e specifica la propria logica di rendering, che può includere il rendering di altri componenti. I componenti specificano i gestori eventi per interazioni utente specifiche per aggiornare lo stato del componente.

Dopo che un componente gestisce un evento, blazer esegue il rendering del componente e tiene traccia delle modifiche apportate nell'output sottoposto a rendering. Non è possibile eseguire il rendering dei componenti direttamente nel Document Object Model (DOM). Eseguono invece il rendering in una rappresentazione in memoria del DOM denominato `RenderTree` in modo che Blazer possa tenere traccia delle modifiche. Blazer confronta l'output appena sottoposto a rendering con l'output precedente per calcolare una diff dell'interfaccia utente che viene quindi applicata in modo efficiente al DOM.

![Interazione DOM Blazer](./media/architecture-comparison/blazor-dom-interaction.png)

I componenti possono anche indicare manualmente che devono essere sottoposti a rendering se il relativo stato viene modificato al di fuori di un normale evento dell'interfaccia utente. Blazer usa un `SynchronizationContext` per applicare un singolo thread logico di esecuzione. I metodi del ciclo di vita di un componente e tutti i callback di evento generati da Blazer vengono eseguiti in questo `SynchronizationContext`.

>[!div class="step-by-step"]
>[Precedente](introduction.md)
>[Successivo](hosting-models.md)
