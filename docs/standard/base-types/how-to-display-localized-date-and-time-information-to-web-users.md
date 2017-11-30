---
title: 'Procedura: visualizzare le informazioni su data e ora localizzate agli utenti del Web'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21493e0e0c9e42cf5efc42d86c8f126fbae9b392
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Procedura: visualizzare le informazioni su data e ora localizzate agli utenti del Web
Poiché una pagina Web può essere visualizzata ovunque nel mondo, operazioni di analisi e formattazione dei valori di data e ora non devono basarsi su un formato predefinito (in genere è il formato delle impostazioni cultura locali del server Web) durante l'interazione con l'utente. In alternativa, Web Form e gestire Data e l'ora di input di stringhe per l'utente deve analizzare le stringhe utilizzando la lingua preferita dell'utente. Analogamente, data e ora devono essere visualizzati all'utente in un formato conforme a impostazioni cultura dell'utente. In questo argomento viene illustrato come eseguire questa operazione.  
  
### <a name="to-parse-date-and-time-strings-input-by-the-user"></a>Per analizzare una data e ora le stringhe di input dall'utente  
  
1.  Determinare se la stringa ha restituito una matrice di <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> proprietà viene popolata. In caso contrario, andare al passaggio 6.  
  
2.  Se la matrice di stringhe restituito dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà viene popolata, recuperare il primo elemento. Il primo elemento indica che l'utente predefinito o lingua preferita e area.  
  
3.  Creare un'istanza di un <xref:System.Globalization.CultureInfo> oggetto che rappresenta l'utente preferita delle impostazioni cultura chiamando il <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> costruttore.  
  
4.  Chiamare il `TryParse` o `Parse` metodo il <xref:System.DateTime> o <xref:System.DateTimeOffset> tipo per provare a eseguire la conversione. Usare un overload di `TryParse` o `Parse` metodo con un `provider` parametro e passare uno dei seguenti:  
  
    -   Il <xref:System.Globalization.CultureInfo> oggetto creato nel passaggio 3.  
  
    -   Il <xref:System.Globalization.DateTimeFormatInfo> oggetto restituito dal <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> proprietà del <xref:System.Globalization.CultureInfo> oggetto creato nel passaggio 3.  
  
5.  Se la conversione non riesce, ripetere i passaggi da 2 a 4 per ogni elemento rimanente nella matrice di stringhe restituiti dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà.  
  
6.  Se la conversione non riesce o se la matrice di stringhe restituito dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà è vuota, analizzare la stringa utilizzando le impostazioni cultura invarianti, viene restituito dal <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> proprietà.  
  
### <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>Per analizzare la data e ora locali di richiesta dell'utente  
  
1.  Aggiungere un <xref:System.Web.UI.WebControls.HiddenField> controllo a un Web form.  
  
2.  Creare una funzione JavaScript che gestisce il `onClick` evento di un `Submit` pulsante scrivendo offset del fuso orario locale e l'ora e la data corrente da Coordinated Universal Time (UTC) per il <xref:System.Web.UI.WebControls.HiddenField.Value%2A> proprietà. Usare un delimitatore (ad esempio un punto e virgola) per separare i due componenti della stringa.  
  
3.  Usare il Web form <xref:System.Web.UI.Control.PreRender> inserire la funzione nel codice HTML dell'evento flusso di output passando il testo dello script per il <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType> metodo.  
  
4.  Connettere il gestore eventi per il `Submit` del pulsante `onClick` evento fornendo il nome della funzione JavaScript il `OnClientClick` attributo del `Submit` pulsante.  
  
5.  Creare un gestore per il `Submit` del pulsante <xref:System.Web.UI.WebControls.Button.Click> evento.  
  
6.  Nel gestore eventi, determinare se la stringa ha restituito una matrice di <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> proprietà viene popolata. In caso contrario, andare al passaggio 14.  
  
7.  Se la matrice di stringhe restituito dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà viene popolata, recuperare il primo elemento. Il primo elemento indica che l'utente predefinito o lingua preferita e area.  
  
8.  Creare un'istanza di un <xref:System.Globalization.CultureInfo> oggetto che rappresenta l'utente preferita delle impostazioni cultura chiamando il <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> costruttore.  
  
9. Passare la stringa assegnata al <xref:System.Web.UI.WebControls.HiddenField.Value%2A> proprietà per il <xref:System.String.Split%2A> metodo per archiviare la rappresentazione di stringa di data locale dell'utente e l'ora e la rappresentazione di stringa dell'offset del fuso orario locale dell'utente in elementi di matrice separati.  
  
10. Chiamare il <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> o <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType> metodo per convertire la data e l'ora della richiesta dell'utente per un <xref:System.DateTime> valore. Usare un overload del metodo con un `provider` parametro e passare uno dei seguenti:  
  
    -   Il <xref:System.Globalization.CultureInfo> oggetto creato nel passaggio 8.  
  
    -   Il <xref:System.Globalization.DateTimeFormatInfo> oggetto restituito dal <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> proprietà del <xref:System.Globalization.CultureInfo> oggetto creato nel passaggio 8.  
  
11. Se l'operazione di analisi nel passaggio 10 non riesce, andare al passaggio 13. In caso contrario, chiamare il <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType> per convertire la rappresentazione di stringa della differenza di fuso orario dell'utente a un numero intero.  
  
12. Creare un'istanza di un <xref:System.DateTimeOffset> che rappresenta l'ora locale dell'utente chiamando il <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType> costruttore.  
  
13. Se la conversione nel passaggio 10 non riesce, ripetere i passaggi da 7 a 12 per ogni elemento rimanente nella matrice di stringhe restituiti dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà.  
  
14. Se la conversione non riesce o se la matrice di stringhe restituito dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà è vuota, analizzare la stringa utilizzando le impostazioni cultura invarianti, viene restituito dal <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> proprietà. Ripetere i passaggi da 7 a 12.  
  
 Il risultato è un <xref:System.DateTimeOffset> oggetto che rappresenta l'ora locale dell'utente della pagina Web. È quindi possibile determinare l'ora UTC equivalente chiamando il <xref:System.DateTimeOffset.ToUniversalTime%2A> metodo. È anche possibile determinare la data e ora equivalente sul server Web mediante la chiamata di <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> metodo e passando il valore <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> come il fuso orario in cui convertire l'ora.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente contiene l'origine HTML e il codice per un Web form ASP.NET in cui viene chiesto all'utente di un valore di data e ora di input. Uno script sul lato client scrive anche informazioni sulla data locale e l'ora di richiesta dell'utente e l'offset del fuso orario dell'utente dall'ora UTC per un campo nascosto. Queste informazioni viene quindi analizzate dal server, che restituisce una pagina Web che consente di visualizzare l'input dell'utente. Visualizza anche la data e l'ora della richiesta dell'utente utilizzando l'ora locale dell'utente, l'ora sul server e l'ora UTC.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 Lo script sul lato client chiama il codice JavaScript `toLocaleString` metodo. Ciò produce una stringa che segue le convenzioni di formattazione delle impostazioni locali dell'utente, che è più probabile analizzare correttamente nel server.  
  
 Il <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> proprietà viene compilata con i nomi delle impostazioni cultura che sono contenuti in `Accept-Language` intestazioni incluse nella richiesta HTTP. Tuttavia, non tutti i browser includono `Accept-Language` intestazioni nelle rispettive richieste e gli utenti possono inoltre le intestazioni completamente. In questo modo, importante disporre di impostazioni cultura di fallback durante l'analisi dell'input dell'utente. In genere le impostazioni cultura di fallback sono la lingua inglese restituita da <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Gli utenti possono anche fornire Internet Explorer con i nomi delle impostazioni cultura che sono immessi in una casella di testo, che crea la possibilità che i nomi delle impostazioni cultura potrebbero non essere validi. In questo modo importante utilizzare la gestione delle eccezioni quando si crea un <xref:System.Globalization.CultureInfo> oggetto.  
  
 Quando recuperati da una richiesta HTTP inviata da Internet Explorer, il <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> matrice viene compilata in base alla preferenza dell'utente. Il primo elemento nella matrice contiene il nome di impostazioni cultura/area primaria dell'utente. Se la matrice contiene elementi aggiuntivi, Internet Explorer assegna loro arbitrariamente un identificatore di qualità, che è delimitato dal nome di lingua da un punto e virgola. Ad esempio, una voce per le impostazioni cultura fr-FR può avere il formato `fr-FR;q=0.7`.  
  
 Nell'esempio viene chiamato il <xref:System.Globalization.CultureInfo.%23ctor%2A> costruttore con il relativo `useUserOverride` parametro impostato su `false` per creare un nuovo <xref:System.Globalization.CultureInfo> oggetto. In questo modo, se il nome delle impostazioni cultura è il nome di lingua predefinito nel server, il nuovo <xref:System.Globalization.CultureInfo> oggetto creato dal costruttore della classe contiene le impostazioni cultura predefinite e non riflette le impostazioni utilizzando il server viene sottoposto a override  **Internazionali e della lingua** dell'applicazione. I valori delle impostazioni nel server sono probabilmente non esistono nel sistema dell'utente o essere riflessi nell'input dell'utente.  
  
 Poiché in questo esempio vengono analizzate due rappresentazioni di stringa di data e ora (una immessa dall'utente, l'altra memorizzata nel campo nascosto), vengono definiti i possibili <xref:System.Globalization.CultureInfo> gli oggetti che possono essere necessari in anticipo. Crea una matrice di <xref:System.Globalization.CultureInfo> gli oggetti che è maggiore del numero di elementi restituiti da uno di <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> proprietà. Crea quindi un <xref:System.Globalization.CultureInfo> dell'oggetto per ogni stringa di lingua/area geografica e un'istanza di un <xref:System.Globalization.CultureInfo> oggetto che rappresenta <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
 Il codice può chiamare il metodo di <xref:System.DateTime.Parse%2A> o <xref:System.DateTime.TryParse%2A> metodo per convertire la rappresentazione di stringa dell'utente di una data e ora in un <xref:System.DateTime> valore. Chiamate ripetute a un metodo di analisi potrebbero essere necessari per una singola operazione di analisi. Di conseguenza, il <xref:System.DateTime.TryParse%2A> metodo è preferibile perché restituisce `false` se un'operazione di analisi ha esito negativo. Al contrario, la gestione delle eccezioni ripetute che possono essere generate dal <xref:System.DateTime.Parse%2A> metodo può essere un metodo molto costosa in un'applicazione Web.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare il codice, creare un [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] pagina Web senza code-behind. Quindi copiare l'esempio nella pagina Web in modo che sostituisce tutto il codice esistente. Il [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] pagina Web deve contenere i seguenti controlli:  
  
-   Oggetto <xref:System.Web.UI.WebControls.Label> controllo, che non viene fatto riferimento nel codice. Impostare il relativo <xref:System.Web.UI.WebControls.TextBox.Text%2A> proprietà su "Immettere un numero:".  
  
-   Un controllo <xref:System.Web.UI.WebControls.TextBox> denominato `DateString`.  
  
-   Un controllo <xref:System.Web.UI.WebControls.Button> denominato `OKButton`. Impostare il relativo <xref:System.Web.UI.WebControls.Button.Text%2A> proprietà su "OK".  
  
-   Un controllo <xref:System.Web.UI.WebControls.HiddenField> denominato `DateInfo`.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per impedire l'inserimento di script nel flusso di HTML di un utente, l'input dell'utente non deve essere mai restituito direttamente nella risposta server. Al contrario, deve essere codificata tramite il <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)  
 [Analisi di stringhe di data e ora](../../../docs/standard/base-types/parsing-datetime.md)
