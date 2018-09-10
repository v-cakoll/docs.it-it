---
title: 'Procedura: visualizzare le informazioni su data e ora localizzate agli utenti del Web'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27e9306164e3d0e008f38f2d94e1f9c11c0d7d3d
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085225"
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>Procedura: visualizzare le informazioni su data e ora localizzate agli utenti del Web
Poiché una pagina Web può essere visualizzata ovunque nel mondo, le operazioni di analisi e formattazione di valori di data e ora non devono essere basate su un formato predefinito, che molto spesso corrisponde al formato delle impostazioni cultura locali del server Web, durante l'interazione con l'utente. Al contrario, i Web Form che gestiscono stringhe di data e ora immesse dall'utente devono analizzare le stringhe tramite le impostazioni cultura preferite dell'utente. Analogamente, i dati di data e ora devono essere visualizzati all'utente in un formato conforme alle impostazioni cultura dell'utente stesso. In questo argomento viene illustrato come eseguire questa operazione.  
  
### <a name="to-parse-date-and-time-strings-input-by-the-user"></a>Per analizzare stringhe di data e ora immesse dall'utente  
  
1.  Determinare se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> è popolata. In caso contrario, andare al passaggio 6.  
  
2.  Se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A> è popolata, recuperarne il primo elemento. Il primo elemento indica la lingua e l'area geografica predefinite o preferite dell'utente.  
  
3.  Creare un'istanza di un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura preferite dell'utente chiamando il costruttore <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4.  Chiamare il metodo `TryParse` o `Parse` del tipo <xref:System.DateTime> o <xref:System.DateTimeOffset> per provare la conversione. Usare un overload del metodo `TryParse` o `Parse` con un parametro `provider` e passare uno degli oggetti seguenti:  
  
    -   Oggetto <xref:System.Globalization.CultureInfo> creato nel passaggio 3.  
  
    -   Oggetto <xref:System.Globalization.DateTimeFormatInfo> restituito dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> dell'oggetto <xref:System.Globalization.CultureInfo> creato nel passaggio 3.  
  
5.  Se la conversione non riesce, ripetere i passaggi da 2 a 4 per ogni elemento rimanente nella matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6.  Se la conversione continua a non riuscire o se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A> è vuota, analizzare la stringa usando le impostazioni cultura inglese non dipendenti da paese/area geografica, restituite dalla proprietà <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
### <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>Per analizzare la data e l'ora locali della richiesta dell'utente  
  
1.  Aggiungere un controllo <xref:System.Web.UI.WebControls.HiddenField> a un Web Form.  
  
2.  Creare una funzione JavaScript che gestisce l'evento `onClick` di un pulsante `Submit` scrivendo la data e l'ora correnti e la differenza di fuso orario locale rispetto all'ora Coordinated Universal Time (UTC) nella proprietà <xref:System.Web.UI.WebControls.HiddenField.Value%2A>. Usare un delimitatore, ad esempio un punto e virgola, per separare i due componenti della stringa.  
  
3.  Usare l'evento <xref:System.Web.UI.Control.PreRender> del Web Form per inserire la funzione nel flusso di output HTML passando il testo dello script al metodo <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4.  Connettere il gestore eventi all'evento `onClick` del pulsante `Submit` specificando il nome della funzione JavaScript nell'attributo `OnClientClick` del pulsante `Submit`.  
  
5.  Creare un gestore per l'evento <xref:System.Web.UI.WebControls.Button.Click> del pulsante `Submit`.  
  
6.  Nel gestore eventi determinare se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> è popolata. In caso contrario, andare al passaggio 14.  
  
7.  Se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A> è popolata, recuperarne il primo elemento. Il primo elemento indica la lingua e l'area geografica predefinite o preferite dell'utente.  
  
8.  Creare un'istanza di un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura preferite dell'utente chiamando il costruttore <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
9. Passare la stringa assegnata alla proprietà <xref:System.Web.UI.WebControls.HiddenField.Value%2A> al metodo <xref:System.String.Split%2A> per archiviare la rappresentazione di stringa della data e dell'ora locali dell'utente e la rappresentazione di stringa della differenza di fuso orario locale dell'utente in elementi di matrice separati.  
  
10. Chiamare il metodo <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> o <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType> per convertire la data e l'ora della richiesta dell'utente in un valore <xref:System.DateTime>. Usare un overload del metodo con un parametro `provider` e passare uno degli oggetti seguenti:  
  
    -   Oggetto <xref:System.Globalization.CultureInfo> creato nel passaggio 8.  
  
    -   Oggetto <xref:System.Globalization.DateTimeFormatInfo> restituito dalla proprietà <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> dell'oggetto <xref:System.Globalization.CultureInfo> creato nel passaggio 8.  
  
11. Se l'operazione di analisi nel passaggio 10 non riesce, andare al passaggio 13. In caso contrario, chiamare il metodo <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType> per convertire la rappresentazione di stringa della differenza di fuso orario dell'utente in un numero intero.  
  
12. Creare un'istanza di un oggetto <xref:System.DateTimeOffset> che rappresenta l'ora locale dell'utente chiamando il costruttore <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType>.  
  
13. Se la conversione nel passaggio 10 non riesce, ripetere i passaggi da 7 a 12 per ogni elemento rimanente nella matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
14. Se la conversione continua a non riuscire o se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A> è vuota, analizzare la stringa usando le impostazioni cultura inglese non dipendenti da paese/area geografica, restituite dalla proprietà <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Ripetere i passaggi da 7 a 12.  
  
 Il risultato è un oggetto <xref:System.DateTimeOffset> che rappresenta l'ora locale dell'utente della pagina Web. È quindi possibile determinare l'ora UTC equivalente chiamando il metodo <xref:System.DateTimeOffset.ToUniversalTime%2A>. È anche possibile determinare la data e l'ora equivalenti nel server Web chiamando il metodo <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> e passando il valore <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> come fuso orario in cui convertire l'ora.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente contiene l'origine HTML e il codice per un Web Form ASP.NET che chiede all'utente di immettere i valori di data e ora. Uno script sul lato client scrive anche le informazioni sulla data e sull'ora locali della richiesta dell'utente e la differenza di fuso orario dell'utente rispetto all'ora UTC in un campo nascosto. Queste informazioni vengono quindi analizzate dal server, che restituisce una pagina Web che visualizza l'input dell'utente. La pagina visualizza anche la data e l'ora della richiesta dell'utente usando l'ora locale dell'utente, l'ora nel server e l'ora UTC.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 Lo script sul lato client chiama il metodo JavaScript `toLocaleString`. Questa chiamata produce una stringa che segue le convenzioni di formattazione delle impostazioni locali dell'utente, che hanno maggiore probabilità di essere analizzate correttamente nel server.  
  
 La proprietà <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> viene popolata con i nomi delle impostazioni cultura contenuti nelle intestazioni `Accept-Language` incluse in una richiesta HTTP. Tuttavia, non tutti i browser includono intestazioni `Accept-Language` nelle rispettive richieste e gli utenti possono anche eliminare completamente le intestazioni. Di conseguenza, è importante avere impostazioni cultura di fallback durante l'analisi dell'input dell'utente. In genere le impostazioni cultura di fallback sono le impostazioni cultura inglese non dipendenti da paese/area geografica restituite da <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Gli utenti possono anche fornire a Internet Explorer nomi delle impostazioni cultura immessi in una casella di testo, ma questo crea la possibilità che tali nomi non siano validi. Di conseguenza, è importante usare la gestione delle eccezioni quando si crea un'istanza di un oggetto <xref:System.Globalization.CultureInfo>.  
  
 Quando viene recuperata da una richiesta HTTP inviata da Internet Explorer, la matrice <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> viene popolata in base alla preferenza dell'utente. Il primo elemento nella matrice contiene il nome delle impostazioni cultura/area geografica primarie dell'utente. Se la matrice contiene elementi aggiuntivi, Internet Explorer assegna loro arbitrariamente un identificatore di qualità, che è separato dal nome delle impostazioni cultura da un punto e virgola. Ad esempio, una voce per le impostazioni cultura fr-FR può avere questo formato: `fr-FR;q=0.7`.  
  
 L'esempio chiama il costruttore <xref:System.Globalization.CultureInfo.%23ctor%2A> con il relativo parametro `useUserOverride` impostato su `false` per creare un nuovo oggetto <xref:System.Globalization.CultureInfo>. In questo modo, se il nome delle impostazioni cultura è il nome delle impostazioni cultura predefinite nel server, il nuovo oggetto <xref:System.Globalization.CultureInfo> creato dal costruttore di classe contiene le impostazioni cultura predefinite e non riflette alcuna impostazione sostituita usando l'applicazione **Opzioni internazionali e della lingua** del server. Vi è una probabilità ridotta che i valori delle impostazioni sostituite nel server siano presenti nel sistema dell'utente o si riflettano sull'input dell'utente.  
  
 Poiché questo esempio analizza due rappresentazioni di stringa di una data e un'ora (una immessa dall'utente, l'altra archiviata nel campo nascosto), definisce gli oggetti <xref:System.Globalization.CultureInfo> possibili che potrebbero essere necessari in anticipo. L'esempio crea una matrice di oggetti <xref:System.Globalization.CultureInfo> maggiore di uno rispetto al numero di elementi restituiti dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType>. Crea quindi un'istanza di un oggetto <xref:System.Globalization.CultureInfo> per ogni stringa di lingua/area geografica e anche un'istanza di un oggetto <xref:System.Globalization.CultureInfo> che rappresenta <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
 Il codice può chiamare il metodo <xref:System.DateTime.Parse%2A> o <xref:System.DateTime.TryParse%2A> per convertire la rappresentazione di stringa dell'utente di una data e un'ora in un valore <xref:System.DateTime>. Per una singola operazione di analisi, possono essere necessarie chiamate ripetute a un metodo di analisi. Di conseguenza, il metodo <xref:System.DateTime.TryParse%2A> è quello preferibile perché restituisce `false` se un'operazione di analisi non riesce. Al contrario, la gestione delle eccezioni ripetute che possono essere generate dal metodo <xref:System.DateTime.Parse%2A> può rivelarsi un problema molto costoso in un'applicazione Web.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare il codice, creare una pagina Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] senza code-behind. Copiare quindi l'esempio nella pagina Web in modo da sostituire tutto il codice esistente. La pagina Web [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] deve contenere i controlli seguenti:  
  
-   Controllo <xref:System.Web.UI.WebControls.Label>, che non è referenziato nel codice. Impostarne la proprietà <xref:System.Web.UI.WebControls.TextBox.Text%2A> su "Immettere un numero:".  
  
-   Un controllo <xref:System.Web.UI.WebControls.TextBox> denominato `DateString`.  
  
-   Un controllo <xref:System.Web.UI.WebControls.Button> denominato `OKButton`. Impostarne la proprietà <xref:System.Web.UI.WebControls.Button.Text%2A> su "OK".  
  
-   Un controllo <xref:System.Web.UI.WebControls.HiddenField> denominato `DateInfo`.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per impedire a un utente di inserire script nel flusso HTML, l'input dell'utente non deve essere mai restituito direttamente nella risposta del server. Al contrario, deve essere codificato tramite il metodo <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)  
- [Stringhe di formato di data e ora standard](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
- [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)  
- [Analisi di stringhe di data e ora](../../../docs/standard/base-types/parsing-datetime.md)
