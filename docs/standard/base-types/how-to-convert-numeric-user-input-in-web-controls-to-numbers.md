---
title: "Procedura: Convertire in numeri l'input numerico dell'utente nei controlli Web"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af942b5e7576c13ff7be8d11c0009fd0c4f7462
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882479"
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Procedura: Convertire in numeri l'input numerico dell'utente nei controlli Web
Poiché una pagina Web può essere visualizzata ovunque nel mondo, gli utenti possono immettere dati numerici in un controllo <xref:System.Web.UI.WebControls.TextBox> in un numero praticamente illimitato di formati. Di conseguenza, è molto importante determinare le impostazioni locali e le impostazioni cultura dell'utente della pagina Web. Quando si analizza l'input dell'utente, è quindi possibile applicare le convenzioni di formattazione definite dalle impostazioni locali e dalle impostazioni cultura dell'utente.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>Per convertire l'input numerico da un controllo Web TextBox a un numero  
  
1. Determinare se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> è popolata. In caso contrario, andare al passaggio 6.  
  
2. Se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A> è popolata, recuperarne il primo elemento. Il primo elemento indica la lingua e l'area geografica predefinite o preferite dell'utente.  
  
3. Creare un'istanza di un oggetto <xref:System.Globalization.CultureInfo> che rappresenta le impostazioni cultura preferite dell'utente chiamando il costruttore <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType>.  
  
4. Chiamare il metodo `TryParse` o `Parse` del tipo numerico in cui si vuole convertire l'input dell'utente. Usare un overload del metodo `TryParse` o `Parse` con un parametro `provider` e passare uno degli oggetti seguenti:  
  
    - Oggetto <xref:System.Globalization.CultureInfo> creato nel passaggio 3.  
  
    - Oggetto <xref:System.Globalization.NumberFormatInfo> restituito dalla proprietà <xref:System.Globalization.CultureInfo.NumberFormat%2A> dell'oggetto <xref:System.Globalization.CultureInfo> creato nel passaggio 3.  
  
5. Se la conversione non riesce, ripetere i passaggi da 2 a 4 per ogni elemento rimanente nella matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A>.  
  
6. Se la conversione continua a non riuscire o se la matrice di stringhe restituita dalla proprietà <xref:System.Web.HttpRequest.UserLanguages%2A> è vuota, analizzare la stringa usando le impostazioni cultura inglese non dipendenti da paese/area geografica, restituite dalla proprietà <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente è la pagina code-behind completa per un Web Form che chiede all'utente di immettere un valore numerico in un controllo <xref:System.Web.UI.WebControls.TextBox> e lo converte in numero. Questo numero viene quindi raddoppiato e visualizzato usando le stesse regole di formattazione dell'input originale.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 La proprietà <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> viene popolata con i nomi delle impostazioni cultura contenuti nelle intestazioni `Accept-Language` incluse in una richiesta HTTP. Tuttavia, non tutti i browser includono intestazioni `Accept-Language` nelle rispettive richieste e gli utenti possono anche eliminare completamente le intestazioni. Di conseguenza, è importante avere impostazioni cultura di fallback durante l'analisi dell'input dell'utente. In genere le impostazioni cultura di fallback sono le impostazioni cultura inglese non dipendenti da paese/area geografica restituite da <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Gli utenti possono anche fornire a Internet Explorer nomi delle impostazioni cultura immessi in una casella di testo, ma questo crea la possibilità che tali nomi non siano validi. Di conseguenza, è importante usare la gestione delle eccezioni quando si crea un'istanza di un oggetto <xref:System.Globalization.CultureInfo>.  
  
 Quando viene recuperata da una richiesta HTTP inviata da Internet Explorer, la matrice <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> viene popolata in base alla preferenza dell'utente. Il primo elemento nella matrice contiene il nome delle impostazioni cultura/area geografica primarie dell'utente. Se la matrice contiene elementi aggiuntivi, Internet Explorer assegna loro arbitrariamente un identificatore di qualità, che è separato dal nome delle impostazioni cultura da un punto e virgola. Ad esempio, una voce per le impostazioni cultura fr-FR può avere questo formato: `fr-FR;q=0.7`.  
  
 L'esempio chiama il costruttore <xref:System.Globalization.CultureInfo.%23ctor%2A> con il relativo parametro `useUserOverride` impostato su `false` per creare un nuovo oggetto <xref:System.Globalization.CultureInfo>. In questo modo, se il nome delle impostazioni cultura è il nome delle impostazioni cultura predefinite nel server, il nuovo oggetto <xref:System.Globalization.CultureInfo> creato dal costruttore di classe contiene le impostazioni cultura predefinite e non riflette alcuna impostazione sostituita usando l'applicazione **Opzioni internazionali e della lingua** del server. Vi è una probabilità ridotta che i valori delle impostazioni sostituite nel server siano presenti nel sistema dell'utente o si riflettano sull'input dell'utente.  
  
 Il codice può chiamare il metodo `Parse` o `TryParse` del tipo numerico in cui verrà convertito l'input dell'utente. Per una singola operazione di analisi, possono essere necessarie chiamate ripetute a un metodo di analisi. Di conseguenza, il metodo `TryParse` è quello preferibile perché restituisce `false` se un'operazione di analisi non riesce. Al contrario, la gestione delle eccezioni ripetute che possono essere generate dal metodo `Parse` può rivelarsi un problema molto costoso in un'applicazione Web.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare il codice, copiarlo in una pagina code-behind ASP.NET in modo da sostituire tutto il codice esistente. La pagina Web ASP.NET deve contenere i controlli seguenti:  
  
- Controllo <xref:System.Web.UI.WebControls.Label>, che non è referenziato nel codice. Impostarne la proprietà <xref:System.Web.UI.WebControls.TextBox.Text%2A> su "Immettere un numero:".  
  
- Un controllo <xref:System.Web.UI.WebControls.TextBox> denominato `NumericString`.  
  
- Un controllo <xref:System.Web.UI.WebControls.Button> denominato `OKButton`. Impostarne la proprietà <xref:System.Web.UI.WebControls.Button.Text%2A> su "OK".  
  
 Sostituire il nome della classe `NumericUserInput` con il nome della classe definita dall'attributo `Inherits` della direttiva `Page` della pagina ASP.NET. Sostituire il nome del riferimento all'oggetto `NumericInput` con il nome definito dall'attributo `id` del tag `form` della pagina ASP.NET.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per impedire a un utente di inserire script nel flusso HTML, l'input dell'utente non deve essere mai restituito direttamente nella risposta del server. Al contrario, deve essere codificato tramite il metodo <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)
- [Analisi di stringhe numeriche](../../../docs/standard/base-types/parsing-numeric.md)
