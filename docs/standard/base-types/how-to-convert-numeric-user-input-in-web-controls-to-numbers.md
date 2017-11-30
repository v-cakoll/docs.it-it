---
title: 'Procedura: convertire in numeri l''input numerico dell''utente nei controlli Web'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92e28e3b303a7523b9da69b7eb283e0261fc681c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>Procedura: convertire in numeri l'input numerico dell'utente nei controlli Web
Poiché una pagina Web può essere visualizzata ovunque nel mondo, gli utenti possono inserire dati numerici in un <xref:System.Web.UI.WebControls.TextBox> controllo in un numero illimitato di formati. Di conseguenza, è molto importante determinare le impostazioni locali e delle impostazioni cultura dell'utente della pagina Web. Quando si analizza l'input dell'utente, è quindi possibile applicare le convenzioni di formattazione definite dalle impostazioni internazionali dell'utente e delle impostazioni cultura.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>Per convertire un numero di input numerico da un controllo TextBox Web  
  
1.  Determinare se la stringa ha restituito una matrice di <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> proprietà viene popolata. In caso contrario, andare al passaggio 6.  
  
2.  Se la matrice di stringhe restituito dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà viene popolata, recuperare il primo elemento. Il primo elemento indica che l'utente predefinito o lingua preferita e area.  
  
3.  Creare un'istanza di un <xref:System.Globalization.CultureInfo> oggetto che rappresenta l'utente preferita delle impostazioni cultura chiamando il <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> costruttore.  
  
4.  Chiamare il `TryParse` o `Parse` input al metodo di tipo numerico che si desidera convertire l'utente. Usare un overload di `TryParse` o `Parse` metodo con un `provider` parametro e passare uno dei seguenti:  
  
    -   Il <xref:System.Globalization.CultureInfo> oggetto creato nel passaggio 3.  
  
    -   Il <xref:System.Globalization.NumberFormatInfo> oggetto restituito dal <xref:System.Globalization.CultureInfo.NumberFormat%2A> proprietà del <xref:System.Globalization.CultureInfo> oggetto creato nel passaggio 3.  
  
5.  Se la conversione non riesce, ripetere i passaggi da 2 a 4 per ogni elemento rimanente nella matrice di stringhe restituiti dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà.  
  
6.  Se la conversione non riesce o se la matrice di stringhe restituito dal <xref:System.Web.HttpRequest.UserLanguages%2A> proprietà è vuota, analizzare la stringa utilizzando le impostazioni cultura invarianti, viene restituito dal <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente è la pagina code-behind completa per un Web form in cui viene chiesto all'utente di immettere un valore numerico in un <xref:System.Web.UI.WebControls.TextBox> controllare e lo converte in un numero. Tale numero viene quindi raddoppiato e visualizzato utilizzando le stesse regole di formattazione dell'input originale.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 Il <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> proprietà viene compilata con i nomi delle impostazioni cultura che sono contenuti in `Accept-Language` intestazioni incluse nella richiesta HTTP. Tuttavia, non tutti i browser includono `Accept-Language` intestazioni nelle rispettive richieste e gli utenti possono inoltre le intestazioni completamente. In questo modo, importante disporre di impostazioni cultura di fallback durante l'analisi dell'input dell'utente. In genere, le impostazioni cultura di fallback sono la lingua inglese restituita da <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>. Gli utenti possono anche fornire Internet Explorer con i nomi delle impostazioni cultura che sono immessi in una casella di testo, che crea la possibilità che i nomi delle impostazioni cultura potrebbero non essere validi. In questo modo importante utilizzare la gestione delle eccezioni quando si crea un <xref:System.Globalization.CultureInfo> oggetto.  
  
 Quando recuperati da una richiesta HTTP inviata da Internet Explorer, il <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> matrice viene compilata in base alla preferenza dell'utente. Il primo elemento nella matrice contiene il nome di impostazioni cultura/area primaria dell'utente. Se la matrice contiene elementi aggiuntivi, Internet Explorer assegna loro arbitrariamente un identificatore di qualità, che è delimitato dal nome di lingua da un punto e virgola. Ad esempio, una voce per le impostazioni cultura fr-FR può avere il formato `fr-FR;q=0.7`.  
  
 Nell'esempio viene chiamato il <xref:System.Globalization.CultureInfo.%23ctor%2A> costruttore con il relativo `useUserOverride` parametro impostato su `false` per creare un nuovo <xref:System.Globalization.CultureInfo> oggetto. In questo modo, se il nome delle impostazioni cultura è il nome di lingua predefinito nel server, il nuovo <xref:System.Globalization.CultureInfo> oggetto creato dal costruttore della classe contiene le impostazioni cultura predefinite e non riflette le impostazioni utilizzando il server viene sottoposto a override  **Internazionali e della lingua** dell'applicazione. I valori delle impostazioni nel server sono probabilmente non esistono nel sistema dell'utente o essere riflessi nell'input dell'utente.  
  
 Il codice può chiamare il metodo di `Parse` o `TryParse` verrà convertito in metodo di tipo numerico che l'input dell'utente. Chiamate ripetute a un metodo di analisi potrebbero essere necessari per una singola operazione di analisi. Di conseguenza, il `TryParse` metodo è preferibile, perché restituisce `false` se un'operazione di analisi ha esito negativo. Al contrario, la gestione delle eccezioni ripetute che possono essere generate dal `Parse` metodo può essere un metodo molto costosa in un'applicazione Web.  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per compilare il codice, copiarlo in un [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] pagina code-behind in modo che non sostituisce tutto il codice esistente. Il [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] pagina Web deve contenere i seguenti controlli:  
  
-   Oggetto <xref:System.Web.UI.WebControls.Label> controllo, che non viene fatto riferimento nel codice. Impostare il relativo <xref:System.Web.UI.WebControls.TextBox.Text%2A> proprietà su "Immettere un numero:".  
  
-   Un controllo <xref:System.Web.UI.WebControls.TextBox> denominato `NumericString`.  
  
-   Un controllo <xref:System.Web.UI.WebControls.Button> denominato `OKButton`. Impostare il relativo <xref:System.Web.UI.WebControls.Button.Text%2A> proprietà su "OK".  
  
 Modificare il nome della classe da `NumericUserInput` per il nome della classe definita dal `Inherits` attributo del [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] della pagina `Page` direttiva. Modificare il nome del `NumericInput` riferimento al nome definito dall'oggetto di `id` attributo del [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] della pagina `form` tag.  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 Per impedire l'inserimento di script nel flusso di HTML di un utente, l'input dell'utente non deve essere mai restituito direttamente nella risposta server. Al contrario, deve essere codificata tramite il <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Esecuzione di operazioni di formattazione](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Analisi di stringhe numeriche](../../../docs/standard/base-types/parsing-numeric.md)
