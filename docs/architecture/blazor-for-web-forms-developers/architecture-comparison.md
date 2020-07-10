---
title: Confronto tra architetture di ASP.NET Web Forms eBlazor
description: Informazioni sulle architetture di ASP.NET Web Forms e sul Blazor confronto.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/11/2019
ms.openlocfilehash: 51b114c842e131ad9b9a589bf5137a522e135082
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173432"
---
# <a name="architecture-comparison-of-aspnet-web-forms-and-blazor"></a>Confronto tra architetture di ASP.NET Web Forms eBlazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Sebbene i Web Form ASP.NET e Blazor abbiano molti concetti simili, esistono differenze nel modo in cui funzionano. Questo capitolo esamina i lavori interni e le architetture dei Web Form ASP.NET e Blazor .

## <a name="aspnet-web-forms"></a>Web Form ASP.NET

Il framework Web Form ASP.NET si basa su un'architettura incentrata sulle pagine. Ogni richiesta HTTP per una posizione nell'app è una pagina separata con cui ASP.NET risponde. Quando vengono richieste le pagine, il contenuto del browser viene sostituito con i risultati della pagina richiesta.

Le pagine sono costituite dai componenti seguenti:

- Markup HTML
- Codice C# o Visual Basic
- Classe code-behind che contiene le funzionalità per la logica e la gestione degli eventi
- Controlli

I controlli sono unità riutilizzabili dell'interfaccia utente Web a cui è possibile inserire e interagire a livello di codice in una pagina. Le pagine sono costituite da file che terminano con *. aspx* contenente markup, controlli e codice. Le classi code-behind si trovano in file con lo stesso nome di base e con estensione *aspx.cs* o *aspx. vb* , a seconda del linguaggio di programmazione usato. È interessante notare che il server Web interpreta il contenuto dei file con *estensione aspx* e li compila ogni volta che vengono modificati. Questa ricompilazione si verifica anche se il server Web è già in esecuzione.

I controlli possono essere compilati con markup e recapitati come controlli utente. Un controllo utente deriva dalla `UserControl` classe e ha una struttura simile alla pagina. Il markup per i controlli utente viene archiviato in un file con *estensione ascx* . Una classe code-behind associata si trova in un file con estensione *ascx.cs* o *ascx. vb* . I controlli possono anche essere compilati completamente con codice, ereditando dalla `WebControl` `CompositeControl` classe di base o.

Le pagine hanno anche un ciclo di vita completo degli eventi. Ogni pagina genera eventi per gli eventi di inizializzazione, caricamento, pre-rendering e scaricamento che si verificano durante l'esecuzione del codice della pagina per ogni richiesta da parte del runtime di ASP.NET.

I controlli in una pagina in genere eseguono il postback alla stessa pagina in cui è stato presentato il controllo e includono un payload da un campo modulo nascosto denominato `ViewState` . Il `ViewState` campo contiene informazioni sullo stato dei controlli nel momento in cui sono stati sottoposti a rendering e presentati nella pagina, consentendo al runtime di ASP.NET di confrontare e identificare le modifiche nel contenuto inviato al server.

## Blazor

Blazorè un Framework dell'interfaccia utente Web sul lato client simile per natura ai Framework front-end JavaScript come angolare o React. Blazorgestisce le interazioni dell'utente ed esegue il rendering degli aggiornamenti dell'interfaccia utente necessari. Blazor*non è* basato su un modello Request/Reply. Le interazioni dell'utente vengono gestite come eventi che non si trovano nel contesto di una particolare richiesta HTTP.

Blazorle app sono costituite da uno o più componenti radice di cui viene eseguito il rendering in una pagina HTML.

![Blazorcomponenti in HTML](./media/architecture-comparison/blazor-components-in-html.png)

Il modo in cui l'utente specifica la posizione in cui devono essere visualizzati i componenti e il modo in cui i componenti vengono collegati per le interazioni utente è l'hosting specifico del [modello](hosting-models.md)

Blazori [componenti](components.md) sono classi .NET che rappresentano una porzione di interfaccia utente riutilizzabile. Ogni componente mantiene il proprio stato e specifica la propria logica di rendering, che può includere il rendering di altri componenti. I componenti specificano i gestori eventi per interazioni utente specifiche per aggiornare lo stato del componente.

Dopo che un componente gestisce un evento, Blazor esegue il rendering del componente e tiene traccia delle modifiche apportate nell'output sottoposto a rendering. Non è possibile eseguire il rendering dei componenti direttamente nel Document Object Model (DOM). Eseguono invece il rendering in una rappresentazione in memoria del DOM denominato a in `RenderTree` modo che Blazor possa tenere traccia delle modifiche. BlazorConfronta l'output appena sottoposto a rendering con l'output precedente per calcolare una diff dell'interfaccia utente che viene quindi applicata in modo efficiente al DOM.

![BlazorInterazione DOM](./media/architecture-comparison/blazor-dom-interaction.png)

I componenti possono anche indicare manualmente che devono essere sottoposti a rendering se il relativo stato viene modificato al di fuori di un normale evento dell'interfaccia utente. BlazorUsa un oggetto `SynchronizationContext` per applicare un singolo thread logico di esecuzione. I metodi del ciclo di vita di un componente e tutti i callback di evento generati da Blazor vengono eseguiti in questo oggetto `SynchronizationContext` .

>[!div class="step-by-step"]
>[Precedente](introduction.md) 
> [Avanti](hosting-models.md)
